---
layout:     post
title:      "Helios64 Shipping Update 2!"
date:       2020-09-28 01:00:00
author:     "Kobol Team"
header-img: "img/070/shipping-update-bg.png"
---

# Shipping Update

**As of today we have shipped exactly half of the orders. It's not moving as fast as we hoped but it's still moving.** The bottleneck comes from the enclosure factory which is not delivering as quickly as they promised after they decided to redo the anodizing of the aluminum case.

Also do note that China will be on public holiday for their National Day coming soon, so this will impact our warehouse operation for the coming 10 days.

Some of you wonder why their orders are still not shipped even though they are amount the early buyers. The reason could be that you are from one of the few countries we made wrong estimate on the shipping fees and/or we didn't anticipated the post covid-19 impact on shipping cost and route. We already addressed this issue with customers from Switzerland, Russia and New Zealand. This week we will approach the other few dozen concerned customers.

We apologize for the fact that this doesn't translate into a great customer experience. We hope you will understand that this is a learning curve for us and all those mistakes we made will help us to further improve.

Finally, please understand that sending us email to ask us about your order status hoping it will fast track your order has the exact opposite effect. The time we spend replying to your email is time we are not spending on fulfillment. We understand the impatience, but keep in mind we are a very small team and we would prefer to allocate our limited bandwidth to more urgent tasks. Thanks for your understanding.

# OS Support Status (Armbian)

**Recently we published the latest Armbian images for Helios64, version 20.08.4.** These images have a lot of improvement but they are still considered as work-in-progress.

The board is still experiencing some instability issues that we have now narrowed down to wrong LPDDR4 timing settings. This is going to take us a bit of time to fine tune. For now we are recommending to use Linux Kernel 4.4 which is more stable than 5.8. Don't worry, you won't have to do a fresh install once Linux Kernel 5.8 is good to go.

Filename | Download
---------|---------
**Armbian_20.08.4_Helios64_buster_legacy_4.4.213.img.xz**<br>Armbian 20.08.4 Debian 10 Buster (Kernel 4.4.213)<br>Build date : 24/09/2020<br>Size : 412 MB<br>Status : **Relatively stable**|[Link](https://dl.armbian.com/helios64/archive/Armbian_20.08.4_Helios64_buster_legacy_4.4.213.img.xz)
**Armbian_20.08.4_Helios64_buster_current_5.8.11.img.xz**<br>Armbian 20.08.4 Debian 10 Buster (Kernel 5.8.11)<br>Build date : 24/09/2020<br>Size : 464 MB<br>Status : **Unstable**|[Link](https://dl.armbian.com/helios64/archive/Armbian_20.08.4_Helios64_buster_current_5.8.11.img.xz)
**Armbian_20.08.4_Helios64_focal_current_5.8.11.img.xz**<br>Armbian 20.08.4 Ubuntu 20.04 Focal (Kernel 5.8.11)<br>Build date : 24/09/2020<br>Size : 345 MB<br>Status : **Unstable**|[Link](https://dl.armbian.com/helios64/archive/Armbian_20.08.4_Helios64_focal_current_5.8.11.img.xz)

This, hopefully, will be the last news we need to post about shipping / fulfillment ;-)
