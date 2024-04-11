---
layout: page
title: The Smart Traffic Signal Platform
description: AI Traffic Management; Enables next-gen ADAS; Safer Self Driving; Increases safety today and tomorrow

---

> Editor’s note: This is an old, loosely structured write-up, not a polished and punchy blog.
> I am posting it here in the hopes that it helps someone or some company pursue this line of work.

### Background & Motivation
#### Intelligent Traffic Systems

Current traffic signals are ‘dumb’. The vast majority typically run on fixed timers. Some busy intersections have occupancy sensors embedded in the road, which trigger signals only if a vehicle is detected. They are very rarely networked and remotely controllable.

Traffic Engineers typically only conduct traffic studies when there is a major infrastructural change, such as a road upgrade or new development. They program the signal timers using a combination of intuitons and traffic formulas to achieve smooth traffic flows. The system is optimized only in a local vicinity, not ‘globally optimized’ across the whole city or region.

Advances in sensing and mobile computing in the past decade has led to growing interest in Intelligent Traffic Systems (ITS). As the name suggests, ITS systems add ‘intelligence’ to roadways and other transportation systems. For cities, this is realized as remotely managed traffic signals. Traffic signals are remotely controlled by computers in the city’s transportation authority. They can be monitored and reprogrammed remotely, instead of visiting the traffic signal cabinet. Operators can adjust traffic signal patterns in response to updates on highway traffic conditions or police reports. In some implementations, cameras installed at key choke points provide additional information.

Improvements in traffic flow allow existing physical infrastructure to be better utilized, reducing both capital and operating costs, and reducing environmental impact. This is driving city investment in ITS systems. Because of their expense, most deployments only automate key intersections.

ITS systems are being deployed across the country. Current deployments include the Las Vegas Strip, Southern California, and Washington D.C.

More Background: [[Wikipedia](https://en.wikipedia.org/wiki/Intelligent_transportation_system)] [[Berkeley PATH](https://path.berkeley.edu/research/traffic-operations)]

#### What is distributed sensing?
In distributed sensing, sensors are placed across a physical space, and work jointly to cover the whole space. This network of sensors behaves as a single functional unit. A CCTV camera deployment in a mall or office building is an example of distributed sensing.

We augment the city traffic signal with sensors (cameras and lidars) to create a smart city-wide distributed sensing network. This allows us to sense all road users -- cars, bikes, busses, and commercial vehicles.

We can build applications on top of this distributed sensing network. One immediate application is AI-Enabled ITS, or “AI Traffic Management.” Other applications include cooperative perception for Advanced Driver Assistance Systems (ADAS)/Advanced Safety Systems (ASS) and self-driving vehicles (SDVs).

#### The need for Cooperative Perception
Sensors on vehicles suffer from occlusion (visibility) problems, just like human drivers do.
One particularly dangerous scenario is the unprotected left turn. 

![Image](/assets/media/intelligent_traffic/unprotected_left.jpg)
Unprotected Left Turn. [[source](https://www.sciencedirect.com/science/article/pii/S0022437515000481)]

In this scenario, each vehicle is traveling the opposite direction and is in the left turn lane. Their view of oncoming traffic is partially occluded (blocked) by the oncoming vehicles turning left. The oncoming traffic is moving quickly because of the green light in both directions. They may take the turn without full visibility, leading to a T-Bone collision. Otherwise, they will wait until the traffic lights turn yellow/green, stopping the oncoming traffic.

> On a personal note, I know two different people who have been in serious accidents during unprotected left turns. In both incidents, the vehicles were totalled and the victims were briefly hospitalized for minor injuries.

This results in many accidents per year in the USA. There is no Advanced Safety System (ASS)/Automated Emergency Braking (AEB) system that can prevent these accidents. This is because no advancement in sensor technology on the vehicle will solve the occlusion problem. However, distributed sensing can solve this problem. By sharing the camera perception data from smart traffic lights (cooperative perception), AEB systems can anticipate such collisions and apply the brakes to prevent collisions. 

Many other traffic scenarios with occlusions would benefit from cooperative perception -- blind right turns on red, “merge or die” lanes on highways, and driving out of urban alleys. 

### Core Technology
#### Hardware
Simple plug and play box inside of the traffic signal control cabinet.
Sensing Package mounted on Traffic Signal near emergency light.
	4x cameras, one in each direction.
1 Lidar
Only need Sensing Package on 2 of 4 signals at a typical 4 way intersection
Traffic Signal Cabinet
V2X radio
LTE Radio
Hardwired Network Connection with failover LTE radio. LTE radio only if no Hardwired connection.

As far as frequencies and transport layers go, in the US and EU there is dedicated spectrum set aside (5.9GHz). C-V2X (a protocol that uses this spectrum, adopted from LTE & 5G) seems to be emerging as the standard. So that takes care of PHY and transport.
#### Software
Sophisticated machine learning algorithms for traffic planning.

Open (no license) protocols to run on the radios

##### Backend
Can be run on-prem, on-cloud, or hybrid, to meet compliance needs and client requirements.

##### On-Device/Client Device
Protocols running on PHY. Raw sensor data v.s. processed perception.
ADAS and SDV licensees may run custom protocols on the same PHY. However, we heavily push for the use of open and interoperable standards.

At the protocol level, I imagine the most basic protocol to transmit the following information -- location, speed, direction, and 'state' (i.e. normal or disabled). I imagine this protocol to be the "FTP" of V2V. I figure there will be a similar family of protocols for bi-directional V2I similar common standard for traffic signal state, and maybe some applications like parking information/payment, and tolls, although this seems less mature at the moment. I imagine that cars will get SW updates to slowly enable more protocols, just like we download a new browser to get support for the latest web features -- or perhaps, more like auto update -- to the limit of the installed HW. I can also imagine proprietary protocols on the network -- similar to today's situation with OBDII diagnostic ports.

##### Open Source
Consortium around the development of open protocols to be used on the platform.

#### Functionality
##### ITS
Automatically create a baseline traffic map (temporal).
Actionable alerts when outlier traffic situations arise. (e.g. dispatch traffic cop).

Recommendations for traffic signal timing changes.
Can implement a zone-by-zone traffic signal timing plan based on your city’s real data. This schedule can change signal timing by time of day, weekday/weekend, holidays, special events. 
	“Rachio but for traffic signals.”

Can automatically generate new traffic plans that increase capacity along specified routes, for special events (sporting events, parades, etc).

Traffic Signal state broadcast for smart device/car integration (like Audi (now) and Waze (future)).

(Future) Integration with Google Maps/Waze routing algorithms to cooperatively plan routes.

##### VRU alerts
Vulnerable Road Users (VRUs) are Peds, Bicycles, Motorcycles, Scooters. Non-motorized and small motor road users with little external shielding to protect them in case of a collision.

VRUs can be integrated into the Cooperative ADAS system via smartphones. Smartphones would share their location within the intersection and in case of a potential collision, two way alerts, on the smartphone, and on the car, would be sent. AEB on the car could also be activated.

##### Road Safety Analytics
Can track frequency of cars entering into bike lanes
Can track the most dangerous intersections
Can track frequency of traffic signal violations, e.g. running red lights or illegal turns.

##### Cooperative ADAS
Current ADAS safety functionality is limited to Automated Emergency Braking (AEB), based on radar or camera sensors on the vehicle itself.
They cannot handle occlusion situations like unprotected left turns -- one of the most common and most dangerous types of accidents.
By using our distributed sensing platform, ADAS systems can handle these situations as well.

Advanced ADAS systems are becoming ubiquitous, even in mainstream brands: Honda’s ADAS systems are standard in all new cars.
Consumers are willing to pay for ADAS systems ([$500](https://technology.informa.com/581934/consumers-crave-advanced-technology-in-new-vehicle-purchases-ihs-markit-survey-finds)) and expect them on their new vehicles. They are also willing to pay for software updates for their vehicles.
More sophisticated, more confident, and less error prone ADAS systems are a point of differentiation. The effectiveness of different implementations are tested by [various organizations](https://www.consumerreports.org/car-safety/cars-with-advanced-safety-systems/).

##### Cooperative Planning for SDVs
These would be open protocols, but encrypted. 
We would form a consortia to standardize these protocols.
Similar to email (open standard) but everyone has their own accounts

### Customers
Cities for ITS
ADAS vendors and OEMs. (Bill to drivers for annual subscription?)
Self-Driving companies

### Selling points
*For Cities:*
The best, most sophisticated, and future proofed ITS system.
The ITS system is adaptive and learns from the city. A fully custom traffic system.

Improve traffic flow in your city
Reduce traffic accidents in your city -- for all road users!!
	Reduce police resources for traffic accidents and traffic management
Make your city a technological leader

*For ADAS Vendors:*
Offer the best ADAS system available.
Offering enhanced AEB will be a competitive advantage.
It is a potential new revenue stream for ADAS and OEMs.
Sell consumers safety and lower insurance costs.

### Monetization
Sell to cities. Make money on recurring subscriptions for the latest software. Have a cost advantage over competitors because we’re selling the software platform, not just the hardware. Drive down costs to cities as licencing to ADAS vendors becomes the dominant part of the business. 

License access to the platform to ADAS vendors. They must pay for a per-vehicle license to enable the technology.

License access to the platform to SDV vendors. They must pay for a per-vehicle license to enable the technology.

### Virtuous Cycles and Platform Effect
Sell to cities. They already have budgets for ITS. It’s a cheaper and intelligent alternative to building new physical infrastructure.

Sell to ADAS vendors. They will push cities to adopt these technologies.

Sell to SDV companies. They will come to cities with the best infrastructure. They will push cities and perhaps partner with cities and large private operators like airports to deploy our technology.

Sophisticated End-Users will push their cities to deploy our technology, so their vehicles can be safer.

Every stakeholder will have their own reasons to buy into the platform. Every stakeholder will have a reason to advocate for the expansion of the platform. This will create a virtuous cycle of expansion.

The virtuous cycle will be kicked off by cities looking to solve traffic congestion issues via ITS. They already have budgets and priors for ITS systems. Legislation is also encouraging cities to deploy ITS.

### Counter-Intuitive Intuitions
The more smart traffic at the intersection, the safer it is!
Costs go down for all users as deployment size increases!
Time to payoff decreases as network size increases.
Private Fleets may be the first adopters of enhanced ADAS features (Amazon, UPS, USPS).

We do not need to dominate the space. Others can roll out their own implementations, but as long as it follows the open standards that our company will drive, all implementations will remain broadly compatible. Other competitors entering the market will expand the addressable market for ITS and the global platform. In other words, we want competitors!

Dense regional is better than sparse nationwide.

### Pop Media Articles
[San Diego deploys cameras on streetlights](https://arstechnica.com/tech-policy/2020/11/san-diegos-spying-streetlights-stuck-switched-on-despite-directive/)

[Audi V2I: traffic light countdown available in select US cities](https://www.extremetech.com/extreme/265671-audi-traffic-light-information-v2i-app-now-works-d-c#:~:text=Audi%20is%20taking%20its%20automatic,time%2Dto%2Dgreen%20communication.)

[Willingness to pay for ADAS ~$500](https://www.businesswire.com/news/home/20160725005763/en/Consumers-Crave-Advanced-Technology-in-New-Vehicle-Purchases-IHS-Markit-Survey-Finds)

[Demo of an ITS system](https://arstechnica.com/video/watch/cars-technica-ars-rides-in-an-iteris-connected-vehicle)

### Others in the space
Iteris -- https://www.iteris.com/products/detection-sensors
Experts in traffic management, traffic analysis, and growing into CV based traffic systems. Repeatedly hired by Federal, State, and city governments for traffic projects. Seems to have a strong collection of expertise. 

Kapsch -- https://www.kapsch.net/us/ktc
Austria/USA. Large player in automotive and controls space. Traffic Controls division is engaging in these new products

Derq -- https://en.derq.com/
MIT Startup, Partnership with Dubai, based in Detroit/Dubai. COVID play for public safety

Observation
Not much information available.

### Old Notes describing the idea

*Motivation:*
It's become clear to me that sensors on the car alone will not fully solve SDVs. They will struggle in situations like unprotected left turns because they just don't have visibility nor the level of intuition that humans have. SDVs from leaders like Waymo, Uber, and Cruise aren't doing any integrations with "smart" infrastructure. I think it's largely because infrastructure's inherent chicken and egg problem.

I think there's a big opportunity for a company to partner with a city to roll out sensors -- cameras, radars, and lidars -- to stoplights on major intersections. These sensors will provide much better situational awareness for any vehicle. Using V2X radio frequencies (or some other tech?) they can broadcast both raw and processed versions of their signals to nearby vehicles. Nearby vehicles, whether they be SDVs or human operated vehicles with advanced safety systems, can receive these signals and operate more safety in these challenging environments.

The city wouldn't pay anything for installation and maintenance, and the company would charge a fee to access the signals from automakers (most likely), or possibly drivers. A car with this technology would drive more safely in cities with this tech, and the roll out would be gradual. This is akin to how a decade ago, some city busses had GPS trackers installed on them, and the apps were crowdsourced. 

There's a lot of analysis to be done here... One obvious risk item is partnering with cities. 
For a vendor of ADAS/SDV software components, I'm curious how this sounds to you. Both as a customer, and as someone who has to sell their tech as a module to others. Does it sound viable?


*Standards and Protocols:*
I agree, the whole proposition will fall apart without standards. As far as frequencies and transport layers go, in the US and EU there is dedicated spectrum set aside (5.9GHz). C-V2X (a protocol that uses this spectrum, adopted from LTE & 5G) seems to be emerging as the standard. So that takes care of PHY and transport.

At the protocol level, there seems to be some basics agreed upon -- location, speed, direction, and 'state' (i.e. normal or disabled). I imagine this to be the "FTP" of V2V. I figure there will be a similar family of protocols for bi-directional V2I similar common standard for traffic signal state, and maybe some applications like parking information/payment, and tolls, although this seems less mature at the moment. I imagine that cars will get SW updates to slowly enable more protocols, just like we download a new browser to get support for the latest web features -- or perhaps, more like auto update -- to the limit of the installed HW. I can also imagine proprietary protocols on the network -- similar to today's situation with OBDII diagnostic ports.

Re: comparison to the highway system. The highway system effectively had a single customer -- the federal government -- since they spent the majority of funds to build the system. A better comparison would be cellular technologies, but even that isn't perfect, since Bell was a monopoly for years -- and there are a dozen or more large automakers around the world. That's where the chicken and egg problem for infrastructure I mentioned comes in.

Back to my original point, there's a lot of activity in the HW and SW, but less on how infrastructure like signals will be updated to support all this tech. I don't think cities will spend on this unless they themselves get some benefits from these upgrades. Hence the partnership idea. 

There could also be an opportunity on the other side of the coin. My line of thinking is -- automakers will want to buy a solution that offers all the safety & convenience benefits of V2X, that's easily integrate-able, ala Mobileye but for V2X. How does that sound?


*How companies will coooperate:*
A startup that partners with cities to roll out this smart infrastructure. The city wouldn't pay anything for installation and maintenance, and the company would charge a fee to access the signals from automakers (most likely), or possibly drivers. I imagine a handful of firms doing this rollout, all around open or shared standards. My venture would join the V2X consortia that are developing these standards.
