---
layout: post
title:  "AKKA Getting Started!"
date:   2017-03-30 16:33
categories: AKKA
---
# AKKA
Akka is a really cool toolkit for building highly concurrent and distributed applications based on a message-driven model. Let's review some key concepts in order to understand it.

## Actor Model
AKKA is based on an actor model that is quite simple, let's suppose that we have 2 actors: A and B

`Actor A`: Hi Actor B, can you do xyz

`Actor B`: Sure, give me a while

Basically a model based on messaging where one Actor send a message to other one when needs something.

<script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- inferior -->
<ins class="adsbygoogle"
     style="display:inline-block;width:728px;height:90px"
     data-ad-client="ca-pub-5428825449848403"
     data-ad-slot="1328012179"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script>

## Main Concepts Related to AKKA
In order to understand how AKKA works, it's vital understand a couple of concepts:

### Concurrency and Parallelism

#### Concurrency
Many task running on single core machine.
One coffee machine, many guys taking a little bit of coffee one after other

#### Parallelism
Many task running on multicore processor machine.
Many coffee machines, many guys taking coffee from there at the same time

### Sync and Async processes

#### Sync
One task invokes another one and it should wait until the other one has completed to continue

#### Async
One task invokes another one and it can keep working with no need to wait for the completion. After the completion, the invoked task can inform about its progress with a callback, message or any other way

### Blocking and Non-blocking

#### Blocking
One task will delay other tasks running
 
#### Non-Blocking
One task run and it wont delay other tasks running

### Race Condition
It's when more than one actor are trying to modify the state of something at the same time

That's all for now, in the next posts we are going to dive into the AKKA world

<script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- inferior -->
<ins class="adsbygoogle"
     style="display:inline-block;width:728px;height:90px"
     data-ad-client="ca-pub-5428825449848403"
     data-ad-slot="1328012179"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script>

