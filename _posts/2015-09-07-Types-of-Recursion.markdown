---
layout: post
title:  "Types of Recursion"
date:   2015-09-07 13:30:00
categories: recursion algorithms
---

Recursion is very frequently a topic that baffles those who are new to computer science principles. What many people don't 
realize is that there are actually several different types of recursion.  My aim is to provide you with a brief introduction
to each type.

Linear recursion calls itself once per function call, and the number of calls increases directly (linearly) in proportion to 
the number of objects in the collection of the problem. Although it is not a common use for recursion, counting and printing
out the numbers from 0 to n is an example of linear recursion.

Tail recursion is a special case of linear recursion. In tail recursion,  each recursive call does not need knowledge of its position in the call stack. In other words, each call is independent and the final output value is not calculated from all the previous calls, but only from the one on top of the stack. The Javascript function below to find a greatest common denominator is an example of tail recursion.

{% highlight js %}
  //INPUT: Integers x, y such that x >= y and y > 0
function gcd(x, y){
  if (y == 0)
     return x;
  else
     return gcd(y, x % y);
}


{% endhighlight %}

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help