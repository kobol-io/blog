---
layout:     post
title:      "Helios4 Software Integration Progress - Update 1 !"
date:       2017-09-04 00:00:00
author:     "Kobol Team"
header-img: "img/007/sw-progress-bg.jpg"
---

<p>
All the current efforts are on having a first baseline with full hardware support. <b>We are almost there</b>, with just the PWM Fan driver that is still a work-in-progress and some other pending tweaks that are waiting we get some 2GB ECC SoM samples.
<p>

<p>
You can follow the development efforts directly on our <b><a href="https://github.com/helios-4" target="_blank">Helios4 Official Github</a></b>.
</p>

<p>
Here are the main projects that you should follow :
<ul>
<li>
<b><a href="https://github.com/helios-4/u-boot-marvell" target="_blank">u-boot-marvell</a></b> Helios4 custom u-boot<br>
(active branch : u-boot-2013.01-15t1-helios4)
</li>
<li>
<b><a href="https://github.com/helios-4/linux-marvell" target="_blank">linux-marvell</a></b> Helios4 custom kernel 4.4<br>
(active branch : linux-marvell-4.4)
</li>
<li>
<b><a href="https://github.com/helios-4/build" target="_blank">armbian/build</a></b> Helios4 integration in Armbian<br>
For now only default target : Debian 8 Jessie<br>
(active branch : helios4)
</li>
</ul>
</p>

<p>
So we should be very soon ready to send a pull request in order to add officially the Helios4 support in the <a href="https://www.armbian.com">Armbian project</a>. Once it will be merge in their master branch then the first images for Helios4 will start to get built and should be available through the Armbian portal.
</p>

<p>
Once the baseline is complete, we will shift the effort to the following U-Boot, Kernel and OS versions :
<ul>
<li>u-boot-2017.03-armada-17.08</li>
<li>mainline kernel 4.13 or LTS kernel 4.9</li>
<li>Debian 9 Strech</li>
</ul>
</p>

<p>
Now in regards to NAS related application, our main focus will be to provide an Armbian image that includes <a href="https://www.openmediavault.org/">OpenMediaVault</a>. This will be actually very straight forward thanks to the existing Armbian customize-image script that already includes a routine to built-in OMV.
</p>

<p>
<img src="{{ site.baseurl }}/img/007/helios-4-github.png" alt="Helios4 Github">
</p>
