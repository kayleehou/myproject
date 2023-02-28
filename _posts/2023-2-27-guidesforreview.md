---
toc: true
layout: post
description: Using Jinja2 for more efficient Coding 
categories: [markdown]
title: Tri 2 Guide for Review- Using Jinja2
comments: true

---
# Problem 
![](https://github.com/kayleehou/myproject/blob/master/images/review1.PNG?raw=true)
I had a very inefficient way of creating the html product cards on my website. I had to hard code all the cards with copy and paste. This wouldn't be efficient if say I had a 100 dogs, it would take forever to copy and paste all the information and fill it out for each dog. I started researching ways to create a loop that would generate the cards for me instead. 

This youtube video was very helpful: [Using Python and Jinja to create an HTML Webpage](https://youtu.be/9v6kDoUjIs4)

# What is Jinja2
- web template engine for the Python programming language.
-  Python library that allows us to build expressive and extensible templates

# How I Implemented Jinja2:
1. I downloaded Jinja2 in my terminal
2. I created JSON file called dogs.json with my data in it. 
3. Then I created a HTML file (stub.html) that held my keys from the json data in the product card HTML like this:
![](https://github.com/kayleehou/myproject/blob/master/images/review3.PNG?raw=true)
4. Then I made a Python file called app.py which imports Jinja and loads the data from dogs.json into the code from stub.html. 
![](https://github.com/kayleehou/myproject/blob/master/images/review9.PNG?raw=true)
Then after you run the python file, it generates a new HTML file called page.html with that creates all the div cards for you:
![](https://github.com/kayleehou/myproject/blob/master/images/review4.PNG?raw=true)
5. Then I wanted to do something similar with the learn more links, instead of having to code twenty different files that had twenty different tables for more info on the dogs, I created an HTML file with the Jinja2 syntax to create a HTML table:
![](https://github.com/kayleehou/myproject/blob/master/images/review5.PNG?raw=true)
In my learn.py file I created a dictionary that stores all the different urls that have the raw json data: 
![](https://github.com/kayleehou/myproject/blob/master/images/review8.PNG?raw=true)
I also created a for loop that would loop through the links based on the button clicked:
![](https://github.com/kayleehou/myproject/blob/master/images/review10.PNG?raw=true)
6. When you run learn.py you get 20 files:
![](https://github.com/kayleehou/myproject/blob/master/images/review6.PNG?raw=true)
7. Finally, you need to change your main.py file so that your work shows up on your website when you type in the link 
![](https://github.com/kayleehou/myproject/blob/master/images/review7.PNG?raw=true)

# Final Result 
After some more styling and pulling, it showed up in my deployed flask like this: 
![](https://github.com/kayleehou/myproject/blob/master/images/review2.PNG?raw=true)
When you click the learn more button, it shows the info in a table for that specific dog like this: 
![](https://github.com/kayleehou/myproject/blob/master/images/review11.PNG?raw=true)

# Last Thoughts
- Being an efficient and laser coder is very important, I will definitely be using Jinja2 for whenever I have to repeat HTML elements over and over again :)
