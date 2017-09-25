---
layout:     post
title:      "Helios4 Software Integration Progress - Update 1 !"
date:       2017-09-04 00:00:00
author:     "Kobol Team"
header-img: "img/007/sw-progress-bg.jpg"
---

All the current efforts are on having a first baseline with full hardware support. **We are almost there**, with just the PWM Fan driver that is still a work-in-progress and some other pending tweaks that are waiting we get some 2GB ECC SoM samples.

You can follow the development efforts directly on our **[Helios4 Official Github](https://github.com/helios-4)**.

Here are the main projects that you should follow :

*   **[u-boot-marvell](https://github.com/helios-4/u-boot-marvell)** Helios4 custom u-boot  
    (active branch : u-boot-2013.01-15t1-helios4)
*   **[linux-marvell](https://github.com/helios-4/linux-marvell)** Helios4 custom kernel 4.4  
    (active branch : linux-marvell-4.4)
*   **[armbian/build](https://github.com/helios-4/build)** Helios4 integration in Armbian  
    For now only default target : Debian 8 Jessie  
    (active branch : helios4)

So we should be very soon ready to send a pull request in order to add officially the Helios4 support in the [Armbian project](https://www.armbian.com). Once it will be merge in their master branch then the first images for Helios4 will start to get built and should be available through the Armbian portal.

Once the baseline is complete, we will shift the effort to the following U-Boot, Kernel and OS versions :

*   u-boot-2017.03-armada-17.08
*   mainline kernel 4.13 or LTS kernel 4.9
*   Debian 9 Strech

Now in regards to NAS related application, our main focus will be to provide an Armbian image that includes [OpenMediaVault](https://www.openmediavault.org/). This will be actually very straight forward thanks to the existing Armbian customize-image script that already includes a routine to built-in OMV.

![Helios4 Github]({{ site.baseurl }}/img/007/helios-4-github.png)
