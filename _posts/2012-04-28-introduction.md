---
layout: post
title: "Introduction"
description: "A simple introduction."
category:
tags: [about]
---

# Hi

This is the first post. Everything seems to be working
fine.

To keep everything as open as possible we have been told to publish our
full proposal to project.  

# Application - GSoC

My name is Maximilian Ludvigsson. I am a twenty years old Swedish student at 
Chalmers university of technology. I am interested in your organization as 
it is a combination of several of my interests. I have worked with programming 
and especially web development since an early age and I am looking forward to 
be able to combine that with biology.  

I view this summer as an opportunity to work with a scientific project and to 
be able to cooperate with people more experienced in the scientific environment.

I am able to work full time on this project during the entire timespan.

## Summary

Name:          Maximilian Ludvigsson   
Email:         max@invoco.se   
Technologies:  HTML, CSS, Javascript, .Net, Python.   


## Project

I will be building a web interface for letting users annotate information on the 
various plugins in BioGPS. This classification is then added to the html markup 
of the plugin with injected javascript. After an initial annotation, the other 
pages for that particular source is automatically annotated. 

At the end of this program, a user should be able to annotate websites. This 
annotation is then saved on the server and is inserted in the HTML with javascript 
injected in the plugin/website.

### User workflow

A user of this system should follow a workflow similar to this:

1. The logged in user chooses a website from a list of the available plugins.
2. The website is opened in an iframe.
3. The user uses the mouse to select an element on the page (similar to 
  how you select elements in chrome dev-tools or firebug).
4. The user is presented by a list of classifiers, one or several is chosen.
5. Repeat step 3 and 4 until the user is satisfied with the classification.
6. The user is able to search for other genes on this particular website to verify 
  and add/edit classifications.

### Implementation

The implementation of this system is primarily going to use javascript,
with a backend for saving the annotation rules.

### Steps

The big steps required to finish this project are:

* Javascript to allow the user to select a certain HTML element
  and get a selector for that element to identify it later.
* A form in a modal, or similar, that saves an element’s selector together 
  with the chosen annotation.
* A backend that saves the selector and the annotation (with django?).
* Javascript that receives element selectors and the corresponding annotation, 
  and inserts the annotation in the HTML markup.
* An interface to verify that a site has the proper annotation. Especially across
  different pages on the same site.

Additional feature that is outside the basic functionality:

Make the site notify if the HTML markup of a notated site has changed, 
demanding an update of the notation.

### Timeline

For achieving this plan I divided the eight weeks in the following steps:

#####First week
Design and prototypes.
#####Second - third week
The element-selector and save form.
#####Fourth week
The backend.
#####Fifth week
The javascript to insert the annotation into the page.
#####Sixth - seventh week
Interface to select different genes on the same page and to verify proper 
annotation. Create notification functionality if there is time.
#####Eighth week
Final fixes and optimization. 


## Qualifications

I am currently an engineering student at Chalmers university of technology with physics 
as my major. I am interested in the combination of math, technology and biology, my plan 
is to choose a master with a biology profile. I think that working with your organisation 
is a great opportunity to further develop these interests. 

I have taken two programming courses on university level, one in python and one in java, 
but my experience is mostly from my own web projects. I have been programming since my 
early teens, mostly web pages in microsoft's .Net-stack (before that: classic ASP) and 
I have done professional work in this area. I later switched more or less to open source 
and linux.

I have extensive experience in HTML and CSS. My javascript experience consists mostly 
of smaller jQuery scripts but it is constantly growing and I have recently been studying 
backbone.js to learn good patterns for building larger javascript applications. I have 
also been looking at node.js, mostly for fun.

It is unfortunate that I don’t have more examples of my work as it mostly consist of joint 
work with my past employers. I am however confident that I am able to finish this project 
as it is well in the reach of my current expertise. I also hope that this could be a 
starting point for me to get more involved in the open source community.

I’ve recently done a website for a Swedish gymnastics association (http://www.lingforbundet.se). 
The page is built from scratch and is featuring a content management system I built with 
javascript against an API. 

Other projects I have been involved in includes a web based order management system for 
a company (http://www.fmktrafik.se). 