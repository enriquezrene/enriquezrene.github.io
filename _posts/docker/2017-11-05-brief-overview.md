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

# Docker comes to help us


# Advantages
- Re-use the kernel
- Less resource consuming
- Independent machines
- Easy to manage

The main idea with docker is to have one container per process.

For example: 

Let's say that you want to run an application that is composed by a MySQL database, some code written in Java that is consuming queues from RabbitMQ.

In the classic way you will probably install on a server MySQL, Java and RabbitMQ, or, if you want to have an isolated environment per product, you would end up with 3 servers.

After all, it's always a good idea keep every different process isolated in different servers. Of this way, if you need to restart your java server you won't end up killing your database and message server too.

Docker solve this problem in a more elegant way. In this case you only need one server and 3 docker instances:

- One instance running Java
- One instance running MySQL
- One instance running RabbitMQ

Wait, what is an instance? 

In docker you have to understand a really simple concept.

Docker uses images, one image consist of the OS of your choice and all the things that you want to run inside it.
A good practice is only have one process running inside an image. 

For example: 

In our case we will need to have:

- Image for Java : Ubuntu 14.04, Java 8
- Image for MySQL : CentOS 5, MySQL 5.x
- Image for RabbitMQ: Debian 9.1, RabbitMQ 3.6.11

And after have these images, we need to run them, so every single image running will be an instance.

Now, all of these instances will be able to run inside your host so you won't need 3 servers but only one. 

And these 3 intances will be re-using the host's kernel instead of install a new one for them.

Of this way, your instances won't consume a lot of resources of your server and you'll have 3 isolated and independent processes running in your server.