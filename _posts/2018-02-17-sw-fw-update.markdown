---
layout:     post
title:      "Helios4 Latest Image Releases !"
date:       2018-02-17 00:01:00
author:     "Kobol Team"
header-img: "img/021/sw-progress-bg.jpg"
---

## Latest image builds

These new builds address the following :
- Enable HDD Activity LED (this was disabled by mistake in previous build)
- Fancontrol improvement :
    - fix 'too many arguments' error messages
    - set pwm to minimum speed when shutting down system
- OMV3 build is now based on kernel 4.14 which provides better hardware support


Filename | Download
---------|----------
**Helios4_Debian_Stretch_4.14.20.img.xz**<br>Debian 9 Stretch (Kernel 4.14.20)<br>Build date : 17/02/2018<br>Size : 229 MB|[Link](https://cdn.kobol.io/files/Helios4_Debian_Stretch_4.14.20.img.xz)
**Helios4_Debian_Jessie_4.14.20-OMV_3.0.97.img.xz**<br>Debian 8 Jessie (Kernel 4.14.20) with OMV 3.0.97<br>Build date : 17/02/2018<br>Size : 259 MB|[Link](https://cdn.kobol.io/files/Helios4_Debian_Jessie_4.14.20-OMV_3.0.97.img.xz)


**You can find all our image builds and support details on [Helios4 Wiki Download page](https://wiki.kobol.io/download) and install instructions [here](https://wiki.kobol.io/install).**

## Apply Fancontrol patch manually

If you want to fix fancontrol on an existing setup, open a shell on your Helios4 and follow the below steps :

**1. Download patch**

```
$> wget https://raw.githubusercontent.com/helios-4/build/helios4/packages/bsp/helios4/fancontrol.patch
```

**2. Apply patch**

```
$> sudo patch -b /usr/sbin/fancontrol -i fancontrol.patch
```

**3. Restart fancontrol**

```
$> sudo systemctl restart fancontrol.service
```

![Debian](/img/020/debian.png)
