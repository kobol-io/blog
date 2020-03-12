---
layout:     post
title:      "New major Armbian Release for Helios4 !"
date:       2020-03-13 01:00:00
author:     "Kobol Team"
header-img: "img/064/sw-progress-bg.jpg"
---

The [Armbian](https://www.armbian.com/) team has done again an awesome work with this new major release [version 20.02](https://github.com/armbian/build/releases/tag/v20.02).
Beside changes listed on [Changelog](https://docs.armbian.com/Release_Changelog/), this version also includes the following improvements which concern directly Helios4 :
- Enable CH34x USB Serial kernel module
- Fix missing nftables that causing iptables and docker failed to run on Debian Buster
- Fix cpufreq (dynamic frequency scaling) for kernel 4.19


**So it's time to update your Helios4 with the latest Armbian packages.**

![Armbian Update](/img/064/armbian-update.jpg)

## Upgrade Procedure

Since November 2019, Armbian changed the version and branch naming. Version naming changed from incremental system (e.g 5.91) to something similar to Ubuntu versioning which consists of Year.Month of the release (e.g 19.11).

As for branch name, the following renaming convention was made :

- *DEFAULT* becomes *LEGACY*
- *NEXT* becomes *CURRENT*

Due to this changes, anyone running a 5.xx Armbian version will need to do additional steps to switch to newer Armbian version.

**To upgrade your 5.xx Armbian use the following commands :**

```
sudo apt-get update
sudo apt-get -y upgrade
sudo armbian-config
```

![armbian-config main menu](/img/064/armbian-config_main.png)

Select System > Other, to switch to other kernel
![armbian-config system menu](/img/064/armbian-config_system.png)

Confirm the action
![armbian-config confirmation](/img/064/armbian-config_other_kernel_confirmation.png)

And after some processes, you will be presented by list of kernels.

For user on *DEFAULT* branch, please select latest **linux-image-legacy-mvebu** as shown on screenshot below

![armbian-config list of legacy kernel](/img/064/armbian-config_other_kernel_list_legacy.png)

For user on *NEXT* branch, please select latest **linux-image-current-mvebu** as shown on screenshot below

![armbian-config list of current kernel](/img/064/armbian-config_other_kernel_list_next.png)

The system will install the new kernel and automatically reboot.

Confirm the kernel installed correctly and Armbian changed to new branch CURRENT by executing,

```
uname -a
grep "BRANCH" /etc/armbian-release
grep "VERSION" /etc/armbian-release
```

on *DEFAULT* system upgraded to *LEGACY*, it should output:
```
$> uname -a
Linux helios4 4.14.171-mvebu #22 SMP Mon Feb 17 03:15:40 CET 2020 armv7l GNU/Linux

$> grep "BRANCH" /etc/armbian-release
BRANCH=legacy

$> grep "VERSION" /etc/armbian-release
VERSION=20.02.4
```

on *NEXT* system upgraded to *CURRENT*, it should output:
```
$> uname -a
Linux helios4 4.19.104-mvebu #20.02.1 SMP Mon Feb 17 03:22:46 CET 2020 armv7l GNU/Linux

$> grep "BRANCH" /etc/armbian-release
BRANCH=current

$> grep "VERSION" /etc/armbian-release
VERSION=20.02.4
```

After those additional steps done, you won't need to run those steps again to update your system. Just run the usual commands to update your system:

```
sudo apt-get update
sudo apt-get upgrade
```
