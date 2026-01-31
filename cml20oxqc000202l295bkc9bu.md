---
title: "Emmet for HTML: A Beginner’s Guide to Writing Faster Markup"
datePublished: Sat Jan 31 2026 07:55:34 GMT+0000 (Coordinated Universal Time)
cuid: cml20oxqc000202l295bkc9bu
slug: emmet
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1769846032392/6087e2f8-dbb5-4b95-aa73-37bf4726963c.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1769846116485/d968d3b1-4b2f-44a3-ad21-ca402819ff2b.png
tags: hiteshchoudharylco, hiteshchaudhary, chaicode, chaicohort, khaliddev

---

## Introduction

Gone are the days, when programmer used to write HTML inside notepad and saving the file witth `.html` extension. It was working finely in those days.

But, hey we are human. When we master something we get bored, we want something new attractive and fancy and automated. So, yahh we build a plugin by the name of Emmet.

Emmet is a code shorthand system and nowadays it is built inside the code editor like Vs Code, Sublime Text and other.

## 1\. What Emmet is (in very simple terms)

Like a told u emmet is a plugin, a code shorthand system, a stick of magic, that can predict the whole code just by matching the pattern of your incomplet code.

But, here is a caveat. We know Browser understand HTML, so a questions can arise does brower know this html is written by a plugin called Emmet.

And, the answer is a “BIG NOOO”.

Because, HTML only helps in writing code faster, but at end of the day it gives us same pure HTML with no fancy addition. So, browser only reads that plain html code.

## 2\. Why Emmet is useful for HTML beginners

To answer this questions, i hope you already know 40-50% of the answer.

It is useful for the beginner, because a beginners finds it difficult to write the opening tag closing tag and repeating the same tags again and again. And, a small mistake can ruined all the code and Emmet is just not useful in writing HTML only. It help in writing CSS, JS, Python and any other programming language.

So, emmet is a life saving plugin, it autowrite the code. So, this feature motivate the beginner to experiment and understand the best writing practice by looking at the auto-generated code template.

Beginner dont have to worry about all those opening and closing tag in HTML, wrirting key and value in CSS etc.. and worring about presentation, readibility of code all of these can be done by Emmet it works perfectly for indentations.

So, yes it is quite helpful and useful for the beginners.

## 3\. How Emmet works inside code editors

Inside the editor it works very smoothly. I will tell you only examples to make you understand.

if you write `header` and click tab or enter. You will have `<header></header>` written.

if you write `p` and click tab or enter. You will have `<p></p>` written.

if u write `section` and click tab or enter. You will have `<section></section>` written.

if u write `div` and click tab or enter. You will have `<div></div>` written.

See, it is making task easier in writing HTML.

## 4\. Basic Emmet syntax and abbreviations

In this section i will tell you all the syantx and abbreviations which i learnt while doing research for Chaicode.com task.

### Creating HTML elements using Emmet

I have already told you how when you just write the name of the tag it gives you whole element.

`html —→ <html> </html>` `body ——> <body> </body>` `header ——> <header> </header>` etc…

### Adding classes, IDs, and attributes

In html we add Class, ID and Attribute to the tags. Class and ID is helpful to target element while adding style to it. And attribute is where we give more roles to the HTML elements.

Lets see how it will work:

1. ***To Add Class :***
    
    `div.container ——→ <div class = “container”> </div>` , `section.nav ——→ <section class = “nav”> </section>`
    

So to add class, after tag name put dot(.) and class name it will automatically reflect the code the way i have written above.

Note: A single class can be alloted to many tags but ID is unique.

2. ***To Add ID :***
    
    `div#container ——> <div id = “container“> <div>` , `section#nav2 ——> <section id = “nav2”> </section>`
    
    So to add ID, after tag name put hastage(#) and ID name it will automatically reflect the code the way i have written above.
    
3. ***To ADD Attributes :***
    
    `img[ src = “img.png” alt = “Image”] ——→ <img src = “img.png” alt = “Image”>`
    
    So to add attribute, after tag name put square bracket \[\] and attribute name it will automatically reflect the code the way i have written above.
    
4. ***To Create Nested Element :***
    
    `header>ul>li ———> <header> <ul> li></li> /ul> </header>`
    
    So to create nested element we use angular bracket &gt; that add the inside features to tags coming after it. So, it becomes the child of the first element.
    
5. ***To Repeating elements using multiplication:***
    
    `header>ul*3 ———> <header> <ul>/ul> <ul>/ul> <ul>/ul> </header>`
    
    So to create multiple element we multipy the tags uisng (\*) symbol.
    
    ## 5\. Generating full HTML boilerplate with Emmet
    
    Boilerplate is the fundamental structure of the HTML code file. It can be created with Emmet with a shortcut.
    
    Juts type ! and hit tab or enter.
    
    ```plaintext
    <!DOCTYPE html>
    <html lang="en">
    <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <title>Document</title>
    </head>
    <body>
    
    </body>
    </html>
    ```
    
    This boilerplate follows modern standards and is exactly what you should start with every time.
    

## Final KeyTakeaway

Emmet is a plugin, a code shorthand system that helps to write code faster, correct and optimised in visual sense.