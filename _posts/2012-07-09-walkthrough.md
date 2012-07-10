---
layout: post
title: "Walkthrough of the project this far"
description: "A walkthrough of the project this far"
category: 
tags: [semantic-biogps, biogps, walkthrough, guide, annotation, biology, semantic web, tutorial]
---

Mid-term
========

I am halfway through the project and the mid-term evaluation is coming up.
As the project is proceeding well I thought that this would be a good
time to walk through the website and show what has been done this far.

The prototype is hosted at [50.112.124.237](http://50.112.124.237/) if you want to try it for yourself.

URL Picker
----------

![ Screenshot of the URL picker ](/images/screen-first-page.png)
_The first thing that hits the user when navigating to the page._

The first thing you see when entering the prototype is the URL picker.
The drop-down list contains a list of URL templates or bioGPS plugins. 
In combination with a gene ID we are able to get an URL to a website.

You can also press one of the example URLs that I have listed. I chose 
"Protein Atlas" for this demo, as it is developed at the other large technical
university here in Sweden (damn you KTH).

(Note: sometimes, the selected URL will load forever, without a loading indicator on 
the browser window. This is when the bioGPS web-service don't answer. For now: 
just reload the page.)

Please note that I haven't tested all of these URLs and there are a few that
aren't working properly. However, as long as they are somewhat standard and don't
depend on a lot of javascript or flash to work there shouldn't be a problem.

Annotating
----------

![ Screenshot of Protein Atlas ](/images/screen-annotation.png)
_On a site, ready to annotate._

After a URL is chosen you will be taken to that site and be able to do annotations.
An annotation is a specific part of the page that contains some content. The
elements that have a blue border are parts of the page that already has annotations on
them and the red highlight is following the mouse.

When the red highlight is highlighting the part of the page which you want to
annotate (in this example: the description) you click and a form appears where
you can enter information about the content:

![ Screenshot of an annotation view ](/images/screen-open-annotation.png)
_How it looks when you are adding or editing an annotation._

(Note: Due to a recent change, the form doesn't work correctly when you scroll, 
this will be fixed soon.)

Some functionality that is waiting to be implemented here are:

+ A toolbar fixed at the top with a title and a couple of navigation links.
+ The _gene attribute_-field is going to have an auto-complete function so that
  you can see similar annotations that other users have used.
+ You will be able to annotate the same part of the page (same element) with different
  kind of annotations multiple times. You can only change old annotations right now.
+ There will be some kind of security so that a malicious user can't destroy anything.

Anyway, I annotated the description, hit save and the annotation was saved on the server.

Verify the annotation
---------------------

The next step is to check how that specific part of the page looks like on other pages
at the same server. For example, you are on the page for gene 1017 and want to check what the description
is for gene 1015 and 1050. This is to verify that the annotation works somehow correctly at
other pages as well.

You can check manually by entering a different gene at the address-bar, or you can go to a
page which automatically fetches the content from different pages and presents it to you.

There isn't a link to this page yet, so for now just change the _gene/{geneid}_-part in the URL to
_verify_, for example, this:

    http://50.112.124.237/#url/200/gene/1015

to this:

    http://50.112.124.237/#url/200/verify

Navigate to this URL and note that it will load for awhile, don't make any reloads. That will only make it take longer. When it is finished, our new annotation and the content for a few different genes will appear:

![ Screenshot of the verification view ](/images/screen-verify.png)
_The screen that shows the annotation content for different genes._

This page is for now quite slow as the server fetches the different pages on request and searches them for the content. When some kind of cache is in place and if the server
gets a little more processing power this will be faster.

It is also going to be more interactive. You should be able to edit annotations directly
from here and to change which genes it fetches.

Conclusion
----------
This was basically everything. It has been great this far and I've learned a lot.
And please, all feedback is valuable, especially on how it can be more useful as
I don't really have the insight in how this will be used!

Thanks,  
Max