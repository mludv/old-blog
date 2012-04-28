---
layout: page
title: Maximilian Ludvigsson
---
# Hi, <small>my name is Maximilian Ludvigsson.</small> 

I am selected to the 2012 Google Summer of Code and this blog is supposed to
document my project. I work with the [Crowdsourcing biology](http://sulab.org/research/crowdbio/)
project.
    
# Posts

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; 
    <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
