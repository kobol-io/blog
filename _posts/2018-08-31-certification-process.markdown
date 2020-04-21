---
layout:     post
title:      "Helios4 FCC and CE Certification !"
date:       2018-08-31 01:00:00
author:     "Kobol Team"
header-img: "img/031/certification-bg.png"
---

After quite some work, we are finally **ready to start ElectroMagnetic Compatibility (EMC) testing to verify Helios4 compliance with FCC and CE standards**. Since Helios4 doesn't deliberately transmit (the board doesn't have any radio module), we are only required to do the following testing :

- Verification of Conformity for FCC Standard :
    * FCC CFR 47 PART 15 SUBPART B Section 15.101

- Declaration of Conformity for CE Standards :
    * EN 55032:2015
    * EN 61000-3-2:2014
    * EN 61000-3-3:2013
    * EN 55024:2010

Here are the two kits that are on their way to the UCS certification lab in South Korea. With two kits the lab can work faster and run in parallel FCC and CE tests.

![Helios4 Test Kit](/img/031/test-kit.jpg){: .center-image }

If you are curious about the testing procedures, you can have a look at our [test manual](https://wiki.kobol.io/files/carrier/Helios4_FCC_CE_Test_Manual-v0.1.pdf) that we wrote for the lab to setup and operate Helios4.

We have also developed a dedicated testing application that was needed in order to exercise all the high speed interfaces on the board while radiating test are performed.  You can find the app on our [github](https://github.com/kobol-io/test-suite).

![Helios4 Test Suite](/img/031/test-app.png){: .center-image }

It will take about 3-4 weeks to run the whole list of tests and for the lab to write the test reports. The System-on-Module on which Helios4 has been built, has already validated the same test scope for other products, so **we can see this process as just a formality... but a painful one :P**

Once it's done we will publish the test reports on our wiki.
