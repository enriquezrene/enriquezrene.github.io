---
layout: post
title:  "Quantifiers"
date:   2017-04-13 11:32
categories: RegEx
---
# Quantifiers
XYZ

## ? Optional
It allows to find a text that contains or not a character 

For the demonstration we are going to use a file named file.txt with this content:
{% highlight shell %}
Java SE it's nice
I like JEE just a little bit
I prefer to avoid J2EE and use plain JavaSE
JavaFX is growing a lot
{% endhighlight %}

Finding lines with JEE or J2EE
{% highlight shell %}
$ grep -E "J2?EE" file.txt
I like JEE just a little bit
I prefer to avoid J2EE and use plain SEJava
{% endhighlight %}

## * Exact Coincidences
Finding lines with Java text (no matter where, beginning-middle-ending)
{% highlight shell %}
$ grep -E "*Java" file.txt
Java SE it's nice
I prefer to avoid J2EE and use plain SEJava
JavaFX is growing a lot
{% endhighlight %}

## + A Quantity Of Coincidences
Let's replace the content by:
{% highlight shell %}
1
2
12
21
123
213
{% endhighlight %}

Finding two or more digits
{% highlight shell %}
$ grep -E "[0-9][0-9]+" file.txt
12
21
123
213
{% endhighlight %}