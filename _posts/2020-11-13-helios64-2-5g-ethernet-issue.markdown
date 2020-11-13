---
layout:     post
title:      "Helios64 Product Limitation Notification !"
date:       2020-11-13 01:00:00
author:     "Kobol Team"
header-img: "img/073/hardware-notif-bg.png"
---

# 2.5G Ethernet Issue at 1Gbps Link Speed

Recently we have discovered that when Helios64 2.5G Ethernet interface is connected at 1000Mb/s Link Speed (e.g. Connected to a Gigabit switch), the performance is really degraded, around 10 - 100 Mbps. Using iperf3 to test, it shows many packet retries which reduce significantly the throughput.

After investigation we found out that center tap of the RJ45 magnetic should have been directly connected to 2.5V power rail to provide common mode for MDI signals. Below is our schematic, we missed the connection on pin 5 and pin 6 to the mentioned power rail.

![schematic](/img/073/RJ45_schematic.png)

Most of 1G Ethernet design (eg. RTL8211F) don't have requirement to connect center tap to power rail. However this connection does exist in 100Mbps design but we didn't expect it would have been needed for our design. Unfortunately during design and manufacturing phases we only focused on 2.5Gbps link speed so we didn't catch this issue earlier.

# Solution

**DISCLAIMER Please understand we are not responsible for any damage you might do to the board !**

Fortunately, it is not too difficult to fix it if you have some soldering skills.

To fix it, you need to connect the following two points with a cable. It is located on bottom side of the board below the affected Ethernet interface.

![wiring](/img/073/wiring_diagram.png)

Below a picture of a fixed board for your reference.

![fixed board](/img/073/fixed_board.png)

# Conclusion

Unless you are able to perform the fix described above, the 2.5G Ethernet interface is therefore limited to 2500Mb/s speed link usage. We apologize for the limitation. We will of course fix this issue in future revision of the board.
