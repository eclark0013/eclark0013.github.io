---
layout: post
title:      "My First Project #the_joy_of_scraping"
date:       2019-07-15 12:52:41 +0000
permalink:  my_first_project_the_joy_of_scraping
---


For four years I have been on the other end of this education game. And thand God for that! I've had to tell so many students to cintinue to persevere that it's become suprisingly easy to do so myself. On this (my first) project, that meant scraping and re-scraping to perfection. 

The requirements of this project were to create a CLI that will provide access to data from a web page based on user input using well-implemented object-oriented programming.

I decided to make a CLI that would retrieve data on candidates for the 2020 Democratic Presidential Nomination. Going into this project I felt like I had a pretty solid grasp on variable scope and using classes, certainly still making mistakes, but at least getting to the point where I find it and know it's a mistake instead of finding and googling why this might be a mistake.

Anyway, that simply meant that my big struggle would be the scraping. At the weediest point, that meant a couple hours trying to pull out a particular row off of a table in wikipedia with the same row title but in a different spot depending on the website requested. It took me at least an hour to get it right in this messy form:

```
def find_education
    @doc.css("tbody tr td a").each do |link|
      if ["niversity", "ollege"].any? {|word| link.text.include? (word)}
        @education << link.text
      end
    end
  end
```

And this was so rough (and lost the degree designation, like BA or JD). Only looking for links in the table that happened to have most of the word University or College. But what took me an hour at first came so much easier by the end, and cleaner. After creating a few other scrapers, I cam back to this and realized I now new how to go down the HTML one level at a time as necessary and then come back up for what I needed and what had taken an hour to create a mess took 5 minutes to create something much, much prettier. 

```
  def find_education
    @doc.css("tbody tr").each do |tr| #makes a list of each link text under education (including degree designations)
      tr.css("th").each do |th|
        if th.text == "Education"
          tr.css("td a").each do |link|
            @education << link.text
          end
        end
      end
    end
    @education.each_with_index do |school,i|
      if i > 0 && school.length < 5
        @education[i-1] = "#{@education[i-1]} (#{school})" # adds on their BA or JD designation to that school
        @education.delete(school) # removes their BA or JD designation as a separate school
      end
    end
  end
```

Through this, I found the joy of scraping. And I'm looking forward to continuing to sharpen the skills. Overall, I'm thrilled with how this first 1/5 of my flatiron experience has gone and eagerly await the next challenge ahead!


