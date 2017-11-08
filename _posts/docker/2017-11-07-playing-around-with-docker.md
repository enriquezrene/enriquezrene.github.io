---
layout: post
title:  "Playing around with Docker"
date:   2017-11-07 22:20
categories: docker
---

Now that you have ran your *Hello World* app with Docker, you're ready to go for more.

We said Docker can use any linux distribution that we want, now the question is:

How can I do that?

In Docker we have a public repo of docker images that we can use to run our apps.
Let's say that you want to use a docker container with CentOS, for it you can type in your terminal:
  
```sh
$ docker search centos
```  
  
and you'll have an output like this:

```sh
NAME                               DESCRIPTION                                     STARS               OFFICIAL            AUTOMATED
centos                             The official build of CentOS.                   3789                [OK]                
ansible/centos7-ansible            Ansible on Centos7                              103                                     [OK]
jdeathe/centos-ssh                 CentOS-6 6.9 x86_64 / CentOS-7 7.4.1708 x8...   89                                      [OK]
...
```

This command basically allow us to search existing docker images that we can use.

# Running docker images

## docker run
Once you found the image that you are looking for (let's say **centos**) we need to use the *run* command:

```sh
$ docker run centos
```

This command will download the image from the internet to our host and then run the container.
The container running on the host is what docker calls, an instance.

## docker ps
Once you ran a container, it will execute whatever process that you have specified inside it and then it finishes.
Since we did not configure any process to run inside the container, the instance should be finished. 
To know what instances have ran in your host you can type the following command:
```sh
$ docker ps -a
  CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                      PORTS               NAMES
  651fb5f3300b        centos              "/bin/bash"         14 seconds ago      Exited (0) 12 seconds ago                       musing_hoover
  810ad3c9ffe7        hello-world         "/hello"            47 seconds ago      Exited (0) 46 seconds ago                       objective_hawking
```

The **-a** flag is used to query the instances that are running and also those instances that have finished.
If you are interested only in the running instances just ignore the **-a** argument.

The command is currently listing two instances with an *Exited* status, which means they are no longer running.

## docker rm
This command allows you to remove the instances that you no longer need. 
```sh
$ docker rm 651fb5f3300b
$ docker ps -a
  CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                      PORTS               NAMES  
  810ad3c9ffe7        hello-world         "/hello"            47 seconds ago      Exited (0) 46 seconds ago                       objective_hawking
```

## docker images
It's helpful to check which images you have downloaded and are available locally:
```sh
$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
hello-world         latest              725dcfab7d63        4 days ago          1.84kB
centos              latest              d123f4e55e12        4 days ago          197MB
```

## docker rmi
If you want to remove a local image, use this command of this way:
```sh
# docker rmi <image_id>
$ docker rmi 725dcfab7d63
$ docker images
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
centos              latest              d123f4e55e12        4 days ago          197MB
```

In the next post I'm going to explain you about what the **Dockerfile** is and how you can use it. 

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