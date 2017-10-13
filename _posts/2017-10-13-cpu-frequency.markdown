---
layout:     post
title:      "Helios4 Default CPU Frequency!"
date:       2017-10-13 00:00:00
author:     "Kobol Team"
header-img: "img/010/cpu-freq-bg.jpg"
---

Some of you might have already realized that we have changed back the **CPU clock from 1.8GHz to 1.6GHz**. Originally when we [first introduced Helios4 on Armbian](https://forum.armbian.com/index.php?/topic/3045-support-of-helios4-intro/) we announced the CPU being clocked at 1.6GHz which corresponds to the SolidRun MicroSOM A388 commercial grade module.

The **Marvell Armada 388 SoC can be clocked up to 2GHz**, so along the way we were planning to clocked it on Helios4 at 1.833GHz. But after much consideration and looking at the small gain versus stability and heat dissipation we decided it was wiser to leave the default clock to 1.6GHz.

Even though we wouldn't advice it, **user can over-clock CPU on their own**. CPU frequency is set using pin strapping. To change the frequency you need to assemble some of the below resistors (R48, R50, R52, R54 and R56).

![schematics](/img/010/freq_assembly.png)

![schematics](/img/010/freq_table.png)

When none of those are assembled then the settings default to **0x0C** which runs the CPU at 1600MHz. For instance, to run at 1833MHz the user would need to assemble R48, R50 and R52.
