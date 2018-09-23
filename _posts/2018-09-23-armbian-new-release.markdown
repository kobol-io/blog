---
layout:     post
title:      "New major Armbian Release, It's time to Upgrade !"
date:       2018-09-23 01:00:00
author:     "Kobol Team"
header-img: "img/035/sw-progress-bg.jpg"
---

The [Armbian](https://www.armbian.com/) team has worked hard to come around this new major release : [version 5.60](https://docs.armbian.com/Release_Changelog/)

**So it's time to update your Helios4 with the latest Armbian packages.**

![Armbian Update](/img/035/armbian-update.jpg)

Beside providing some improvements and latest Kernel 4.14, the new release also includes a fix for Helios4 U-Boot that solves the Ethernet interface not always initializing properly at startup (issue explained [here](https://forum.armbian.com/topic/6033-helios4-support/?do=findComment&comment=60776)).

**To upgrade your system use the following commands :**

```
$> sudo apt-get update

$> sudo apt-get dist-upgrade
```

You will need to reboot your system for the new U-Boot and Kernel to be loaded.

```
$> sudo reboot
```

 You can check with the following 2 commands that your system has been updated to the latest Armbian release :

```
$> uname -a
Linux helios4 4.14.70-mvebu #266 SMP Wed Sep 19 10:35:09 CEST 2018 armv7l GNU/Linux

$> cat /etc/armbian-release | grep VERSION
VERSION=5.60
```

----

### Reminder : Debian Jessie is End-Of-Life !

For people still running Debian Jessie on their Helios4, take note that it is End-Of-Life. No more support is provided for Debian Jessie and/or Kernel 4.4 builds. **We strongly recommend you to re-install your system with the [latest Armbian build](https://wiki.kobol.io/download/#latest-os-images).**

Instead of the recommended fresh install, you could try to upgrade your existing Debian Jessie system to Debian Stretch. But depending of your setup it might break some package dependencies and you will be missing some tweaks present in the latest Armbian build. Here the sequence of commands to perform such system upgrade.

**DISCLAIMER : No guaranty the following will not break your system !!!**

```
$> apt-get update && apt-get upgrade -y
$> apt-get dist-upgrade -y

$> armbian-config
System > Switch > Switch kernel to 'Next' version.

$> reboot

$> uname -a
Check Kernel version is now 4.14

$> sed -i 's/jessie/stretch/g' /etc/apt/sources.list    
$> sed -i 's/jessie/stretch/g' /etc/apt/sources.list.d/armbian.list

$> apt-get update && apt-get upgrade -y
$> apt-get dist-upgrade -y

$> reboot
```
