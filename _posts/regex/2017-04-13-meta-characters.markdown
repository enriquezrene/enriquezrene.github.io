---
layout: post
title:  "Meta-Characters"
date:   2017-04-13 11:08
categories: RegEx
---
# Meta-Characters
RegEx uses heavily meta-characters in order to easily find patterns inside a file

## [] Brackets
It allows to define a range of characters for find them in a file. 

For the demonstration we are going to use a file named file.txt with this content:
{% highlight shell %}
1
hello
2
goodbye
{% endhighlight %}

Finding alphabetic characters
{% highlight shell %}
$ grep "[a-z]" file.txt
hello
goodbye
{% endhighlight %}

Finding numbers 
{% highlight shell %}
$ grep "[0-9]" file.txt
1
2
{% endhighlight %}
 
## ^ Negate
Finding no-alphabetic characters
{% highlight shell %}
$ grep "[^a-z]" file.txt
1
2
{% endhighlight %}

Finding no numbers 
{% highlight shell %}
$ grep "[^0-9]" file.txt
hello
goodbye
{% endhighlight %}


## Searching Text Starting and Ending With
For the sake of simplicity let's change the content of the file by:
{% highlight shell %}
FirstName
LastName
Name1
1stName
{% endhighlight %}

### ^[ Starting With
Finding text starting with a number
{% highlight shell %}
$ grep "^[0-9]" file.txt
1stName
{% endhighlight %}

### $ Ending With
Finding text ending in a number
{% highlight shell %}
$ grep "[0-9]$" file.txt
Name1
{% endhighlight %}