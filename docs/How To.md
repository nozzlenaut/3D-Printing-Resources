---
title: How-To Guides
---

# How-To Guides

A collection of practical setup, configuration, and integration references. Read the documentation for your exact board and printer revision before copying configuration examples.

## Building

- [Voron Sourcing and Buying FAQ](https://docs.vorondesign.com/sourcing_faq.html) — useful guidance for buying components used in printer builds
- [Voron Mechanical Assembly Tips](https://docs.vorondesign.com/build/mechanical/) — practical assembly advice and maintenance considerations that apply to many printers

## Software and Remote Access

- [KIAUH](https://github.com/dw-0/kiauh) — simplified installation and management of common Klipper services
- [SSH Basics and Setup](https://github.com/VoronDesign/Voron-Documentation/blob/main/build/software/ssh.md) — remote terminal access  
  *Tip: Choose a memorable hostname when flashing the SD card. A hostname such as `voron` may let you connect with `voron.local` without looking up the IP address.*
- [Boot a Raspberry Pi from an SSD](https://www.makeuseof.com/how-to-boot-raspberry-pi-ssd-permanent-storage/) — includes guidance for moving an existing SD-card installation
- [KlipperScreen Installation](https://klipperscreen.github.io/KlipperScreen/Installation/) — can also be installed through KIAUH; includes Android setup information
- [Raspberry Pi Camera Documentation](https://www.raspberrypi.com/documentation/accessories/camera.html)
- [Configure a Webcam in Fluidd](https://docs.fluidd.xyz/features/cameras) — supports many USB webcams and may require [Crowsnest](https://docs.fluidd.xyz/features/cameras#crowsnest-support)
- [Configure a Webcam in Mainsail](https://docs.mainsail.xyz/overview/settings/webcams) — supports many USB webcams and may require [Crowsnest](https://crowsnest.mainsail.xyz/)

## Tuning

- [USB Input Shaper Setup](https://www.youtube.com/watch?v=W_VHbT_tsZw&t=584s)
- [Sensorless Homing](https://github.com/VoronDesign/Voron-Documentation/blob/main/community/howto/clee/sensorless_xy_homing.md)
- [More tuning resources](Tuning.md)

## Klipper and Moonraker Integrations

- [Moonraker Configuration](https://moonraker.readthedocs.io/en/latest/configuration/) — integrations for services and connected devices
- [Klipper-Backup](https://staubgeborener.github.io/klipper-backup/) — back up printer configuration to a repository and restore a known-good state
- [KAMP](https://github.com/kyleisah/Klipper-Adaptive-Meshing-Purging) — adaptive bed meshing and purging focused on the area being printed
- [Install Klipper on an Ender 3](https://www.obico.io/blog/install-klipper-ender-3/) — printer-specific example with concepts that apply to many conversions
- Use [WLED](https://kno.wled.ge/) with Klipper — [local tutorial](https://github.com/nozzlenaut/3D-Printing-Resources/blob/main/misc%20pages/WLED.md) and [Gliptopolis' guide](https://github.com/Gliptopolis/WLED_Klipper)
- [Moonraker Timelapse](https://github.com/mainsail-crew/moonraker-timelapse) — create print timelapses with a connected camera
- [Use Raspberry Pi GPIO with Klipper](https://www.klipper3d.org/RPi_microcontroller.html)

## YouTube Channels

- [CNC Kitchen](https://www.youtube.com/@CNCKitchen) — testing, engineering, and 3D-printing research
- [Made with Layers](https://www.youtube.com/@MadeWithLayers) — build streams, comparisons, and testing
- [Makers Muse](https://www.youtube.com/@MakersMuse) — general 3D-printing applications and tutorials
- [Mandic Really](https://www.youtube.com/@MandicReally) — modifications, builds, and practical printed projects
- [Maple Leaf Makers](https://www.youtube.com/@MapleLeafMakers/featured) — concise modification and build videos
- [ModBot](https://www.youtube.com/@ModBotArmy) — modifications, how-to videos, and reviews
- [Nero3D](https://www.youtube.com/@CanuckCreator) — modifications, reviews, tutorials, and build streams
- [Steve Builds](https://www.youtube.com/@SteveBuilds) — printer build and modification streams
- [Teaching Tech](https://www.youtube.com/@TeachingTech) — build logs and tutorials for a wide range of skill levels
