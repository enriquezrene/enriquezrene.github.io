---
layout: post
title:  "Ip Adress with RegEx"
date:   2017-04-17 14:34
categories: RegEx
---
# Looking for valid IP Addresses
IP Addresses have the format
3DIGITS.3DIGITS.3DIGITS.3DIGITS
 
So, the expression for find these values is quite simple:
{% highlight shell %}
$ grep -P "^([\d]{1,3}\.){3}[\d]{1,3}$" file.txt
127.0.0.1
129.22.224.55
192.168.1.1
123.255.255.255
Where:
^               : at the beginning
[\d]{1,3}       : find 1, 2 or 3 digits
\.              : those numbers must be followed by a .
{3}             : we are looking for 3 groups with the same pattern
[\d]{1,3}       : find a block of 1,2 or 3 digits
$               : at the end
{% endhighlight %}

For this example we have used a file with this content:
{% highlight shell %}
127.0.0.1
129.22.224.55
192.168.1.1
123.12.12
11.00.00.1.2
123.255.255.255
12.12.12.12.12
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