---
layout: post
title: "Pointer Events"
description: "How the pointer events is used to disable mouse events."
category: 
tags: ["pointer-events", "css", "inspector", "firebug"]
---

# Creating an inspector

As the point of this project is to point out specific DOM elements that needs
to be annotated. The most natural way of selecting these elements is with an 
"inspector" such as the one you select elements with in firebug or chrome dev-
tools.

To create this inspector I used a div-element as a mask and set its width and 
height to match the currently hovered element. Something like this:

{% highlight javascript %}
$(document).on('mouseover', function(e) {
  var w   = $(e.target).width(),
      h   = $(e.target).height(),
      pos = $(e.target).offset();

  $('.highlighter')
    .width(w)
    .height(h)
    .offset(pos);
});
{% endhighlight %}

The problem with this approach is that when the mask is covering a large element,
say a table, the mask (which is in front of the table) is preventing the mouseover 
event to fire on any element below it, say a td-element.