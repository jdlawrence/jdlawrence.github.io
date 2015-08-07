---
layout: post
title:  "Becoming Efficient at Toy Problems"
date:   2015-08-07 18:00:00
categories: toy problems
---
Toy problems are brief exercises that emphasize formulating a quick solution to a task. They are questions 
that an employer might ask for an interview such as writing a sorting algorithm, string manipulation and/or
concatenation, and implementing mathematical functions. Here are some tips for becoming more efficent
in toy problems.

1) Formulate an idea and RAPIDLY test it as quickly as possible. Make a shell for the function you are 
creating, and stick a `console.log` statement inside. Call this function and makes sure it outputs the
statement.

{% highlight js %}
var exponentiate = function(base, exponent) {
  console.log('inside function');  
};

exponentiate(2,4); // should print out 'inside function'
{% endhighlight %}

2) Assuming you have inputs, change your `console.log` statement to be something that log your inputs:


{% highlight js %}
var exponentiate = function(base, exponent) {
  console.log('base:', base, 'exponent:', exponent);  
};

exponentiate(2,4); // should print out 'base: 2 exponent: 4'
{% endhighlight %}

3) Include a variable for the result, usually a number, string, or integer, and formulate a first attempt at the calculation you want to make. Make sure to return this `result` variable as well as log it to the console.

{% highlight js %}
var exponentiate = function(base, exponent) {
  var result = 0;
  result = base * exponent;
  console.log('result', result);
  return result;
};

exponentiate(2,4); // should print out 'base: 2 exponent: 4'
{% endhighlight %}

Part 2 will include common toy problems that more are based on. Stay tuned!



[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help