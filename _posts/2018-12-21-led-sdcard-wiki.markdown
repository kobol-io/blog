---
layout:     post
title:      "About Helios4 LEDs and SD Card UHS mode !"
date:       2018-12-21 01:00:00
author:     "Kobol Team"
header-img: "img/045/led-sdcard-bg.png"
---

We have updated our wiki with 2 new tutorials :

- [How to use on-board LEDs](https://wiki.kobol.io/led/){: .underline }
- [How to enable SD Card UHS](https://wiki.kobol.io/sdcard/){: .underline }

### How to use on-board LEDs

The Helios4 board has a collection of LEDs used to report activity, like System heartbeat or Disk activities.

![LED Location](/img/045/led_location.png)

While most LEDs are already pre-configured, the fault LED remains unconfigured in previous **Armbian** builds. The tutorial will explain for example how to setup your system to report RAID errors on the fault LED. [Find out more...](https://wiki.kobol.io/led/)

### How to enable SD Card UHS

The Helios4 SoC (Armada 388) SDIO controller supports up to UHS-I speed mode. However, it is not compatible with all cards even though the SD cards are declared as UHS-I capable.

![UHS compatibility](/img/045/uhs_compatibility.png)

To keep it compatible with most of cards, Helios4 device tree only defines by default Normal Speed mode. If you still want to test the UHS mode, the tutorial will run you through all the necessary steps. [Find out more...](https://wiki.kobol.io/sdcard/)
