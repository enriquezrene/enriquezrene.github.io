---
layout: post
title:  "BackReference"
date:   2017-04-17 12:34
categories: RegEx
---
# Back Reference
It allows to find repeated blocks in an expression
let's use this content in your file for tests
{% highlight shell %}
I need to to find double
expressions in
this this file
{% endhighlight %}

## Repeated words
In order to find repeated words let's use this expression:
{% highlight shell %}
$ grep -E "([a-z]+) +\1" file.txt
I need to to find double
this this file
{% endhighlight %} 


If you like this post please pay me with a click on the ads :)

<script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- inferior -->
<ins class="adsbygoogle"
     style="display:inline-block;width:728px;height:90px"
     data-ad-client="ca-pub-5428825449848403"
     data-ad-slot="1328012179"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script>