---
layout: post
title:      "React/Redux Project: BookLister"
date:       2020-11-09 20:21:40 +0000
permalink:  react_redux_project_booklister
---


My final project for this Full Stack Web Development program is a library organizer application that focuses on adding library objects to one or many lists. In some ways, this is simply setting up the ability to create objects and tag those objects. I’ve added a bit more, though, for expansion in the future and to meet the project requirements. Let’s go through some of the basic features and where I still plant to work and let this thing grow after submission.

Basic features and frameworks:
* **Creating and accessing objects**: The application is set up to allow you to create new books which will automatically be added to the “All Books” list. You can add notes and images to the books. Those books are then accessible by going to the page for any list that contains that book (which will always be at least the “All Books” list in addition to through the “All Books” dropdown tab on the navbar.

* **Creating and accessing lists**: Beyond just being a simple application with CRUD capabilities on one type of object, the books can be added to lists. The idea of this app is that you can creatively organize and track your books by adding them into lists. Notes can be added to these lists. All the different lists can be viewed on a single page and are accessible by the dropdown menu in the navbar. These lists can be expanded in the future to be connected to users to allow sharing.

* **React/Redux features**: This is my first project using the React/Redux frameworks. Overall, I get how these are somewhat magical and can allow for a lot of quick web development but there is so much going on behind the scenes that it can become a bit tricky to troubleshoot at times. That being said, I’m happy to have been pushed to learn it.

* **Container components**: To fulfill the requirements of this project, I have used container components to collect and organize the bootstrap cards that are found in the all lists page (with list cards) and in each individual list show page (with book cards). In some ways, this has felt a bit superfluous, but I can definitely see the merit in organization. There is some clarity to the program that I think allows for simpler communication of how the app is functioning.

Some struggles and features to build out in the future:
* **Users**: I had originally set up this project to incorporate users and have those users own lists and maybe even be able to share those lists with others, setting up the possibility of a platform that could handle some social interaction. As it went on, I decided to scrap it for the time being, but many of those ideas are still sitting in my head in seed form and germinating– users owning lists, lists having owners and viewers (based on the user who created the list), allowing varying abilities of editing for viewers (maybe they can add objects to a list but not delete them?), etc. We’ll see what comes of it.

* **Error handling**: I would certainly like to clean up some possible vulnerabilities and better handle errors. I made it a focus of my work in the Javascript project but I tried to spend this project simply getting a strong handle on React components, using the Redux store effectively, and simple Bootstrap. As far as user experience is concerned, I would certainly like some more explicit error handling. Something for after submission.

* **Autocomplete**: So the easiest way to add books to a list or to modify the lists to which a book should belong would have been some sort of checkbox form. However, I wanted to take this a step further than simple checkboxes and also make it a little more real to what one would expect from a decent user experience. So I started using Autocorrect components. It’s had its ups and downs. Definitely a learning experience, and one that should bear fruit in the future. These components look clean and are very user-friendly.

And with that, after many months of chipping away on this project, it is finally complete and ready for submission! Thank God!

