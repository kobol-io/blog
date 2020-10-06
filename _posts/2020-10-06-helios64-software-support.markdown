---
layout:     post
title:      "Helios64 Software News 1!"
date:       2020-10-06 01:00:00
author:     "Kobol Team"
header-img: "img/071/software-support-bg.png"
---

# New Armbian Images Available

We have just published new Armbian images (20.08.8) with some adjustments that should be fixing the instability issues that we have been facing with early image releases. Of course we need your help to test and see if it achieves the expected stability (**Important** : We recommend to do a fresh install).

### Image List

Filename | Link
---------|---------
**Armbian_20.08.8_Helios64_buster_legacy_4.4.213.img.xz**<br>Build date : 05/10/2020<br>Size : 397 MB|[Download](https://dl.armbian.com/helios64/archive/Armbian_20.08.8_Helios64_buster_legacy_4.4.213.img.xz)|
**Armbian_20.08.8_Helios64_buster_current_5.8.13.img.xz**<br>Build date : 05/10/2020<br>Size : 443 MB|[Download](https://dl.armbian.com/helios64/archive/Armbian_20.08.8_Helios64_buster_current_5.8.13.img.xz)
**Armbian_20.08.8_Helios64_focal_current_5.8.13.img.xz**<br>Build date : 05/10/2020<br>Size : 330 MB|[Download](https://dl.armbian.com/helios64/archive/Armbian_20.08.8_Helios64_focal_current_5.8.13.img.xz)

_If download links are broken, you can check directly on Armbian [repo](https://archive.armbian.com/helios64/archive/)._

# Features Support Status

Again these Helios64 images are still a work-in-progress, not all board features are supported yet. You will find below the list of features that are partially or not fully supported yet on both Linux Kernel 4.4 and 5.8.

### Linux Kernel 4.4

| **Feature** | **Support Status**| **Remarks** |
|---------|----------------|---------|
| **Shutdown** | Partial | Fails to shutdown PMIC and triggers crash, HDD already parked |
| **Reboot** | Partial | Similar like shutdown but Watchdog triggers the reboot so it appears successful |
| **Suspend to RAM** | Not Supported | Fails to resume operation after wake up |
| **2.5G Ethernet** | OK | |
| **Main Power/UPS Status** | OK | Status can be read from sysfs |
| **Battery Charging Status** | Not supported | |
| **UPS configuration** | Not Supported  | Need user-space tool to monitor power status and trigger shutdown |
| **USB Type C - Host** | OK | |
| **USB Type C - Gadget** | OK | use g_mass_storage kernel module |
| **USB Type C - DisplayPort** | OK |
| **eMMC Boot** | Not Supported | Bootloader unable to load rootfs from eMMC |
| **SPI Boot** | Not Supported |
| **Recovery key** | Not Supported | System can enter maskrom mode but need special OS image and rkdevelop |

### Linux Kernel 5.8

| **Feature** | **Support Status** | **Remarks** |
|---------|----------------|---------|
| **Shutdown** | OK | |
| **Reboot** | OK | |
| **Suspend to RAM** | Not Supported | USB host controller refuses to enter suspend mode |
| **2.5G Ethernet** | Performance issue | Slightly improved with tx offload disabled |
| **Main Power/UPS Status** | OK | Status can be read from sysfs |
| **Battery Charging Status** | OK | Charging and Full charge can be read from sysfs |
| **UPS configuration** | Not Supported | Need user-space tool to monitor power status and trigger shutdown |
| **USB Type C - Host** | Not Supported | There are some issues with fusb302 driver and USB Host Controller driver |
| **USB Type C - Gadget** | Not Supported | There are some issues with fusb302 driver and USB Controller driver |
| **USB Type C - DisplayPort** | Not Supported | There are some issues with fusb302 driver and DisplayPort alternate driver |
| **eMMC Boot** | Not Supported | Bootloader unable to load rootfs from eMMC |
| **SPI Boot** | Not Supported |
| **Recovery key** | Not Supported | System can enter maskrom mode but need special OS image and rkdevelop  |
