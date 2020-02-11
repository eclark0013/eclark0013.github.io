---
layout: post
title:      "First Rails Project: Tough but Rewarding"
date:       2020-02-11 21:30:47 +0000
permalink:  first_rails_project_tough_but_rewarding
---


I just completed my first rails project: a recipe and grocery list database that can create lists by adding recipes and/or individual items.

I found myself repeatedly running into walls with this project. I was warned when I started working with rails that there was a lot of "magic". I could see this in small ways while I was laerning the basics of it but only in a real sense when I started working with thr project. Let me go through a few of the challenges:

Scope: I found myself multiple times defining methods that were not accessible to the object that were calling them. I think this is just because of the size of the project and having to remember details such as items having a name in the database but no quantity, whereas additional items have a quantity but no name. I certainly could have been more precise at different times.

Refactoring controllers: I have come to appreciate a "skinny" controller. Before refactoring, those controllers were *disgusting* but moving that logic over to the model with simple methods in the controller... mmm... so beautiful. There were certainly challenges to have all the relevant data accessible to those instance methods, but they were well worth the pay off of turning 20 lines of code into one concise and well-named method in the controller.

Partials: I ran into some difficulty rendering partials within my views- primarily with sending locals to the partial in the context of forms. This was my first time doing this and much like refactoring controllers, the payoff was sweet.

As I move forward in the future there are definitely some improvements to be made on future projects. 
1. Though I did a lot of planning beforehand on how Lists, Items, and Recipes would be associated those plans had to be scrapped multiple times and I wish I had spent much longer in the beginning doing that planning and trying to consider what features I will want each class to have. 
2. I also want to add in a few gems and see how they may ease my load (on the front of my mind now is Devise).
3. Find ways to refactor throughout. It's not that I'm unsatisfied with the DRYness of the code, but I think it could be better if I had been refactoring controller logic into models and creating view partials throughout instead of saving a lot of that work until I was reaching the end.

All in all, a great start and I'm looking forward to my next Rails project. (And maybe continuing to work on this one...)
