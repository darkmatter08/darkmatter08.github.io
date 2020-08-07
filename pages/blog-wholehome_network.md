---
layout: page
title: Whole Home Network
description: A wired network to enable convenient and fast use of our computers across the house. 
---

> A wired network to enable convenient and fast use of our computers across the house. 

* * * 

![Image](/assets/media/wholehome_network/Patch Panel.jpg)

We moved to a new house. I got a new computer, for my room. We just set up a NAS (networked attached storage) as a home server. But all these new devices needed more connectivity. Our Wi-Fi was slow and unreliable. It prevented us from backing up our computers and streaming media. 

At first, we bought a better router. More power and range seemed to be the only tenable solution. While better, this router didn’t enable easy, pain-free backups and buffer less streaming. 

At the same time, we began to investigate our little wiring closet. It was the endpoint for phone and coaxial wiring. We then noticed that the phone wires were actually Cat-5e cables. And they all terminated in that one closet. It seemed like we could actually make something of this. Gigabit Ethernet to every room in the house! 

I began investigating how to add connectors to each cable. I ran across [these connectors](http://www.monoprice.com/Product?c_id=105&cp_id=10513&cs_id=1051303&p_id=1044&seq=1&format=2&utm_expid=58369800-11.KFcpHWqASSutMqNPOqaJVg.0&utm_referrer=http%3A%2F%2Fwww.monoprice.com%2FSearch%2FIndex%3Fkeyword%3Dcat6%2Bkeystone) on monoprice.com, one of my favorite websites for ordering wiring related stuff.

It was a way to attach a cut Ethernet cable into a jack. And these [“keystone” jacks](http://www.monoprice.com/Product/?c_id=105&cp_id=10517&cs_id=1051703&p_id=6725&seq=1&format=2&utm_expid=58369800-11.KFcpHWqASSutMqNPOqaJVg.0&utm_referrer=http%3A%2F%2Fwww.monoprice.com%2FProduct%3Fc_id%3D105%26cp_id%3D10513%26cs_id%3D1051303%26p_id%3D1044%26seq%3D1%26format%3D2) attached to wall plates that could hold any configuration of these jacks.

We ordered a few of these. With some basic continuity testing, we figured out to which room each cable went.  We did a trial with the phone wire to my room. It worked! 

Now we knew we had a working solution on our hands. We could have Ethernet going to every room that didn’t need a phone connection. But what if we wanted to switch between the two? 

I discovered by experimentation that Cat3 (phone) and Cat5 or Cat6 are ‘backwards compatible,’ but not in the traditional sense. You can actually plug in a Cat3 connector into a Cat5 jack. Of course, if the Cat5 jack was actually connected to a switch, it wouldn’t do anything. But if the Cat5 jack was connected to the POTS (plain old telephone system) on the other end, then it would function just like a normal Cat3 connection. This meant that we could actually change all the Cat3 jacks (in each room) to Cat5 jacks. On the other end, we could chose which rooms to connect to a switch versus POTS. 

This was better. What if a future owner wanted POTS to every room? What about Ethernet? He might have to call in an electrician. So we wanted a modular system that didn’t require a permanent conversion. 

I discovered something called a ‘patch panel.’ It’s basically a big set of keystone jacks on one panel, used for terminating wiring in a closet. If we attached every room’s cable to a patch panel, then we could attach some rooms to the network and some rooms to POTS, via a splitter. We called this the ‘room’ patch panel. 

Wiring POTS is very simple. You have one ‘source’ wire, traditionally coming from your phone provider (AT&T) from the outside of your house. The two wires that the phone signal actually comes on are simply wired together with every room that needs it. It’s usually done with a simple electrical end cap. So basically we needed a clean and modular splitter for our application. 

The bad solution would have been to attach a bunch of wires to our source POTS wire, and attach that to the patch panel. Instead what we did was to turn another patch panel into our POTS splitter. 

Basically we wired all the patch panel’s common pins together. Then we had one ‘input wire’ into the whole splitter. We mounted the splitter right adjacent to the patch panel that had the wires to the room. Now, a simple connection from one patch panel to the other turned it into a POTS connection. Or an Ethernet from the room patch panel to the switch turned that room into a gigabit Ethernet connection. This new patch panel was not really a patch panel. We called it the POTS splitter. 

Now we had a pretty tenable solution. We bought a Dell 24-port Gigabit Ethernet switch, since we had a $150 gift card from them. It was an L3 switch, capable of cool things like port bonding and VLANs. We also moved most all of our networking equipment into that closet – the cable modem, our Vonage VoIP box, our ‘gateway’ router, and our Qnap NAS (now retired). Some time later I also experimented with using m0n0wall as our gateway. 

We mounted the patch panels onto a wood panel, and the switch right adjacent to it in our networking closet. It was a pretty cool solution. This was basically our ‘network room’ and ‘server room.’ It was the ‘digital hub’ of our home. Our network was extremely fast and reliable. We could stream media or make backups instantly. We were free from the unreliability of Wi-Fi. 

Soon afterwards, we expanded the network throughout our finished basement. Since we were self-installing, we used all Cat6 grade hardware – cables, jacks, and patch panels. This allowed us to have more computer as servers in our spare bedroom, and gigabit Ethernet in the media room. 

I learned a lot from this project. How ‘commercial grade’ network wiring is done, and the tools used to do it. How to make a modular and flexible system. Using L3 switches. How to organize wires with zip ties. This was probably the project that triggered and enabled so many future projects. 

Gallery:
![Image](/assets/media/wholehome_network/CAT6 Install 1.jpg)
![Image](/assets/media/wholehome_network/CAT6 Install 2.jpg)
![Image](/assets/media/wholehome_network/CAT6 to Ethernet.jpg)
![Image](/assets/media/wholehome_network/CAT6 to Phone.jpg)
![Image](/assets/media/wholehome_network/Ethernet 1.jpg)
![Image](/assets/media/wholehome_network/Patch Panel Full.jpg)
![Image](/assets/media/wholehome_network/Server Room Connections.jpg)
![Image](/assets/media/wholehome_network/Switch.jpg)
![Image](/assets/media/wholehome_network/Switches and routers.jpg)
