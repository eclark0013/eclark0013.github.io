---
layout: post
title:      "My First Project #the_joy_of_scraping"
date:       2019-07-15 08:52:42 -0400
permalink:  my_first_project_the_joy_of_scraping
---


For four years I have been on the other end of this education game. And thank God for that! I've had to tell so many students to persevere that it has become suprisingly simple to do so myself. On this (my first) project, that meant scraping and re-scraping to perfection. 

The requirements of this project were to create a CLI that would provide access to data from a web page based on user input using well-implemented object-oriented programming.

I decided to make a CLI that would retrieve data on candidates for the 2020 Democratic Presidential Nomination. Going into this project I felt like I had a pretty solid grasp on variable scope and using classes– certainly still making mistakes, but at least getting to the point where I could read the error message and know how it happened instead of searching google to understand why this might be a mistake.

Anyway, that simply meant that my big struggle would be the scraping. At the weediest point, that meant a couple hours trying to pull out a particular row off of a table in wikipedia pages conatining the same row title but in a different spot depending on the particular page requested. It took me at least an hour to get it right in this messy form:

```
def find_education
    @doc.css("tbody tr td a").each do |link|
      if ["niversity", "ollege"].any? {|word| link.text.include? (word)}
        @education << link.text
      end
    end
  end
```

This was so rough (and it lost the degree designation, like BA or JD). It was only looking for links in the table that happened to have most of the word University or College. But even this was an accomplishment. After creating a few other scrapers, I cam back to this and realized I now knew how to go down the HTML one level at a time as necessary and then come back up for what I needed and what had taken an hour to create poorly took 5 minutes to create cleanly. 

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

Through this project, I found the joy of scraping and solidified many of the ins and outs of object-oriented programming. And I'm looking forward to continuing to sharpen those skills. Overall, I'm thrilled with how this first 1/5 of my flatiron experience has gone and eagerly await the next challenge ahead!


