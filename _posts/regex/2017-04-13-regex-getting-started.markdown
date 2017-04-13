---
layout: post
title:  "RegEx Getting Started"
date:   2017-04-13 09:09
categories: RegEx
---
# RegEx
It allows us to find certain patterns in strings, those string can be stored in files, variables, or any other place

## Filtering with GREP
The most simple way to find text in files in UNIX is using GREP. This one is heavily used daily on servers in order to find some patterns inside logs.
For example, let say we are looking for the string "ERROR" in the logs directory.

Move to the logs directory:
`cd path/to/logs/directory`

Use grep for finding the pattern:

{% highlight shell %}
$ grep -n 'ERROR' *.log
apache.log:8:ERROR in line ...
nginx.log:77:it has an ERROR ...
{% endhighlight %}

Explanation:

{% highlight shell %}
-n:     print the line number
ERROR:  string to find
*:      any file
.log:   files must have .log extension
{% highlight %}

From the output, firstly you will se file that has the coincidence, then the line number and the whole line that has the string that you are searching for