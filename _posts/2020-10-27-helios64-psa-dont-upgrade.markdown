---
layout:     post
title:      "Do NOT Update to Armbian 20.08.13!"
date:       2020-10-27 01:00:00
author:     "Kobol Team"
header-img: "img/072/software-support-bg.png"
---

# Do NOT Update to Armbian 20.08.13

We have received instability issues reported through email and forum with this new image. We are still investigating the root cause and managed to reproduce the kernel crash on some of our boards. We advise user do **NOT** upgrade to **Armbian 20.08.13** which contain **Linux Kernel 5.8.16** until further notice.

You can download **Armbian 20.08.10** which is known stable from following links

Filename | Link
---------|---------
**Armbian_20.08.10_Helios64_buster_current_5.8.14.img.xz**<br>Build date : 13/10/2020<br>Size : 443 MB|[Download](https://archive.armbian.com/helios64/archive/Armbian_20.08.10_Helios64_buster_current_5.8.14.img.xz)
**Armbian_20.08.10_Helios64_focal_current_5.8.14.img.xz**<br>Build date : 13/10/2020<br>Size : 334 MB|[Download](https://archive.armbian.com/helios64/archive/Armbian_20.08.10_Helios64_focal_current_5.8.14.img.xz)

You can prevent Board Support Package (bootloader/kernel/device tree) by following instruction on next [section](#prevent-bsp-update).


## Revert back to Linux Kernel 5.8.14

To downgrade to LK 5.8.14 we need to use *armbian-config*

```
sudo armbian-config
```

- Select System

![Armbian config main](/img/072/revert_01_main.png)

- Select Other

![Armbian config main](/img/072/revert_02_system.png)

- Confirm that you understand the risk and want to switch kernel.

![Armbian config main](/img/072/revert_03_agreement.png)

- Select Kernel, **linux-image-current-rockchip64=20.08.10**

  System will automatically reboot.

![Armbian config main](/img/072/revert_04_kernel_list.png)

- Verify you are running kernel 5.8.14 by executing

  `uname -r`

  You should get `5.8.14-rockchip64`


## Prevent BSP update

After kernel 5.8.14 running (either by downgrading or use older image), we need to frezee/hold the BSP package so it will not be updated in future.
We can use *armbian-config* for this purpose.

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

