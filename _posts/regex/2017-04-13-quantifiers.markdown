---
layout: post
title:  "Quantifiers"
date:   2017-04-13 11:32
categories: RegEx
---
# Quantifiers
It allows us to specify how many characters we do need to search, let's dive right in

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

## {} Quantifiers for IDN
Let's validate an identification number, we are looking for this pattern:
3_DIGITS - 4_DIGITS - 2_DIGITS - 5_DIGITS
For this example we are use a file with this content:

{% highlight shell %}
12345-4567-453465-45646
123-4568-45-45698
45646-454-545-99999
321-6548-55-87549
01236-21-45646-00
012-2546-5-00008
{% endhighlight %}
The expression that we need is:
{% highlight shell %}
$ grep -E "[0-9]{3}-[0-9]{4}-[0-9]{2}-[0-9]{5}" file.txt
123-4568-45-45698
321-6548-55-87549
{% endhighlight %}

Let's suppose that valid IDN is:
3or5_DIGITS-4_DIGITS-2orMORE_DIGITS-5DIGITS
The expression that we need in this case is:
{% highlight shell %}
$ grep -E "[0-9]{3,5}-[0-9]{4}-[0-9]{2,}-[0-9]{5}" file.txt
12345-4567-453465-45646
123-4568-45-45698
321-6548-55-87549
{% endhighlight %}