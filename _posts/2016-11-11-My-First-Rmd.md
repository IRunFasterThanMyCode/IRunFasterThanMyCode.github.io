---
layout: post
title: "My First R Markdown"
author: Sam Robson
published: true
status: publish
draft: false
tags: R 
---
 

 
## So this is R Markdown, huh?
 
So all I need to do is to write an R markdown file, click **Knit**, and I am good to go. 
 
## Have a useless plot
 
Not all of my plots are useless, honest.
 
![plot of chunk useless_plot](/figures/useless_plot-1.png)
 
## And some useless stats
 

{% highlight r %}
summary(rnorm(100))
{% endhighlight %}



{% highlight text %}
##     Min.  1st Qu.   Median     Mean  3rd Qu.     Max. 
## -2.61800 -0.63760  0.05586  0.03785  0.66820  2.28800
{% endhighlight %}
 
