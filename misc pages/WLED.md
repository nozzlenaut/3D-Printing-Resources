# WLED with Klipper and Moonraker

This walkthrough shows one way to control WLED presets from Klipper through Moonraker.

The example uses a controller named `controller`, four WLED presets, and printer-specific macros. Change the IP address, LED count, preset numbers, sensor names, and printer commands to match your hardware.

> **Before you begin:** Back up your working Klipper and Moonraker configuration. Confirm the LED voltage, controller limits, wiring, fuse protection, and power-injection requirements. Do not power a long LED strip directly from a small controller board.

## 1. Prepare the WLED Controller

1. Read the WLED [getting-started guide](https://kno.wled.ge/basics/getting-started/).
2. Confirm that your control board and LEDs are supported. ESP32, ESP8266, and D1 Mini boards are common options.
3. Install WLED with the [browser-based installer](https://install.wled.me/).
4. Wire the LEDs and test them through the WLED web interface or mobile app.

For a small number of LEDs, the controller may be able to supply power directly. Larger installations usually require an appropriately sized external supply or buck converter with power injection. Follow the WLED wiring guidance for your voltage and strip length.

At this stage, the LEDs should work independently through WLED before Klipper or Moonraker is involved.

## 2. Add WLED to Moonraker

Add a WLED section to `moonraker.conf`:

```ini
[wled controller]          # Rename "controller" if desired
type: http
address: 192.168.68.77     # IP address of the WLED controller
initial_preset: 1          # Preset applied when Moonraker starts
chain_count: 120           # Number of LEDs in the strip
```

Restart Moonraker after saving the configuration.

See the official [Moonraker WLED documentation](https://moonraker.readthedocs.io/en/latest/configuration/#wled) for all supported options.

## 3. Create WLED Presets

Open the WLED interface and create the presets you want to call from Klipper. Presets can represent printer states, chamber lighting, accent lighting, or any other arrangement.

When saving each preset:

1. Choose **Save to ID**.
2. Assign a number.
3. Record the number for use in the Klipper macros.

This example uses:

- Preset `1`: default lighting
- Preset `2`: an “off” preset
- Preset `3`: chamber lighting
- Preset `4`: skirt lighting

WLED can also apply a default startup preset from its settings.

## 4. Add Klipper Macros

Add macros like these to `printer.cfg` or a separate included macro file.

```ini
[gcode_macro WLED_ON]
description: Apply the default WLED preset
gcode:
  {% set strip = params.STRIP|default("controller")|string %}
  {% set preset = params.PRESET|default(1)|int %}
  {action_call_remote_method("set_wled_state",
                             strip=strip,
                             state=True,
                             preset=preset)}

[gcode_macro WLED_OFF]
description: Apply the WLED off preset
gcode:
  {% set strip = params.STRIP|default("controller")|string %}
  {% set preset = params.PRESET|default(2)|int %}
  {action_call_remote_method("set_wled_state",
                             strip=strip,
                             state=True,
                             preset=preset)}

[gcode_macro CHAMBER_ON]
description: Apply the chamber-lighting preset
gcode:
  {% set strip = params.STRIP|default("controller")|string %}
  {% set preset = params.PRESET|default(3)|int %}
  {action_call_remote_method("set_wled_state",
                             strip=strip,
                             state=True,
                             preset=preset)}

[gcode_macro SKIRT_ON]
description: Apply the skirt-lighting preset
gcode:
  {% set strip = params.STRIP|default("controller")|string %}
  {% set preset = params.PRESET|default(4)|int %}
  {action_call_remote_method("set_wled_state",
                             strip=strip,
                             state=True,
                             preset=preset)}
```

This `WLED_OFF` example applies preset `2`, which is expected to be an off preset. To turn the strip off directly instead, use Moonraker's supported `state=False` behavior.

After restarting Klipper, the macros should appear as buttons in Mainsail or Fluidd.

You can also pass a different preset manually:

```gcode
WLED_ON PRESET=4
```

Another useful reference is [Gliptopolis' WLED Klipper guide](https://github.com/Gliptopolis/WLED_Klipper).

## 5. Call WLED from Print Macros

The following example calls `WLED_ON` near the beginning of `PRINT_START` and `WLED_OFF` in `PRINT_END`.

> **Important:** This is a printer-specific Voron-style example. It references Stealthburner status macros, quad gantry leveling, a chamber temperature sensor, a bed mesh, and other configuration that may not exist on your printer. Copy only the parts you understand and adapt them to your setup.

```ini
[gcode_macro PRINT_START]
gcode:
  # Values supplied by the slicer
  {% set target_bed = params.BED|int %}
  {% set target_extruder = params.EXTRUDER|int %}
  {% set target_chamber = params.CHAMBER|default("40")|int %}
  {% set x_wait = printer.toolhead.axis_maximum.x|float / 2 %}
  {% set y_wait = printer.toolhead.axis_maximum.y|float / 2 %}

  # Home the printer and enable the default WLED preset
  STATUS_HOMING
  WLED_ON
  G28
  G90

  # Clear a previously saved bed mesh
  BED_MESH_CLEAR

  # Heat-soak logic for higher bed temperatures
  {% if params.BED|int > 90 %}
    SET_DISPLAY_TEXT MSG="Bed: {target_bed}c"
    STATUS_HEATING
    M106 S255

    # Uncomment if configured
    # SET_PIN PIN=nevermore VALUE=1

    G1 X{x_wait} Y{y_wait} Z15 F9000
    M190 S{target_bed}
    SET_DISPLAY_TEXT MSG="Heat soak: {target_chamber}c"
    TEMPERATURE_WAIT SENSOR="temperature_sensor chamber" MINIMUM={target_chamber}
  {% else %}
    SET_DISPLAY_TEXT MSG="Bed: {target_bed}c"
    STATUS_HEATING
    G1 X{x_wait} Y{y_wait} Z15 F9000
    M190 S{target_bed}
    SET_DISPLAY_TEXT MSG="Soak for 5 min"

    # Uncomment to wait five minutes
    # G4 P300000
  {% endif %}

  # Heat the nozzle before Z-related calibration
  SET_DISPLAY_TEXT MSG="Hotend: 150c"
  M109 S150

  # Voron 2.4 quad gantry leveling
  SET_DISPLAY_TEXT MSG="QGL"
  STATUS_LEVELING
  QUAD_GANTRY_LEVEL
  G28 Z

  # Generate a bed mesh
  SET_DISPLAY_TEXT MSG="Bed mesh"
  STATUS_MESHING
  BED_MESH_CALIBRATE

  # Heat the nozzle to the slicer target
  SET_DISPLAY_TEXT MSG="Hotend: {target_extruder}c"
  STATUS_HEATING
  G1 X{x_wait} Y{y_wait} Z15 F9000
  M107
  M109 S{target_extruder}

  # Purge line and printing state
  SET_DISPLAY_TEXT MSG="Printer goes brr"
  STATUS_PRINTING
  G0 X{x_wait - 50} Y4 F10000
  G0 Z0.4
  G91
  G1 X100 E20 F1000
  G90

[gcode_macro PRINT_END]
description: Safely finish a print and apply the WLED off preset
gcode:
  {% set th = printer.toolhead %}
  {% set x_safe = th.position.x + 20 * (1 if th.axis_maximum.x - th.position.x > 20 else -1) %}
  {% set y_safe = th.position.y + 20 * (1 if th.axis_maximum.y - th.position.y > 20 else -1) %}
  {% set z_safe = [th.position.z + 2, th.axis_maximum.z]|min %}

  SAVE_GCODE_STATE NAME=STATE_PRINT_END

  M400
  G92 E0
  G1 E-5.0 F1800

  TURN_OFF_HEATERS

  G90
  G0 X{x_safe} Y{y_safe} Z{z_safe} F20000
  G0 X{th.axis_maximum.x//2} Y{th.axis_maximum.y - 2} F3600
  M107

  BED_MESH_CLEAR
  WLED_OFF

  RESTORE_GCODE_STATE NAME=STATE_PRINT_END MOVE=0
```

Once the basic integration works, you can create additional presets and macros for homing, heating, leveling, errors, or completed prints.
