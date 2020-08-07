---
layout: page
title: RouteFun, MIT-VW-IDEO Hackathon
description: Analyzed OBD-II and GPS data from many drivers to rank routes by level of ‘fun.’ 
---

> Analyzed OBD-II and GPS data from many drivers to rank routes by level of ‘fun.’  

* * * 

![Image](/assets/media/routefun/)

[IDEO Hackathon page](http://ideo.cc/projects/vw-hackathon/)

I participated in the “Data Driven” hackathon jointly hosted by the Media Lab, Volkswagen, and IDEO. This hackathon seemed to be right up my niche – cars, computers, and probably the world’s best known design firm. 
VW was making available some interesting resources to hack with. There were four broad categories:
1.	OBD Data
Collected data from 15 volunteer VW of America employees. The Torque app (available on Android) tracked not only OBD Data, but also GPS coordinates, g-force, and more statistics.
2.	Sales and Marketing Data
Data about sales leads – gender, age, zip code, and more – and then information about follow through purchases.
3.	Free Data
This was by far the most vague of the categories. This was basically scraping the internet and extracting data from it. If you involved yourself with this group, then some participants brought in knowledge of tools they know. Ultimately, I only saw conceptual projects come out of this category.  
4.	Audi RS7
VW brought an Audi RS7 to show people the current state of car technologies. They wanted someone to imagine an ‘improved experience’ – new UI/UX, and something that incorporated data. 


I worked with my friend Andrew. Both of us were intrigued by the availability of the OBD data – something that’s normally just locked inside of the car. While brainstorming, we decided that we wanted to build a ‘profile’ for each driver based on his driving style, by analyzing the OBD data. Once we had a profile, we could sell targeted ads to the user. For an ‘enthusiast’ driver, this could be ads for exotic car rentals, new models, and car upgrades. For an ‘eco’ driver this could be carpooling services or eco-friendly eateries. 

Andrew and I were interested in building something though. It didn’t seem like we had enough data to build a profile. So after much debate, we simplified the idea. We would analyze each ‘route’ that was recorded and rank it by how fun it is. We would analyze the OBD data for key statistics – changes in RPM, total G force, change in pedal position, and more statistics. We’d boil down all this analysis into a ranking from 1 to 5, where 5 is  ‘enthusiast’ and 1 is ‘eco-friendly’ – the code word for ‘boring.’ 

The data was presented to us in a hosted MySQL database. Although I was familiar with relational database architecting and concepts, I actually never had learned SQL. This is because I learned about relational databases through Test#Code, which was written in Django. It allows you to work with databases without writing SQL queries, but you still must understand how a database works.

I learned about SQL queries while exploring the database, with the help of a VW employee there. He was really helpful – he must have spent 3 hours helping me get up to speed with SQL. 

The plan was to first manipulate the database to add the “ranking” column, having done all our analytics. Then I would write a Django backend to work with this database and serve up the frontend requests. The frontend would simply ask the user what ranking of routes he wanted (“Only routes greater than 4”) and then would ask the backend for all the matching routes. The user would then select any particular route and it would be plotted on the embedded Google Maps, by asking the server for all the GPS coordinates that matched that particular route. 

It seemed pretty simple once I got the database ready to go. I thought I would just use Django’s “inspectdb” feature to automatically import a legacy database into django’s model wrapper. But our database schema had a composite primary key on a table we needed. Somehow, Django didn’t support this schema. This meant that I’d have to write custom SQL queries and format the data myself before sending it to the frontend. That’s exactly what I did. 

The last step was to get all these GPS coordinates and draw a “polyline” with them on the Google Map. Just by following the Google Maps API docs made it pretty easy. https://developers.google.com/maps/documentation/javascript/examples/polyline-simple 

It took me 2 days outside of the hackathon, but finally the project worked. Now I’m just waiting on Andrew to update the great frontend he made with the logic on my demo page. 

A problem I faced: Getting external MySQL databases to work on Mac with Django was a pain. I eventually had to download and install MySQL just to get some config file that the mysql-python module needed, but I don’t think even ultimately used.  

Things I learned: 

•	How to bypass Django’s model framework and write custom SQL. 

•	How to connect Django with external DBs. 

•	How to write SQL queries to view and manipulate data. 

•	Some more jQuery tricks - $(this) – in particular. 

Some things I noticed:

•	There were a lot of VW execs at the hackathon, but I hardly saw them around. They seemed to be in internal meetings or sales pitches by IDEO. It seemed like the hackathon was almost a side event for them.

•	The winner of the hackathon was a conceptual idea to bring a new, simple UI/UX to the car that reacted to your mood and emotions. There was no real product. It was a thought out idea with a slick presentation and video (I think). It seemed atypical of a hackathon to reward an idea rather than an implementation, but the judges mostly seemed to be non-technical people. 

•	There was a whole night of just brainstorming and ideation, yet we were allowed to work on our real implementation. The IDEO people were moderating this, and their techniques and approach were remarkably helpful. 
