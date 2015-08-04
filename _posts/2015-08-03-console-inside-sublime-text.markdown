---
layout: post
title:  "Adding the console inside of Sublime Text"
date:   2015-08-03 18:00:00
categories: javascript closures
---
During my time at Telegraph Academy, we are given many different 'toy problems' consisting of relatively short, script like
tasks. They can almost always be written inside a single javascript file, or with a combination of one javascript file and 
one html file. This makes them prime candidates for rapid development solely with the javascript console. The console in Chrome's 
developer tools works well, but for very simple debugging using console.log statements, I prefer to debug by installing the 
Javascript console within Sublime Text. Here's an example of the finished product:

![alt text](/images/sublimeJSConsole.png)

To confire the Javascript Console on a Mac, do the following:

1) Install Node.js from their website [here](https://nodejs.org/).

2) In Sublime Text, click on "Tools" and then "New Build System..."

![alt text](/images/sublimeNewBuild.png)

3) Delete all existing code and replace it with:

{% highlight js %}
{
  "cmd": ["/usr/local/bin/node", "$file"],
  "selector": "source.js"
 }
{% endhighlight %}

4) Save the build as `Node.sublime-build`.

5) Whenever you want to run it, hit `command b` and your new build will run.

Remember that this is best for short, algorithmic tasks where you're looking for output from `console.log` statements. Have fun
coding with your new tool!

[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help