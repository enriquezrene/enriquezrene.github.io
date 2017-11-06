---
layout: post
title:  "Brief Overview"
date:   2017-11-05 22:21
categories: docker
---

Docker is one of the most used terms when you hear people talking about deployments, continuous integration, testing, DevOps, etc. 

I have been working with this technology for a while and I decided to write a little bit about my experience with it. Let's start understanding what Docker is.

# Background
At the beginning we used to buy powerful servers in order to deploy our applications. Often these servers used to be underused.
Probably they were used at the half of their maximum capacity in the best cases. 

One of the worst things that used to happened us was related to have many services running on a physical server. 
So if we needed to restart the server because of a failure or something, all those services were down while the server was starting.

Keep the services isolated is one of the best practices to deal with these problems, but of course, buy one server per service is only worst.
That's why Virtual Machines raised, with them, we can have many services running on a single host and all of them are isolated. 
So if you need to restart one service, you only need to restart that VM (Virtual Machine) and that's it.


# What's wrong with VMs?
There is nothing wrong with them but the unique bad stuff is they need the full blown OS to work.
As we know each OS consumes:

- RAM
- Hard disk
- CPU
- Licenses (like Windows, RedHat and other OS)

# Docker is here to help us
Nowadays we have containers, and Docker is one of them, in a nutshell a container is like a VM that re-use the host kernel.
Since the container re-use the host kernel you have allowed to run any Linux distribution as a docker instance in your Unix (Linux/Mac) docker host. Same it's true for Windows.

- Docker host: physical server
- Docker image: like a VM re-using the host kernel

A Docker image is composed of the OS of your choice, and the services that you want inside it. 
For example, if you have installed Ubuntu in your host machine, you can run on it CentOS, RedHat, Debian or whatever other linux distribution.

A good practice is to run only one service inside a docker image.

Let's say that you want to run an application that is composed by a MySQL database, some code written in Java that is consuming queues from RabbitMQ.

With this idea in mind we will need three docker images and let's say three different OS too (if you want):

- Image 1: Ubuntu 14.04, Java 8
- Image 2: CentOS 5, MySQL 5.x
- Image 3: Debian 9.1, RabbitMQ 3.6.11

Of course we can use Ubuntu or any other distro for all the images, but I wrote three different OS just to make it clear.
Once you have your images you can run them, an image running is what we call an instance, so you'll have three docker instances running.

In the next posts I'm going to show you how to create your own docker images and how to run applications/services inside of them.

If you liked this post you can pay me with a click on the ads :)

<script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- inferior -->
<ins class="adsbygoogle"
     style="display:inline-block;width:728px;height:90px"
     data-ad-client="ca-pub-5428825449848403"
     data-ad-slot="1328012179"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script>