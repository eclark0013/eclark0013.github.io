---
layout: post
title:      "Coding Smarter, Not Harder"
date:       2019-10-17 19:37:07 +0000
permalink:  coding_smarter_not_harder
---

This second section of the Flatiron Software Engineering program went a little slower for me than the first. There was a period where I felt like I was getting hopelessly stuck again and again. This came to a head right before starting the Fwitter lab. I was doing a lot of coding because things seemed simple and then making mistakes and when I went to test my code's functionality there would be issues and I would be spending far too much time simply trying to figure out where exactly was the broken piece. I decided to use a different approach. Getting frustrated, I started to write code in shorter chunks and test it more frequently.

Practically, this has meant using binding.pry and tux more effectively. The Fwitter lab went significantly more smoothly than anything had in weeks and this shift has certainly helped me in this Sinatra project. I've been able to have a more focused scope on my errors which has meant better google searches and an overall more fruitful learning experience. 

For example, when I started this project, I quickly realized I was going to need seed data to be able to test functionality as I went. And I had a typo in my seed and had to reseed the database. Suddenly, very simple methods weren't working as I had anticipated. Before, I probably wouldn't have noticed this and would have already written multiple views and routes. Luckily I hadn't gone far so I knew that the issues had to be in my seed.rb. After a couple minutes using tux I realized that though I had removed the first seed data it was not restarting the id incrementation at 1. A quick google search and a gem later I was back on track using a database cleaner whenever I had to reseed the database.

With this new strategy I have created a Sinatra web application for rating items. Fairly straight forward, users can rate different items and see the ratings of others- not so different from the functionality offered by any online retailer, yelp, lyft, etc. One small difference that inspired the application's name, "comparatively," is that the score items receive takes into account the average score that user gives. If a user gives every lyft driver a 5, then giving a 4 would hurt that driver's score (regardless of where that driver is rated currently). If a user is a troll going around giving every movie on Rotten Tomatoes a 1, then rating their next selection a 3 would actually be a great compliment and would be reflected in that movie's score.
