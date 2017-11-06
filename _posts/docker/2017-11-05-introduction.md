---
layout: post
title:  "Docker Introduction"
date:   2017-11-05 22:21
categories: docker
---

Docker is one of the most used terms when you hear people talking about deployments, continuous integration, testing, DevOps, etc. 

I have been working with this technology for a while and I decided to write a little bit about my experience.
Let's start understanding what Docker is.

Docker is a container <- still hard to understand

A container is like a virtual machine running an OS but re-using the host's kernel. 
By this reason is really less resource consuming in comparison to a virtual machine where you need to install the whole OS.

# Advantages
- Re-use the kernel
- Less resource consuming
- Independent machines
- Easy to manage

The main idea with docker is to have one container per process.

For example: 
Let's say that you want to run an application that is composed by a MySQL database, some code written in Java that is consuming queues from RabbitMQ.
In the classic way you would probably install on a server MySQL, Java and RabbitMQ, or, if you want to have an isolated environment per product, you would end up with 3 servers.
After all, it's always a good idea keep every different process isolated in different servers. Of this way, if you need to restart your java server you won't end up killing your database and message server too.

Docker solve this problem in a more elegant way. In this case you only need one server and 3 docker instances:
1.- One instance running Java
2.- One instance running MySQL
3.- One instance running RabbitMQ

But, what is an instance is? 
In docker you have to understand a really simple concept.

Docker uses images, one image consist of the OS of your choice and all the things that you want to run inside it.
A good practice is only have one process running inside an image. For example: in our case we'd have:

1.- Image for Java : Ubuntu 14.04, Java 8
2.- Image for MySQL : CentOS 5, MySQL 5.x
3.- Image for RabbitMQ: Debian 9.1, RabbitMQ 3.6.11

And after have this images, we need to run them, so every single image running will be an instance.
Now all of this instance will be able to run inside your host so you won't need 3 servers but one. And these 3 intances will be re-using the host's kernel instead of install a new one for them.
Of this way, your instance won't consume a lot of resources of your server but you'll have 3 isolated and independent processes running.