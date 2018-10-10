---
layout:     post
title:      "How to use GPIO and SPI NOR Flash on Helios4 !"
date:       2018-10-10 01:00:00
author:     "Kobol Team"
header-img: "img/037/spi-gpio-bg.png"
---

We have updated our wiki with 2 new tutorials :

- [How to use GPIO](https://wiki.kobol.io/gpio/){: .underline }
- [How to use SPI](https://wiki.kobol.io/spi/){: .underline }


### How to use GPIO

Helios4 provides **12 GPIOs** on header J12 which can be used for user application.

![J12 Header](/img/037/gpio_pinout_j12.png)

The tutorial will explain you how to use to the GPIOs and how to understand the mapping between physical header and the operating system.

[Find out more...](https://wiki.kobol.io/gpio/)

### How to use SPI

The A388 System-On-Module used by Helios4 provides an **32 Mbit SPI NOR Flash** which can be used as a reliable boot device to host U-Boot bootloader.

![Boot Mode](/img/037/dipswitch_boot_spinor.png) SW1 Dipswitch

This will offer you the option to host your Root FileSystem on an USB3.0 storage device without the need to rely anymore on a microSD card.

We have work with the [Armbian](https://www.armbian.com/) team to add the SPI install support for Helios4 in latest Armbian release. This way you can use the *nand-sata-install* utility to easily take care of setting up the SPI Flash and moving your RootFS to a USB device.

If you intend to use SPI, you should upgrade your system to latest Armbian packages with the following command.

    sudo apt-get update && sudo apt-get upgrade

Also new Armbian image are [available](https://wiki.kobol.io/download/) for fresh install.

[Find out more...](https://wiki.kobol.io/spi/)
