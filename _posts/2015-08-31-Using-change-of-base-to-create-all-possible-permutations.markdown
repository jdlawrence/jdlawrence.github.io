---
layout: post
title:  "Using a change-of-base formula to output all possible string permutations of a chosen length"
date:   2015-08-31 09:00:00
categories: algorithms permutations change-of-base
---

In dealing inputs, one common task that arises is to create a list of all possible strings of a certain length. Because order matters, these are known as all the possible permutations. For example, given the letters 'a' and 'b', the possible two character strings are: 

{% highlight js %}
'aa'
'ab'
'ba'
'bb'
{% endhighlight %}

Because there are two choices, 'a' and 'b', and our string is two characters long, there are 2 ^ 2 or 4 permutations. Consider another example using inputs 'x', 'y', and 'z'. Let's say we want to create and list all of the three character strings that are possible with these three letters. The list would look like: 

{% highlight js %}
'xxx'
'xxy'
'xxz'
'xyx'
'xyy'
'xyz'
...
'zzz'
{% endhighlight %}

Since there are three possible inputs, and three characters, we have a total of 3 ^ 3 = 27 possible permutations. This calculation always uses the number of inputs as a base, and desired string length as an output. Given 5 possible inputs with a desired string length of 4, there would be 5 ^ 4 = 625 possible permutations.

So far we have discussed how many possible permutations exist, but not the algorithm to create those combinations. This algorithm starts with a loop that counts from 0 to the number of permutations minus 1. For example, if there were 27 possible permtuations, we count from 0 through 26. In Javascript, this would like so:

{% highlight js %}
for (var i = 0; i < 27; i++) {
  // do something magical in here
}
{% endhighlight %}



[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help