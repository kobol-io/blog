---
layout:     post
title:      "Helios64 Software Issue Report !"
date:       2020-10-27 01:00:00
author:     "Kobol Team"
header-img: "img/072/software-support-bg.png"
---

# Do NOT Upgrade to Armbian 20.08.13

We have received reports of instability issues through email and forum with the latest Armbian image we published (20.08.13). We are still investigating the root cause and managed to reproduce the kernel crash on some of our boards. We advise user to **NOT** install or upgrade to **Armbian 20.08.13** which contain **Linux Kernel 5.8.16** until further notice.

You can download **Armbian 20.08.10** which is known stable from following links

Filename | Link
---------|---------
**Armbian_20.08.10_Helios64_buster_current_5.8.14.img.xz**<br>Build date : 13/10/2020<br>Size : 443 MB|[Download](https://archive.armbian.com/helios64/archive/Armbian_20.08.10_Helios64_buster_current_5.8.14.img.xz)
**Armbian_20.08.10_Helios64_focal_current_5.8.14.img.xz**<br>Build date : 13/10/2020<br>Size : 334 MB|[Download](https://archive.armbian.com/helios64/archive/Armbian_20.08.10_Helios64_focal_current_5.8.14.img.xz)

You can prevent Board Support Package (bootloader/kernel/device tree) upgrade by following instruction on next [section](#prevent-bsp-update).


## Revert back to Linux Kernel 5.8.14

To downgrade to LK 5.8.14 you can use *armbian-config*

```
sudo armbian-config
```

- Select System

![Armbian config main](/img/072/revert_01_main.png)

- Select Other

![Armbian config main](/img/072/revert_02_system.png)

- Confirm that you understand the risk and want to switch kernel.

![Armbian config main](/img/072/revert_03_agreement.png)

- Select Kernel, **linux-image-current-rockchip64=20.08.10  5.8.14-rockchip64**

![Armbian config main](/img/072/revert_04_kernel_list.png)

System will automatically reboot.

- Verify you are running kernel 5.8.14 by executing

  `uname -r`

  You should get `5.8.14-rockchip64`


## Prevent BSP update

After kernel 5.8.14 running (either by downgrading or use older image), you need to frezee/hold the BSP package so it will not be updated in future. You can use *armbian-config* for this purpose.

```
sudo armbian-config
```

- Select System

![Armbian config main](/img/072/bsp_hold_01_main.png)

- Select Freeze

![Armbian freeze menu](/img/072/bsp_hold_02_system.png)

- Confirm to freeze the firmware updates

![Armbian freeze confirmation](/img/072/bsp_hold_03_freeze.png)

- After the packages frozen, the background color will be changed to red.

![Armbian frozen](/img/072/bsp_hold_04_warning_frozen.png)

- Exit Armbian Configuration Utility


You will see this message when doing update while the BSP frozen.
```
The following packages have been kept back:
  armbian-firmware linux-dtb-current-rockchip64 linux-image-current-rockchip64
  linux-u-boot-helios64-current
```

## Armbian Support Forum

If you are facing an issue, you can go on the **Armbian** forum to ask for some help. There is a thread dedicated to [Helios64 support](https://forum.armbian.com/topic/15431-helios64-support/).
