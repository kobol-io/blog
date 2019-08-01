---
layout:     post
title:      "New major Release, Armbian 5.91, It's time to Upgrade !"
date:       2019-08-01 01:00:00
author:     "Kobol Team"
header-img: "img/058/sw-progress-bg.jpg"
---

The Kobol Team has joined the [Armbian](https://www.armbian.com/) team to be the official maintainer of Armbian build for *mvebu* SoC family. We have worked hard together to come with this new major release  **Amrbian 5.91** which introduces **Debian 10 Buster** and major Kernel and U-Boot upgrade for Helios4.

![Armbian Update](/img/058/armbian-update.jpg)

### Here are the key changes :

Armbian **Next** for Helios4

- U-Boot : Mainline 2019.04
- Linux Kernel : Mainline 4.19.y
- OS : Debian 10 Buster or Ubuntu Bionic

Armbian **Default** for Helios4

- U-Boot : 2018.11
- Linux Kernel : Mainline 4.14.y
- OS : Debian 9 Stretch

You will find the new images on our Wiki Download [page](https://wiki.kobol.io/download/#latest-os-images) or on Armbian Download [page](https://dl.armbian.com/helios4/).

You can check latest release changes on Armbian changelog [page](https://docs.armbian.com/Release_Changelog/).

We have already updated the different sections of the [wiki](https://wiki.kobol.io) to be aligned with this new release.

### Important Note

While **we strongly recommend users who start a fresh install to choose the Armbian Next with Debian 10 Buster**, we are still offering Armbian Default with Debian 9 Stretch because OMV 5 (OpenMediaVault) for Debian 10 Buster is still in Beta, therefore **users who want to use OMV will need to stick to Debian 9 Stretch with OMV 4 for now**.

### Armbian Upgrade

For users with an already running system, **it's time to upgrade your Helios4 with the latest Armbian packages.**


**To upgrade your system use the following commands :**

```
$> sudo apt-get update

$> sudo apt-get upgrade
```

You will need to reboot your system for the new Kernel to be loaded.

```
$> sudo reboot
```

You can check with the following 2 commands that your system has been updated to the latest Armbian release :

On Debian Default

```
$> uname -r
4.14.134-mvebu

$> cat /etc/armbian-release | grep VERSION
VERSION=5.91
```

On Debian Next

```
$> uname -r
4.19.62-mvebu

$> cat /etc/armbian-release | grep VERSION
VERSION=5.91
```

---

If you want to update your U-Boot version on SDcard, you need to use **nand-sata-install** tool.

***Note :** New SDcard U-Boot now stores the Environment variables on /boot/boot.env. For users that had modified their environment variables, you will need to configure again and save those variables in u-boot after updating.*

```
$> sudo nand-sata-install
```

![U-Boot Update](/img/058/nand-sata-install.png)

Choose option **5 "Install/Update the bootloader on SD/eMMC"**.

You will also need to reboot your system for the new U-Boot to be used.

```
$> sudo reboot
```

For users using SPI NOR Flash to store U-Boot, refer to [this section](https://wiki.kobol.io/spi/#under-armbian) of the wiki SPI page to update your U-Boot.

### From Stretch to Buster

The recommend approach is to do a fresh install with Debian Buster image, however you could try to upgrade your existing Debian Stretch to Debian Buster. But note that depending of your setup, there are chances you will break some package dependencies and you will be missing some tweaks present in the latest Armbian build. Here the sequence of commands to perform such system upgrade.

**DISCLAIMER : Upgrading from Debian Stretch to Buster is not always a reliable process. No guarantee the following will not break your system !!!**

```
$> sudo apt-get update && apt-get upgrade -y
$> sudo apt-get dist-upgrade -y

$> sudo sed -i 's/stretch/buster/g' /etc/apt/sources.list    
$> sudo sed -i 's/Stretch/buster/g' /etc/apt/sources.list.d/armbian.list

$> sudo apt-get update && apt-get upgrade -y
$> sudo apt-get dist-upgrade -y

$> sudo reboot
```

### Reminder : Debian Jessie is End-Of-Life !

For users still running Debian Jessie on their Helios4, take note that it is End-Of-Life. No more support is provided for Debian Jessie and/or Kernel 4.4 builds. **You must re-install your system with the [latest Armbian build](https://wiki.kobol.io/download/#latest-os-images).**
