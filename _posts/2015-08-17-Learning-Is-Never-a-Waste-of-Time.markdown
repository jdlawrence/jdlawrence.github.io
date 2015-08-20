---
layout: post
title:  "Learning is Never a Waste of Time: My Experience with Backbone.js"
date:   2015-08-17 18:00:00
categories: learning Backbone.js
---
5 Hours. Reconstructing most of 10 files of an application. Painfully writing approximately 50 lines code. This is what
I recently spent my time doing while attempting to add a feature written largely using the Backbone.js framework. 
My team's application is a music player, and I was trying to implement a feature that when a song finishes playing, if 
there are other songs in queue after the current one, the next song is automatically be played. The actual player 
is an HTML5 element, and from documentation I determined that when a song ends, the player fires of an 'ended' event. 
Tracing this the propogation of this event and how it was handled sent me on a journey full of learning.

Backbone.js is not very strict in the way it enforces many things, but this particular codebase I was using listens to 
events in a view. Upon detecting an event, the view calls a function on its model. The model emits a different event 
which is listened to by a collection. The collection removes a model from its storage, and calls another function. If
this sounds convuluted, it is! Then came the kicker: all of this was unnecessary. The functionality I was looking for 
was buried right inside of the html controller.

I could have looked at this process as an exercise in futility, but instead I chose to think of it as a great learning 
opportunity. I have a much deeper understanding of the event handling process of Backbone.js as well as the relationship
between models, views, and collections. Some might fail to realize the value of this exercise because my initial goal was 
so easily achieved, but I chose to believe that every experience has something to teach me, regardless of outcome.


[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help