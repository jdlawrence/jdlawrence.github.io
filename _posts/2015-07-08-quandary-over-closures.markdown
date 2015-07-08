---
layout: post
title:  "A quandary over Javascript closures"
date:   2015-07-08 08:00:00
categories: javascript closures
---
On my journey to becoming a programming Ninja (I've still got a long way to go), one of the topics that has caused me confusion and curiousity is closures. While I am far from a Ninja in any language, I've had a fair amount of experience programming in Java. However, in my limited experience, I didn't run across closures in Java, and the concept was initially very baffling. Wikipedia defines a closure as `a technique for implementing lexically scoped name binding in languages with first-class functions.` So what exactly does that mean?

I'm big on analogies, and so I'm going to describe one that helped me. Let's imagine that you are function:

{% highlight js %}
var me = function() {
}
{% endhighlight %}

Let's add certain qualities to yourself. We'll add your height, your weight, and attractiveness as personal properties:

{% highlight js %}
  var me = function() {
  var height = 74;
  var weight = 220;
  var attractiveness = 9;
}
{% endhighlight %}

Let's say that you have the ability to view these personal properties. You can recall your height (`myHeight`), your weight (`myWeight`), your attractiveness (`myAttractiveness`).

{% highlight js %}
var me = function() {
  var height = 74;
  var weight = 220;
  var attractiveness = 9;

  var myHeight = function() {
    return height; 
  };
  var myWeight = function(){
    return weight;
  };
  var myAttractiveness = function(){
    return attractiveness;
  };
};
{% endhighlight %}
The three functions, `myHeight`, `myWeight`, and `myWeight` are all closures. They are inner functions of `me` and therefore they have access to all of `me`'s variables.

Now this function `me` is snapshot of you at a certain time. It has a lifetime on the memory stack, but once it's been snapped and it's no longer on the memory stack then you no longer have access to the personal properties that were part of `me`. You might be wondering what all the fuss is over closures. Other languages like Java have inner functions that do this same functionality, so what's so powerful about a closure?

A big part of the real power in closures is a side effect that gives them the ability to access the outer function's variables even after the outer function has returned. Consider that a function has a lifetime where it lives on the stack in memory. Normally once that function has returned, the function's properties are inaccessible. However a closure gives you access to the functions properties AFTER it has returned. This is magical!

To continue our analogy, think of a function's lifetime as a picture. Once that picture of you is taken, you cannot change the properties of yourself. What if we had a way to change one of these properties? Let's add a function that does this called `makeMeBeautiful`.

{% highlight js %}
var me = function() {
  var height = 74;
  var weight = 220;
  var attractiveness = 9;

  var myHeight = function() {
    return height; 
  };
  var myWeight = function(){
    return weight;
  };
  var myAttractiveness = function(){
    return attractiveness;
  };

  var makeMeBeautiful = function(){
    attractiveness += 0.2;
    console.log("My attractiveness is now a " + attractiveness);
  };

  return makeMeBeautiful;
};

{% endhighlight %}


Our `me` function now returns the `makeMeBeautiful` function. We can assign this function to a variable, `aMoreAttractiveMe`, and when it's called, our attractiveness increases! This is essentially taking a picture of yourself, going back into time, and changing the properties of yourself. 

{% highlight js %}
var aMoreAttractiveMe = me();
aMoreAttractiveMe(); // Outputs "My attractiveness is now a 9.2"
{% endhighlight %}

The `me` function returns a function that is assigned to `aMoreAttractiveMe`. Whenever this function is called, although `me` has long since returned, the `attractiveness` variable inside of the `me` is still able to be increased. It will keep increasing for as many times as you call it.

Hopefully this analogy has given you a useful viewpoint on closures. They are used very frequently in Javascript and its powerful libraries such as jQuery. Go forth and use closures!

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help