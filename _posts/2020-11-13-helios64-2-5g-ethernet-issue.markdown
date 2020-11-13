---
layout:     post
title:      "Helios64 Product Limitation Notification !"
date:       2020-11-13 01:00:00
author:     "Kobol Team"
header-img: "img/073/hardware-notif-bg.png"
---

# 2.5G Ethernet Issue at 1Gbps Link

Recently we have discovered that when 2.5G Ethernet connected at 1Gbps link (eg. it connected to a Gigabit switch), the performance is really bad, 10 - 100 Mbps.
Using iperf3 to test, shows many packet retry that reduce the throughput much. In factory test, we test the ethernet at 2.5Gbps speed so we didn't catch this issue earlier.

After some investigation we found out that center tap of the RJ45 magnetic should be connected to 2.5V power rail directly to provide common mode for MDI signals. Below is our schematic, we missed the connection on pin 5 and pin 6 to the afromentioned power rail.

![schematic](/img/073/RJ45_schematic.png)

Most of 1G ethernet design (eg. RTL8211F) don't have requirement to connect center tap to power rail. However this connection does exist in 100Mbps design.

# Solution

Fortunately, it is quite easy to fix. You just need a cable, solder wire and a soldering iron.

![wiring](/img/073/wiring_diagram.png)
To fix it, we need to connect these two points with a cable. It is located on bottom side of the board.

Below is photo of the fixed board for your reference.
![fixed board](/img/073/fixed_board.png)


