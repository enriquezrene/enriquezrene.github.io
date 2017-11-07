---
layout: post
title:  "Brief Overview"
date:   2017-11-05 22:21
categories: docker
---

Docker is one of the most used terms when you hear people talking about deployments, continuous integration, testing, DevOps, etc. 

I have been working with this technology for a while and I decided to write a little bit about my experience with it. Let's start understanding what Docker is.

# Background
At the beginning we used to buy powerful servers in order to deploy our applications. Often these servers used to be under-used.
Probably they were used at the half of their maximum capacity in the best cases. 

One of the worst things that used to happened us was related to have many services running on a physical server. 
So if we needed to restart for some reason, all those services were down while the server was being started, this is too bad.

On the other hand, keep the services isolated is one of the best practices to deal with these problems, but of course, buy one server per service is not a smart idea at all, and that's why Virtual Machines (VMs) raised.
 
Using VMs, we can have many services running on a single host and all of them are isolated one each other. 
So if you need to restart one service, you only need to restart that VM and that's it.


# What's wrong with VMs?
There is nothing wrong with them but the unique bad stuff is they need the full blown OS to work and as we know, each OS consumes:

- RAM
- Hard disk
- CPU
- OS Licenses (like Windows and other OS)

# Now we have Docker
Keeping in mind those issues a new (not really new) solution was created and now we have containers. 
Docker is one of them, in a nutshell a container is like a VM that re-use the host's kernel and because of that you have allowed to run any Linux distribution as a docker instance on your Linux docker host. Of course, the same it's true for Windows.

Let's review two basic concepts:

### Docker host
This is your physical server, nowadays it's pretty common an EC2 instance running on AWS.

### Docker image
It is composed of the OS of your choice, and the services that you want running inside it.
 
For example, if you have installed Ubuntu in your host machine, you can run on it CentOS, RedHat, Debian or whatever other linux distribution.

> A good practice is to run only one service inside a docker image.

In order to understand better how Docker can be used, let's say that you want to run an application that is composed by a MySQL database and some code written in Java.

With this idea in mind, we will need two docker images, and each one of them can have a different OS, for example:

- Image 1: Ubuntu 14.04, Java 8
- Image 2: CentOS 5, MySQL 5.x

Of course we can use Ubuntu or any other distro for all the images, but I'm choosing two different OS just to make it clear.
Once you have your images you can run them, an image running is what we call an instance, so you'll have two docker instances running.

And each one of them will be absolutely isolated and re-using the host kernel. Of this way, if we want to restart the database server,
we will only need to restart the Image 2 and the Image 1 and the docker host will keep working without any problems.

In the next posts, I'm going to show you how to create your own docker images and how to run applications/services inside of them.

If you liked this post, you can pay me with a click on the ads :sweat_smile: :v:

<script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- inferior -->
<ins class="adsbygoogle"
     style="display:inline-block;width:728px;height:90px"
     data-ad-client="ca-pub-5428825449848403"
     data-ad-slot="1328012179"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script>