---
layout:     post
title:      "Helios4 Latest Image Releases !"
date:       2018-02-05 00:01:00
author:     "Kobol Team"
header-img: "img/020/sw-progress-bg.jpg"
---

## Latest image builds

One of the main highlight of these new builds is the improvement of fan management.
1. Now pwm-fan driver works in Kernel 4.4.*
2. Fans and sensors mapping has been fixed ensuring fancontrol always works.

Filename | Download
---------|----------
**Helios4_Debian_Stretch_4.14.17.img.xz**<br>Debian 9 Stretch (Kernel 4.14.17)<br>Build date : 05/02/2018<br>Size :242 MB|[link](https://cdn.kobol.io/files/Helios4_Debian_Stretch_4.14.17.img.xz)
**Helios4_Debian_Jessie_4.4.112.img.xz**<br>Debian 8 Jessie (Kernel 4.4.112)<br>Build date : 05/02/2018<br>Size :210 MB|[link](https://cdn.kobol.io/files/Helios4_Debian_Jessie_4.4.112.img.xz)
**Helios4_Debian_Jessie_4.4.112-OMV_3.0.96.img.xz**<br>Debian 8 Jessie (Kernel 4.4.112) with OMV 3.0.96<br>Build date : 05/02/2018<br>Size : 272 MB|[link](https://cdn.kobol.io/files/Helios4_Debian_Jessie_4.4.110-OMV_3.0.96.img.xz)


## Upgrade your system

If you want to update an existing Helios4 setup and fix the fan control issues, open a shell on your Helios4 and follow the below steps :

**1. Update kernel**

```
$> sudo apt-get update
$> sudo apt-get dist-upgrade
```

**2. Install Helios4 udev rules**

Create a file */etc/udev/rules.d/90-helios4-hwmon.rules* and copy the following

```
# Helios4 persistent hwmon

ACTION=="remove", GOTO="helios4_hwmon_end"

#
KERNELS=="j10-pwm", SUBSYSTEMS=="platform", ENV{_HELIOS4_FAN_}="j10", ENV{_IS_HELIOS4_FAN_}="1", ENV{IS_HELIOS4_HWMON}="1"
KERNELS=="j17-pwm", SUBSYSTEMS=="platform", ENV{_HELIOS4_FAN_}="j17", ENV{_IS_HELIOS4_FAN_}="1", ENV{IS_HELIOS4_HWMON}="1"
KERNELS=="0-004c", SUBSYSTEMS=="i2c", DRIVERS=="lm75", ENV{IS_HELIOS4_HWMON}="1"

SUBSYSTEM!="hwmon", GOTO="helios4_hwmon_end"

ENV{HWMON_PATH}="/sys%p"
#
ATTR{name}=="f1072004mdiomii00", ENV{IS_HELIOS4_HWMON}="1", ENV{HELIOS4_SYMLINK}="/dev/thermal-eth"
ATTR{name}=="armada_thermal", ENV{IS_HELIOS4_HWMON}="1", ENV{HELIOS4_SYMLINK}="/dev/thermal-cpu"
#
ENV{IS_HELIOS4_HWMON}=="1", ATTR{name}=="lm75", ENV{HELIOS4_SYMLINK}="/dev/thermal-board"
ENV{_IS_HELIOS4_FAN_}=="1", ENV{HELIOS4_SYMLINK}="/dev/fan-$env{_HELIOS4_FAN_}"

#
ENV{IS_HELIOS4_HWMON}=="1", RUN+="/bin/ln -sf $env{HWMON_PATH} $env{HELIOS4_SYMLINK}"

LABEL="helios4_hwmon_end"
```
**3. Update fancontrol config**

* For Kernel 4.4

Edit file */etc/fancontrol* and replace the content by the following

```
# Helios4 PWM Fan Control Configuration
# Temp source : /dev/thermal-board
INTERVAL=10
FCTEMPS=/dev/fan-j10/pwm1=/dev/thermal-board/temp1_input /dev/fan-j17/pwm1=/dev/thermal-board/temp1_input
MINTEMP=/dev/fan-j10/pwm1=45 /dev/fan-j17/pwm1=45
MAXTEMP=/dev/fan-j10/pwm1=70 /dev/fan-j17/pwm1=70
MINSTART=/dev/fan-j10/pwm1=50 /dev/fan-j17/pwm1=50
MINSTOP=/dev/fan-j10/pwm1=50 /dev/fan-j17/pwm1=50
MINPWM=/dev/fan-j10/pwm1=50 /dev/fan-j17/pwm1=50
```

* For Kernel 4.14.*

Edit file */etc/fancontrol* and replace the content by the following

```
# Helios4 PWM Fan Control Configuration
# Temp source : /dev/thermal-cpu
INTERVAL=10
FCTEMPS=/dev/fan-j10/pwm1=/dev/thermal-cpu/temp1_input /dev/fan-j17/pwm1=/dev/thermal-cpu/temp1_input
MINTEMP=/dev/fan-j10/pwm1=55 /dev/fan-j17/pwm1=55
MAXTEMP=/dev/fan-j10/pwm1=95 /dev/fan-j17/pwm1=95
MINSTART=/dev/fan-j10/pwm1=50 /dev/fan-j17/pwm1=50
MINSTOP=/dev/fan-j10/pwm1=50 /dev/fan-j17/pwm1=50
MINPWM=/dev/fan-j10/pwm1=50 /dev/fan-j17/pwm1=50
```

**4. Restart**

```
$> reboot
```

## Known Issues

#### All Kernels

* SDcard High Speed timing have compatibility issue with some brands.
  Temporary workaround : Disable UHS option/support.

* During SATA heavy load, accessing SPI NOR Flash will generate ATA errors.
  Temporary workaround : Disable SPI NOR flash.

#### Legacy Kernel (4.14)
* DVFS doesn't report correct CPU freq range (666 - 1332Mhz instead of 800-1600MHz).

![Debian](/img/020/debian.png)

**You can find all our image builds and support details on [Helios4 Wiki Download page](https://wiki.kobol.io/download) and install instructions [here](https://wiki.kobol.io/install).**
