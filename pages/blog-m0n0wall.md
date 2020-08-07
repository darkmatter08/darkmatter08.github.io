---
layout: page
title: m0n0wall Gateway
description: A high performance, enterprise grade, open source gateway for the home.
---

> A high performance, enterprise grade, open source gateway for the home.

* * * 

After our whole home network installation was done, our network was convenient and fast. But all our components – the routers and WiFi access points – were consumer products, other than our gigabit switch. But I knew there was speed to be gained at the entry of our network – the gateway from the internet to the switch. M0n0wall http://m0n0.ch/wall/ is a BSD distribution that functions as an internet gateway. It tracks network traffic both in and out. It can do packet level filtering and blocking. It can do bandwidth throttling/QoS. I thought that the throughput from our Comcast cable internet to our network was being bottlenecked by our basic Linksys router. So I purchased two gigabit network cards and installed them into an old computer. I also decided to get a PATA to SD card adapter to save electricity by not running a spinning disk. 

I installed m0n0wall, and it was pretty neat. I thought I would turn the box into my WiFi hotspot as well, by buying a wireless card. But the port forwarding never seemed to work. I’m not sure why. After a week of experimentation, I decided to abandon the effort. I’d like to try the product again, armed with my more advanced knowledge of Linux networking. There’s also a similar distribution called PfSense http://www.pfsense.org/ 

Since then, we’ve switched over to a Cisco RSV-4000, which is pretty fast and works as a VPN host. It’s also a gigabit switch. 
