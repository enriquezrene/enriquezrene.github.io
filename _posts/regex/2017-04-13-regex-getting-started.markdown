---
layout: post
title:  "RegEx Getting Started"
date:   2017-04-13 09:09
categories: RegEx
---
{% capture time %}{{ content | reading_time }}{% endcapture %}
<p>This article will take {{ time }} {% if time == '1' %}minute{% else %}minutes{% endif %} to read.</p>

# RegEx
It allows us to find certain patterns in strings, those string can be stored in files, variables, or any other place

## Filtering with GREP
The most simple way to find text in files in UNIX is using GREP. This one is heavily used daily on servers in order to find some patterns inside logs.
For example, let say we are looking for the string "ERROR" in the logs directory.

Move to the logs directory:
`cd path/to/logs/directory`

<script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- inferior -->
<ins class="adsbygoogle"
     style="display:inline-block;width:728px;height:90px"
     data-ad-client="ca-pub-5428825449848403"
     data-ad-slot="1328012179"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script>

Use grep for finding the pattern:

{% highlight shell %}
$ grep -n 'ERROR' *.log
apache.log:8:ERROR in line ...
nginx.log:77:it has an ERROR ...

# Where:
-n:     print the line number
ERROR:  string to find
*:      any file
.log:   files must have .log extension
{% endhighlight %}

From the output, firstly you will se file that has the coincidence, then the line number and the whole line that has the string that you are searching for

If you enjoyed this article please support it clicking on the ads

