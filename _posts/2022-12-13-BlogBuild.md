---
layout: post
title: My blog stack
comments: true
---

What is the point of building a blog if I dont get to talk about the tech stack.

# Intro
This is a _mostly_ static website that is hosted on github and built by jekyll. It is fairly easy for blogging and I wanted to outline the lessons I learned. 

# Writing posts
I use an app called [Joplin](https://joplinapp.org/) that uses dropbox to sync my phone and PC notes. I write a lot of my blog posts on a phone, then edit and square away on the PC. Joplin allows me to do this seemlessly, oh and did I mention it renders markdown?! SO I just write in markdown, joplin shows me a preview and I can hop onto my pc to edit and review. 

# Posting
I run VS code to edit my code. This was needed for the setup, but is also a decent text editor that can also render markdown. I just move my joplin notes to VS code. Importantly I have VS code linked to my github page that (spoiler alert) hosts this whole site. So I can just push my changes to master if I am happy with them. 

# Previewing
Importantly I like to be able to preview my webpage before posting it live. I installed Jekyll locally on my PC so that I can render the site locally on my localhost. I preview it before commiting my changes and pushing it into github. 

# Hosting
The Jekyll on my computer is not needed really. Jekyll runs within github, so when I make a change to my master branch the webpage is automatically already created. 

# Themes
Worth noting that I wanted math added to my page so I had to change the jekyll theme to minima.

# Comments
I linked my pages to disqus. THis allows me to add comments!

# Subscribe
I wanted an email subscriber. I added mailchimp to the jekyll layout of all my posts. THis is actually a huge weakness right now. I would love a methodology of sending my subscribers an email once I add a new post but right now that is manual. I need to look up my subscriber list and create an email.

# to be continued...