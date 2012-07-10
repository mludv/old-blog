---
layout: post
title: "Creating a proxy"
description: "Working around the same origin policy"
category: 
tags: []
---

# The same origin policy

The first challenge in this project was to get around the "same origin policy".
This policy permits scripts and web documents on the same domain to access 
each others methods and contents, but prevent access to pages that originate 
from a different website.

As the annotation interface I am building needed to access the HTML of another 
server I couldn't just put the URL in an iframe, access it with javascript
and start with the annotation code. I had to serve their website from my
server. 

As I am using node for my server I found a library called [node-http-proxy](https://github.com/nodejitsu/node-http-proxy) on github. Although it looked really feature-rich and stable, it did by default serve on a different port than my node server. I was unable to use it as different ports are equal to different domains. 

# The solution

I decided to build my own proxy solution. I used a library called [request](https://github.com/mikeal/request) that made web requests with node really simple. All it took to stream content from an [express](https://github.com/visionmedia/express)-route was one line of code

    function(req, res) {
      request("http://url.com").pipe(res);
    }

I wired it up to serve another page if the server found a query string with the
name _proxy-url_ in the request. This worked good enough with the initial html-page. All requests for images and stylesheets by that html-page was not found
as those request didn't have the _proxy-url_ query string in the url. 

I installed [node inspector](https://github.com/dannycoates/node-inspector), 
an awesome debugger for node, and discovered that the _req_-object had a property called _headers.referer_ containing the url from where the current request originated from. I extracted the query string from this url and passed on any of these requests and boom, I had a working proxy.

After I had put up some tests to make sure everything was working correctly I made a bit of refactoring and was able to put everything in a [connect middleware](https://github.com/senchalabs/connect). This way it is easy to put
the proxy-part of this project in a node module and open source it by itself, after I have got some whitelists and other functionality in place.
