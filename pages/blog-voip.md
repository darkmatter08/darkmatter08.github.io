---
layout: page
title: In Home VOIP
description: Convert our home phones into an IP system with the Asterisk PBX
---

> Convert our home phones into an IP system with the Asterisk PBX

* * * 

I was reading an article on SmallNetBuilder back in 2009 about the IP-PBX software called Asterisk http://www.smallnetbuilder.com/content/view/24226/72/ . The author talked about using Asterisk to build an answering machine, with the long term plan of managing his whole phone network through the software. IP-PBX seemed to turn the antiquated analog home phone into something worth of the internet age. It offered the flexibility of monitoring, extensions, answering machines, phone call analytics, and more. An IP-Phone is an embedded computer with a headset. I also learned that the telco’s backend is all IP based – and the analog ‘front end’ – the consumer facing part – is there only for compatibility/legacy reasons. In fact Vonage offered to its business customers direct links to their backend ‘trunk’ lines – meaning their Linksys VoIP router would be unnecessary. 

We were interested however in first augmenting our phone network. To do that, we needed to bring our analog lines into the IP-PBX. This is called “FXO” – foreign exchange office, or basically any external line. All the actual “phone numbers” that you have – basically the lines that you can call out from – are called “trunk lines.” So if we have one FXO card with one input and no configured digital (VoIP) trunk lines configured, we have a total of 1 trunk line. 

With one line to work with, we set out to configuring our IP Phones. We purchased two cheap sets from GrandStream via eBay. The rest of the configuration involved setting up Asterisk on the network, registering the phones on the PBX, and setting up the routing between the trunk and the phones. We also configured ‘softphones’ – software IP Phones that ran on your computer. Now, there are also IP Phone implementations on smartphones.  

Frustratingly, the GrandStream phones would not register onto Asterisk, despite our efforts to update firmware and change the settings. The softphones connected instantly and worked without error. I believe it was the poor implementation of the VoIP stack on these devices – I think a tried and tested Cisco device would work well. 

The promise of the VoIP service was huge. Besides the analytics and extensions, there was also the option of connecting remotely to your IP-PBX so you could make and receive calls from anywhere you had internet access with your local phone number.

We eventually shut down our IP-PBX experiment, as it wasn’t a viable replacement because of its high costs to replace all our existing phones. Now, I would implement the system and use a softphone client on my smartphone as a client. There are also low cost, low power ‘appliance’ devices that run Asterisk with built in FXO interfaces. If I could switch over to an IP Trunk provider (ie Vonage Business) and get a hosted IP PBX – Asterisk in the cloud – then I could simply have an IP Phone device at home and a softphone client on my phone. My home phone everywhere, delivered via IP. 

Nowadays, this is really not that exciting – why bother with a second phone system when cell phones work well? This makes sense for Gen-Yers who have no landline. But there are pretty substantial legacy applications for which this is important. I think this could be an interesting service for Google to consider – perhaps as a spinoff to Google Voice, and with a tightly integrated Android client that works just as well as a native client. It would also be interesting to offer this as a paid service to people in developing countries where telecom is expensive. The delivery costs are the same wherever you are. 

Other Resources:

[http://www.smallnetbuilder.com/multimedia-voip/multimedia-voip-reviews/24750-reviewaah](http://www.smallnetbuilder.com/multimedia-voip/multimedia-voip-reviews/24750-reviewaah)

[http://www.smallnetbuilder.com/labels/Asterisk](http://www.smallnetbuilder.com/labels/Asterisk)
