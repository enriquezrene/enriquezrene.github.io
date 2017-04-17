---
layout: post
title:  "Shortcuts"
date:   2017-04-17 12:34
categories: RegEx
---
# Shortcuts
It allows to specify key characters for simplifying our expressions

## \d digits ([0-9])
The expression:
{% highlight shell %}
$ grep -E "[0-9]{3,5}-[0-9]{4}-[0-9]{2,}-[0-9]{5}" file.txt
{% endhighlight %} 

can be easily translated into:
{% highlight shell %}
$ grep -P "[\d]{3,5}-[\d]{4}-[\d]{2,}-[\d]{5}" file.txt
{% endhighlight %} 

NOTE: we are using -P instead of -E flag because now we are using a Perl regular expression

let's use this content in your file for tests
{% highlight shell %}
1stName
2ndName
Name1
Name2
LastName1
LastName2
Full Name
Change4Free
 Type
  your
   name
{% endhighlight %}

## \b beginning
Finding expressions beginning with a number:
{% highlight shell %}
$ grep -P "\b[\d]" file.txt
1stName
2ndName
{% endhighlight %}

At the end:
{% highlight shell %}
$ grep -P "[\d]\b" file.txt
Name1
Name2
LastName1
LastName2
{% endhighlight %}

## \s space
Finding expressions with spaces:
{% highlight shell %}
$ grep -P "\s" file.txt
Full Name
 Type
  your
   name
{% endhighlight %}

## (?: GROUP )? Optional Group
Let's validate ZIP codes, valid values are:
5_DIGITS
5_DIGITS-4_DIGITS

For this example we are going to replace the content of the file with:
{% highlight shell %}
12354
456465-444
54546-4445
5554
65465-9978
{% endhighlight %}

The expression that we need is:
{% highlight shell %}
$ grep -P "^[\d]{5}(?:-[\d]{4})?$" file.txt
12354
54546-4445
Where:
^               : at the beginning
[\d]{5}         : 5 digits
(?:REGEX)       : expression
?               : optional
$               : at the end
{% endhighlight %}