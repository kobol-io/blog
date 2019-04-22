---
layout:     post
title:      "Design Change Notification for Helios4 !"
date:       2019-04-22 01:00:00
author:     "Kobol Team"
header-img: "img/052/design-change-bg.png"
---

For Batch 3 we did a minor design modification to **provide better isolation between Fan control signals and the ARMADA 388 SoC GPIO pins**. The change is motivated by few reports of product damage to the said SoC GPIO pins during wrong manipulation.

![PWM redesign](/img/052/pwn-redesign.png)

To be in line with 4-wire PWM Fan specifications that requires the PWM pin to be open-drain and 5V tolerant we added a non-inverting buffer for each GPIO PWM pin as shown above.

The new carrier board will be tagged as **rev 1.2**. We have already published the updated carrier board schematics [here](https://wiki.kobol.io/docs/#carrier-board) on our wiki.

This minor change **doesn't have any impact** on certification nor on manufacturing schedule ;-)
