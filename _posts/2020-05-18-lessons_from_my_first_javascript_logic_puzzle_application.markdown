---
layout: post
title:      "Lessons from a Javascript Logic Puzzle Application"
date:       2020-05-18 13:51:29 -0400
permalink:  lessons_from_my_first_javascript_logic_puzzle_application
---


I’ve been working on a nonogram puzzle game interface called Nonogrammit. It’s set up as a single page application with backend Rails and frontend Javascript. Being my first JavaScript project, there were a fair number of bumps in the road. There are three major lessons I hope to not need to learn twice:

1. Manipulating the DOM using Javascript with containers
2. Blocks vs. Grid in CSS
3. Keeping the backend simple



**Manipulating the DOM using Javascript with containers**

Containers are a beautiful thing. It’s easy for me to start running along in a project without them and then suddenly realize I’m trying to balance a couple dozen divs and make sure they all are created in the right order (more on that in my second point). Containers are a simple step to move things in the right direction. This is a simple step towards organization that has a huge payoff. No more folding my clothes and leaving them in piles on the floor. I got a wardrobe, and it’s life changing.



**Blocks vs. Grid in CSS**

I don’t generally think of myself as stylistically-minded, so CSS has not always been my friend. In this project, I ran into some difficulty as I tried to move through my project with a stiff layout full of blocks and inline-blocks.

After significant difficulty formatting where small edits were repeatedly having unintended effects downscreen, I decided to move into using a grid template. I considered flexbox– however, the puzzle set up, being so angular, lended itself well to a fairly clear and concise grid layout. 

```
html body{
   height: 100%;
   display: grid;
   min-width: 780px;
   grid-template-columns: minmax(100px, 10%) minmax(15px, auto) min-content max-content min-content minmax(15px, auto) minmax(100px, 10%);
   grid-template-rows: auto minmax(80px, auto) minmax(300px, auto) min-content 70px ; 
   margin: 0px;
   text-align: center;  
   background-color: floralwhite;
}
```

At first, I was trying to add containers in the right order and had to be very careful about making sure they lined up correctly. The minmax on the columns allowed me to keep a buffer between the puzzle and the menu bars. (When the screen gets too small, it switches to scroll.) The min-content and max-content ensure that the puzzle squares and parameters are aligned nicely. And my favorite part is that when I am ready to set it up to add in an option for row parameters on the right side and column parameters on the bottom, I will simply add a container to the appropriate grid location and it will be ready to go.


**Keeping the backend simple**

I had started with plans to create a database with Puzzles that have many Columns and have many Rows. Then those Columns and Rows would have squares which would each belong to a Row and a Column (and with 25 rows and columns that comes to a total of 625 of these squares). I quickly realized that I was firing an inordinate amount of SQL requests that was totally unnecessary. To simplify this, I set up just Puzzles and Users and then those puzzles contain a solution that should be shaded in (an array of coordinates) and row and column params (a string of integers). Then I added a game class to connect the two and contain information like time and completion status.

I’m looking forward to adding many more features (ability to mark definitively non-shaded squares with an x, highlight params for row and column when you hover over a square, users saving progress on puzzles), but I’ve reached a good pausing point. I’m happy with it and ready to play!

