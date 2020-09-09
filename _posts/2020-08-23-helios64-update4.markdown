---
layout:     post
title:      "Helios64 Production Update 4 !"
date:       2020-08-23 01:00:00
author:     "Kobol Team"
header-img: "img/068/production-update-bg.png"
---

# Manufacturing Status

It took us a bit of time to post this update because of few annoying problems we are experiencing on the last phase of production, generating a lot of stress for things we thought was behind us already.

### Helios64 Board

As mentioned previously, the latest step before packing the board was the Factoring Acceptance Test (FAT). Unfortunately this process is not going as fast as expected and managing it remotely is not helping either. Our test successful rate is not as high as we expected. It turned out that our FAT software was a bit too strict resulting in some board failing the FAT while they are actually OK. We also noticed an issue with the PCIe link training on some of the boards, which we are currently investigating in order to fine tune the PCIe PHY settings on both RK3399 and JMB585 chips.

### Helios64 Enclosure Kit

While the manufacturing was completed, the quality inspection revealed that the anodize finish of the aluminum shell wasn't up to standard. So it was decided to redo the anodizing step. It's ongoing and will soon be completed.

# Shipping Status

**We are still starting to ship next week !** But it will take us a bit longer to get all of the thousand++ orders on their way. For fairness we will ship according to order dates. First people to have pre-ordered, will be the first ones to get their Helios64 shipped.

**As soon as we have shipped your order you will receive a notification email with the tracking information**. You can also check your order status [here](https://shop.kobol.io/check-order/) using your order ID and email. If the order status is *"processing"*, it means you order hasn't been shipped yet. If it shows as *"completed"*, it means it has been shipped and the tracking information should be displayed.

# DDP for EU customers

Last month we introduced the Delivered Duty Paid (DDP) option for EU customers and we made it mandatory for all orders of Helios64 Full Bundle. Almost everyone has already settled their DDP add-on invoice but we have still few dozens which haven't yet. Please take note that we won't be able to ship your order until you settle the invoice. We will resend the invoice for those who haven't settled it yet in case you didn't receive the email in the first place.

# Assembly Manual

While we still have a lot to publish on our wiki regarding installation and configuration instructions,**we just finished the Enclosure Kit assembly manual that you will find on the following [page](https://wiki.kobol.io/helios64/kit/).**

[![Kit Assembly](/img/068/kit-assembly1.png)](https://wiki.kobol.io/helios64/kit/)

[![Kit Assembly](/img/068/kit-assembly2.png)](https://wiki.kobol.io/helios64/kit/)

# Armbian Support

**Helios64 support has been added to Armbian lastest [version 20.08](https://www.armbian.com/newsflash/armbian-20-08-caple/)**. You can already find image on the Armbian [download page](https://www.armbian.com/helios-64/). It's still a work in progress, but should be completed by the time people receive the first boards.

# CE and FCC EMC Test Result

We are happy to announce that **Helios64 passed all the required EMC (ElectroMagnetic Compatibility) tests to conform to FCC an CE regulation**. You can find the test reports and declaration of conformity documents on our wiki [here](https://wiki.kobol.io/helios64/docs/#certification).

[![CE FCC DoC](/img/068/ce-fcc-doc.png)](https://wiki.kobol.io/helios64/docs/#certification)



**Once again the Kobol Team apologizes for the delay experienced.**  
