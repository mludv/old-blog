---
layout: page
title: Maximilian Ludvigsson
---
# Hi, <small>my name is Maximilian Ludvigsson.</small> 

I am selected to the 2012 Google Summer of Code and this blog is for
documenting my work. The organization I work with is [Crowdsourcing biology](http://sulab.org/research/crowdbio/).
    
# Posts

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; 
    <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
