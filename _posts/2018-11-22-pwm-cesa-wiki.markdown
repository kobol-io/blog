---
layout:     post
title:      "Everything about PWM Fan and Crypto Engine on Helios4 !"
date:       2018-11-22 01:00:00
author:     "Kobol Team"
header-img: "img/042/pwm-cesa-bg.png"
---

We have updated our wiki with 2 new tutorials :

- [How to use CESA to accelerate encryption](https://wiki.kobol.io/cesa/){: .underline }
- [How to use PWM for Fan speed control](https://wiki.kobol.io/pwm/){: .underline }

### How to use CESA

The A388 System-On-Module used by Helios4 has two **Cryptographic Engines and Security Accelerator (CESA)** which can be used to offload compute intensive cryptographic operations.

![Crypto API](/img/042/crypto_api_interfaces.png)

The tutorial will explain how to leverage on Marvell CESA units to accelerate network application encryption. This guide is for advanced users who understand the security implication of tweaking encryption library and cipher configuration. [Find out more...](https://wiki.kobol.io/cesa/)

### How to use PWM

Helios4 provides **2x PWM Fan connectors** (headers J10 and J17) to connect cooling fans. The tutorial will explain in details how PWM works and how to setup your system to automatically control fan speed based on CPU temperature. If you are using Armbian image, you don't have to do anything, it is already built-in. [Find out more...](https://wiki.kobol.io/pwm/)

![FAN PWM Curve](/img/042/fan_type_c_curve.jpg)
