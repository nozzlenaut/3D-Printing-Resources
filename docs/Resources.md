---
title: Manuals, Hardware, and Software Resources
---

# 3D-Printing Resources

A categorized collection of official documentation, original project repositories, configuration examples, and practical reference material.

> **Note:** Hardware can have multiple revisions. Confirm the exact board, display, probe, or toolhead version before using a wiring diagram or configuration file.

## Contents

- [CAD](#cad)
- [Camera Setup](#camera-setup)
- [Displays](#displays)
- [Extruders](#extruders)
- [Filament](#filament)
- [General Documentation and Communities](#general-documentation-and-communities)
- [Hotends](#hotends)
- [Input-Shaper Hardware](#input-shaper-hardware)
- [Klipper](#klipper)
- [Mainboards](#mainboards)
- [Probes](#probes)
- [Printer Manuals](#printer-manuals)
- [Printheads](#printheads)
- [Raspberry Pi](#raspberry-pi)
- [Slicers](#slicers)
- [Toolhead Boards](#toolhead-boards)

## CAD

- [Tinkercad](https://www.tinkercad.com/) — beginner-friendly browser-based modeling
- [Fusion 360 for Personal Use](https://www.autodesk.com/products/fusion-360/personal) — free personal-use tier with feature limitations
- [Onshape](https://www.onshape.com/en/) — browser-based CAD; documents created with the free plan are public

## Camera Setup

- [Fluidd Camera Configuration](https://docs.fluidd.xyz/features/cameras) — supports many USB webcams and may require [Crowsnest](https://docs.fluidd.xyz/features/cameras#crowsnest-support)
- [Mainsail Webcam Configuration](https://docs.mainsail.xyz/overview/settings/webcams) — supports many USB webcams and may require [Crowsnest](https://crowsnest.mainsail.xyz/)
- [Raspberry Pi Camera Module](https://www.raspberrypi.com/documentation/accessories/camera.html)

## Displays

- [Fysetc Mini 12864](https://github.com/FYSETC/FYSETC-Mini-12864-Panel/blob/master/README.md) — [Amazon](https://amzn.to/4awzZQt)
- [BTT HDMI5](https://github.com/bigtreetech/docs/blob/master/docs/HDMI5.md) — [Amazon](https://amzn.to/4cA6saE)
- [BTT HDMI7 V1.0](https://github.com/bigtreetech/docs/blob/master/docs/HDMI7%20V1.0.md) — [Amazon](https://amzn.to/3Tz8wqz)
- [BTT HDMI7 V1.2](https://github.com/bigtreetech/docs/blob/master/docs/HDMI7%20V1.2.md)
- [BTT KNOMI](https://github.com/bigtreetech/docs/blob/master/docs/KNOMI.md) — [Amazon](https://amzn.to/4a9yrfH)
- [BTT KNOMI 2](https://github.com/bigtreetech/docs/blob/master/docs/KNOMI2.md) — [Amazon](https://amzn.to/49in3g2)
- [Raspberry Pi Official 7-inch Display](https://www.raspberrypi.com/documentation/accessories/display.html)
- [BTT TFT24](https://github.com/bigtreetech/docs/blob/master/docs/TFT24.md)
- [BTT TFT35 E3](https://github.com/bigtreetech/docs/blob/master/docs/TFT35%20E3.md)
- [BTT TFT35 SPI](https://github.com/bigtreetech/docs/blob/master/docs/TFT35%20SPI.md) — [Amazon](https://amzn.to/49d7yG4)
- [BTT TFT35](https://github.com/bigtreetech/docs/blob/master/docs/TFT35.md)
- [BTT TFT43-DIP](https://github.com/bigtreetech/docs/blob/master/docs/TFT43-DIP.md)
- [BTT TFT50](https://github.com/bigtreetech/BIGTREETECH-TouchScreenHardware/tree/master/BTT%20Pi%20TFT50%20V2.0%20Github) — [Amazon](https://amzn.to/43jhuxL)

## Extruders

- Annex Engineering Sherpa [Mini](https://github.com/Annex-Engineering/Sherpa_Mini-Extruder) and [Micro](https://github.com/Annex-Engineering/Sherpa_Micro-Extruder)
- [Bondtech Extruders](https://www.bondtech.se/product-category/extruders/)
- **Orbiter Extruder** — LDO-designed extruder available from multiple suppliers; the original product page was unavailable when this list was compiled
- [Vz-HextrudORT](https://github.com/VzBoT3D/Vz-HextrudORT)

## Filament

- [Bambu Lab Filament Guide](https://bambulab.com/en/filament-guide)
- [Prusa Material Guide](https://help.prusa3d.com/materials)
- [Simplify3D Materials Guide](https://www.simplify3d.com/resources/materials-guide/) — material uses, advantages, and tradeoffs

## General Documentation and Communities

- [BTT Wiki](https://bttwiki.com/) — if the site is unavailable, the [BTT documentation repository](https://github.com/bigtreetech/docs/tree/master/docs) contains much of the same material
- [LDO Documentation](https://docs.ldomotors.com/) — documentation for LDO kits and parts
- [Prusa Forum](https://forum.prusa3d.com/)
- [RatOS Configuration Examples](https://github.com/Rat-OS/RatOS-configuration)
- [TeamFDM](https://www.teamfdm.com/) — primarily Voron-focused, with information that applies to many printers
- [Voron Design Forum](https://forum.vorondesign.com/)

## Hotends

- [Bambu Lab Hotend](https://store.bambulab.com/collections/bambu-hotends/products/hotend-with-nozzle) — increasingly supported by third-party printhead designs
- [neXt-G Hotend](https://github.com/Dropeffect/neXt-G-Hotend)
- [E3D Revo Support](https://e3d-online.zendesk.com/hc/en-us/categories/6051537794333-Revo-Support)
- [Phaetus GitHub Repositories](https://github.com/Phaetus?tab=repositories) — locate the repository for the specific hotend model
- [Slice Engineering Support](https://support.sliceengineering.com/portal/en/kb/slice-engineering) — Mosquito-family hotends
- [XG Hotend](https://github.com/Dropeffect/XG-Hotend)

## Input-Shaper Hardware

- [BTT USB ADXL345 V2.0 Manual](https://cdn.shopify.com/s/files/1/1619/4791/files/BIGTREETECH_ADXL345_V2.0_User_Manual.pdf?v=1694085087) — [Amazon](https://amzn.to/3VBDH7c)
- [DIY ADXL345](https://amzn.to/3TvEO5P) — setup may be documented in the mainboard manual; see Klipper's [resonance measurement guide](https://www.klipper3d.org/Measuring_Resonances.html#adxl345) for Raspberry Pi and RP2040 options
- [Fysetc Portable Input Shaper](https://github.com/FYSETC/FYSETC-PortableInputShaper/blob/main/README.md) — [Amazon](https://amzn.to/43uNPAN)

> Some toolhead boards include an accelerometer. Check the board features before buying a separate input-shaper board.

## Klipper

- [Klipper](https://www.klipper3d.org/)
- [KIAUH](https://github.com/dw-0/kiauh) — installation and update utility for Klipper-related services
- [KlipperScreen](https://klipperscreen.readthedocs.io/en/latest/) — touchscreen interface for Klipper printers
- [MainsailOS](https://docs-os.mainsail.xyz/)
- [Moonraker Documentation](https://moonraker.readthedocs.io/en/latest/) — includes integrations for WLED, MQTT, buttons, and more
- [Fluidd](https://docs.fluidd.xyz/) and [FluiddPi](https://github.com/fluidd-core/FluiddPI)
- [RatOS](https://os.ratrig.com/docs/introduction/) — preconfigured Klipper environment for RatRig and selected other printers

## Mainboards

*Configuration examples are listed where available. Always verify the board revision and pin assignments.*

- [Fysetc Cheetah V3](https://github.com/FYSETC/Cheetah_V3.0)
  - [Voron 0 configuration](https://github.com/VoronDesign/Voron-0/blob/Voron0.2r1/Firmware/fysetc-cheetah-v3.0.cfg)
- [Fysetc E4](https://github.com/FYSETC/FYSETC-E4/blob/main/README.md)
- [Fysetc S6](https://github.com/FYSETC/FYSETC-S6/blob/main/README.md)
- [Fysetc Spider](https://github.com/FYSETC/FYSETC-SPIDER/blob/main/README.md)
  - [Rook 180](https://github.com/rolohaun/Rook-180/blob/main/Klipper%20Configs/Fystec%20Spyder/printer.cfg)
  - [Voron 2.4](https://github.com/VoronDesign/Voron-2/blob/Voron2.4/firmware/klipper_configurations/Spider/Voron2_Spider_Config.cfg)
- [BTT Kraken](https://github.com/bigtreetech/BIGTREETECH-Kraken)
  - [Voron Trident](https://github.com/VoronDesign/Voron-Trident/blob/main/Firmware/Kraken/Voron_Trident_Kraken_Config.cfg)
  - [Voron 2.4](https://github.com/VoronDesign/Voron-2/tree/Voron2.4/firmware/klipper_configurations/Kraken)
- [BTT Manta M4P](https://github.com/bigtreetech/docs/blob/master/docs/M4P.md)
  - [Voron 0 configuration](https://github.com/VoronDesign/Voron-0/blob/Voron0.2r1/Firmware/bigtreetech-manta-m4p.cfg)
- [BTT Manta M5P](https://github.com/bigtreetech/docs/blob/master/docs/M5P.md)
- [BTT Manta M8P](https://github.com/bigtreetech/docs/blob/master/docs/M8P.md) — [Amazon](https://amzn.to/42NgtOp)
  - [Voron Trident](https://github.com/VoronDesign/Voron-Trident/blob/main/Firmware/M8P/Trident_M8P_config.cfg)
  - [Voron 2.4](https://github.com/VoronDesign/Voron-2/tree/Voron2.4/firmware/klipper_configurations/M8P)
  - [Salad Fork](https://github.com/PrintersForAnts/Salad_Fork/blob/master/config/printer.cfg-m8p_with_ebb36_sample.cfg)
- [Mellow Fly Gemini V3](https://github.com/Mellow-3D/Fly-Gemini-V3)
  - [Voron 0 configuration](https://github.com/VoronDesign/Voron-0/blob/Voron0.2r1/Firmware/mellow-fly-gemini-v3.cfg)
- [Mellow Fly Super 8](https://github.com/Mellow-3D/Fly-Super8)
  - [VzBot Vz235](https://github.com/VzBoT3D/VzBoT-Vz235/blob/main/Firmware/235AWD-printer.cfg)
  - [VzBot Vz330](https://github.com/VzBoT3D/VzBoT-Vz330/blob/master/Firmware/330AWD-printer.cfg)
  - [VzBot Vz150](https://github.com/VzBoT3D/VzBoT-Vz150/blob/main/Firmware/150AWD-printer.cfg)
- [MKS Monster8](https://github.com/makerbase-mks/MKS-Monster8) — confirm whether the board is V1 or V2
  - [Rook 180](https://github.com/rolohaun/Rook-180/tree/main/Klipper%20Configs/MKS%20Monster%208%20V2)
- [BTT Octopus Pro](https://github.com/bigtreetech/docs/blob/master/docs/Octopus%20Pro.md) — confirm whether the board is V1.0, V1.0.1, or V1.1
- [BTT Octopus MAX EZ](https://github.com/bigtreetech/docs/blob/master/docs/Octopus%20MAX%20EZ.md)
- [BTT Octopus](https://github.com/bigtreetech/docs/blob/master/docs/Octopus.md)
  - [Voron Trident](https://github.com/VoronDesign/Voron-Trident/blob/main/Firmware/Octopus/Trident_Octopus_Config.cfg)
  - [Voron 2.4](https://github.com/VoronDesign/Voron-2/tree/Voron2.4/firmware/klipper_configurations/Octopus)
  - [Micron](https://github.com/PrintersForAnts/Micron/blob/main/Firmware/Config/Octopus-V1-Printer.cfg)
- [BTT SKR V1.3/V1.4](https://github.com/bigtreetech/BIGTREETECH-SKR-V1.3) — [Amazon](https://amzn.to/3JfU5Xi)
  - Voron 2.4 [SKR 1.3](https://github.com/VoronDesign/Voron-2/tree/Voron2.4/firmware/klipper_configurations/SKR_1.3) and [SKR 1.4](https://github.com/VoronDesign/Voron-2/tree/Voron2.4/firmware/klipper_configurations/SKR_1.4)
  - [Voron Legacy SKR V1.3](https://github.com/VoronDesign/Voron-Legacy/blob/main/Firmware/skr_v1.3_config.cfg)
- [BTT SKR 3](https://github.com/bigtreetech/docs/blob/master/docs/SKR%203.md)
  - [Voron 0](https://github.com/VoronDesign/Voron-0/blob/Voron0.2r1/Firmware/bigtreetech-skr-3-ez.cfg)
  - [Rook](https://github.com/rolohaun/Rook/blob/main/Klipper%20Config/SKR%203/printer.cfg)
- [BTT SKR Mini E3](https://github.com/bigtreetech/docs/blob/master/docs/SKR%20MINI%20E3.md) — [Amazon](https://amzn.to/4op2fLO); confirm whether the board is V2 or V3
  - [Voron 0](https://github.com/VoronDesign/Voron-0/blob/Voron0.2r1/Firmware/bigtreetech-skr-mini-e3-v2.0.cfg)
  - [Voron Switchwire](https://github.com/VoronDesign/Voron-Switchwire/blob/master/Firmware/skr_mini_e3_v2_config.cfg)
  - [Rook](https://github.com/rolohaun/Rook/tree/main/Klipper%20Config/SKR%20Mini%20E3%20v2)

## Probes

- [Beacon](https://docs.beacon3d.com/) — [official store](https://beacon3d.com/store/)
- [BLTouch](https://www.antclabs.com/bltouch) — sold officially through [Amazon](https://amzn.to/3vC5ZDW) and eBay
- [BTT Eddy](https://github.com/bigtreetech/Eddy) — eddy-current probe
- [Cartographer](https://docs.cartographer3d.com/)
- [Euclid Probe](https://github.com/nionio6915/Euclid_Probe)
- [Klicky Probe](https://github.com/jlas1/Klicky-Probe) — dockable probe
- [Tap-style probe options](mods.md#tap-style-probes)

## Printer Manuals

- **Fysetc:** [Prusa MK3S Clone](https://github.com/FYSETC/FYSETC-Prusa-MK3S-clone), [Voron 2](https://github.com/FYSETC/FYSETC-Voron-2), [Voron 0.2 Pro](https://github.com/FYSETC/FYSETC-Voron-0.2-Pro), and [Voron Trident](https://github.com/FYSETC/FYSETC-Voron-Trident/blob/main/README.md)
- **LDO Motors:** [Voron kits](https://docs.ldomotors.com/) and [Milo](https://docs.ldomotors.com/en/milo/milov15)
- **RatRig:** [V-Core 3.1](https://docs.ratrig.com/v-core-3-1/v-core-bom) and [V-Minion](https://docs.ratrig.com/product-details/v-minion-1-0)
- [Rolohaun 3D](https://www.rolohaun3d.ca/3d-printers) — printer manuals, rotation-distance calculator, and Klipper tips
- [Printers for Ants](https://3dprintersforants.com/) — manuals for Voron 0 modifications and smaller Voron-derived printers such as Micron and Salad Fork
- [Prusa Assembly Manuals](https://help.prusa3d.com/category/assembly-manuals_272)
- **Voron Design:** [Voron 0](https://github.com/VoronDesign/Voron-0/raw/Voron0.2r1/Manuals/VORON_V0.2r1_Assembly_Manual.pdf), [Voron 2.4](https://github.com/VoronDesign/Voron-2/raw/Voron2.4/Manual/Assembly_Manual_2.4r2.pdf), and [Voron Trident](https://github.com/VoronDesign/Voron-Trident/raw/main/Manual/Frame_Upgrade_Trident.pdf)

## Printheads

- [Afterburner](https://github.com/VoronDesign/Voron-Afterburner/tree/afterburner) — [assembly manual](https://github.com/VoronDesign/Voron-Afterburner/blob/afterburner/Manual/Afterburner.pdf)
- [Dragon Burner](https://github.com/chirpy2605/voron/tree/main/V0/Dragon_Burner) — supports multiple printers, hotends, and extruders
- [EVA](https://main.eva-3d.page/)
- [RatRig Toolhead](https://docs.ratrig.com/v-core-3-1/ratrig-toolhead-v1-0-upgrade)
- [Voron Stealthburner](https://github.com/VoronDesign/Voron-Stealthburner)
- Vz-Printhead: [printed](https://github.com/VzBoT3D/Vz-Printhead-Printed) and [CNC](https://github.com/VzBoT3D/Vz-Printhead-CNC)
- [XOL Toolhead](https://github.com/Armchair-Heavy-Industries/Xol-Toolhead) — formerly known as the Mantis printhead

## Raspberry Pi

- [Raspberry Pi Documentation](https://www.raspberrypi.com/documentation/) — configuration guides, data sheets, and tutorials
- [GPIO and Pinout Documentation](https://www.raspberrypi.com/documentation/computers/raspberry-pi.html) — GPIO can be used with Klipper
- **Stock and retailers:** [RPi Locator](https://rpilocator.com/), [Micro Center](https://www.microcenter.com/search/search_results.aspx?Ntk=all&sortby=match&N=4294910344+4294819333+4294818256&myStore=true), and [Amazon](https://amzn.to/4cujmH0)

### Alternatives

- [BTT Pi](https://github.com/bigtreetech/BTT-Pi) — [Amazon](https://amzn.to/47erpG7)
- [Orange Pi](https://amzn.to/3TK4X0S) — available in many hardware variants

### Helpful Programs

- [balenaEtcher](https://etcher.balena.io/) — flash operating-system images to USB drives and SD cards
- [Chrome Secure Shell](https://chromewebstore.google.com/detail/secure-shell/iodihamcpbpeioajjeobimgagajmlibd) — SSH client for Chrome
- [FileZilla](https://filezilla-project.org/) — transfer files to and from networked devices
- [FormatUSB](https://formatusb.com/) — format USB drives and SD cards
- [Notepad++](https://notepad-plus-plus.org/) — text editor with syntax highlighting and plugins
- [Raspberry Pi Imager](https://www.raspberrypi.com/software/) — create Raspberry Pi boot media
- [PuTTY](https://www.putty.org/) — SSH client
- [Visual Studio Code](https://code.visualstudio.com/) — editor with remote SSH support

## Slicers

- Cura
- PrusaSlicer
- OrcaSlicer
- Bambu Studio
- Slic3r

## Toolhead Boards

- [Esoterical's CAN Bus Guide](https://canbus.esoterical.online/) — clear CAN bus explanation and setup examples
- [BTT EBB SB2209 CAN RP2040](https://github.com/bigtreetech/docs/blob/master/docs/EBB%202209%20CAN%20RP2040.md) — [Amazon](https://amzn.to/3Q1HCa3) and [sample configuration](https://github.com/bigtreetech/EBB/blob/master/EBB%20SB2209%20CAN%20(RP2040)/sample-bigtreetech-ebb-sb-rp2040-canbus-v1.0.cfg)
- [BTT EBB SB2240/SB2209 CAN](https://github.com/bigtreetech/docs/blob/master/docs/EBB%202240%202209%20CAN.md) — [Amazon](https://amzn.to/3vB6BJZ) and [sample configuration](https://github.com/bigtreetech/EBB/blob/master/EBB%20SB2240_2209%20CAN/sample-bigtreetech-ebb-sb-canbus-v1.0.cfg)
- [BTT EBB36 CAN](https://github.com/bigtreetech/docs/blob/master/docs/EBB%2036%20CAN.md) — [Amazon](https://amzn.to/3TCk8Ji); configurations for [V1.0](https://github.com/bigtreetech/EBB/blob/master/EBB%20CAN%20V1.0%20(STM32F072)/sample-bigtreetech-ebb-canbus-v1.0.cfg), [V1.1](https://github.com/bigtreetech/EBB/blob/master/EBB%20CAN%20V1.1%20(STM32G0B1)/sample-bigtreetech-ebb-canbus-v1.1.cfg), and [V1.2](https://github.com/bigtreetech/EBB/blob/master/EBB%20CAN%20V1.1%20(STM32G0B1)/sample-bigtreetech-ebb-canbus-v1.2.cfg)
- [BTT EBB42 CAN](https://github.com/bigtreetech/docs/blob/master/docs/EBB%2042%20CAN.md) — [Amazon](https://amzn.to/3PFFAvY); configurations for [V1.0](https://github.com/bigtreetech/EBB/blob/master/EBB%20CAN%20V1.0%20(STM32F072)/sample-bigtreetech-ebb-canbus-v1.0.cfg), [V1.1](https://github.com/bigtreetech/EBB/blob/master/EBB%20CAN%20V1.1%20(STM32G0B1)/sample-bigtreetech-ebb-canbus-v1.1.cfg), and [V1.2](https://github.com/bigtreetech/EBB/blob/master/EBB%20CAN%20V1.1%20(STM32G0B1)/sample-bigtreetech-ebb-canbus-v1.2.cfg)
- [BTT U2C](https://github.com/bigtreetech/docs/blob/master/docs/U2C.md) — [Amazon](https://amzn.to/3TxWRbr)
- [Mellow Fly SB2040](https://github.com/Mellow-3D/Fly-SB2040)
- [Mellow Fly CAN Toolboards](https://github.com/Mellow-3D/Klipper-CAN-Toolboards)
