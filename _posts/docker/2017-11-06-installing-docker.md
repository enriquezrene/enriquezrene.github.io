---
layout: post
title:  "Installing Docker"
date:   2017-11-06 22:23
categories: docker
---

In this post, I'm going to show you how to install Docker on Ubuntu 17.10

Old linux distributions used to include the program *docker*, *docker.io* and *docker-engine* as part of a fresh installation.
Those programs are really old, if you have them, please ensure to first remove them of this way:
```sh
$ sudo apt-get remove docker docker-engine docker.io
```

Now, let's add the required repos and install docker-ce (community edition) on our PC with the following commands:

```sh
$ sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu zesty stable"
$ sudo apt-get update
$ sudo apt-get install docker-ce
```

In order to verify if the installation was successful, run the following command: 
```sh
docker --version
```

You will see something like this:
```sh
﻿Docker version 17.09.0-ce, build afdb6d4
```

# Hello World
I know we all love *Hello World* examples and that's why we are going to run a *Hello World* using our
fresh Docker installation. 

For this, let's type in your terminal the next command:
```sh
sudo docker run hello-world
```

You'll have an output like this:
```sh
﻿$ sudo docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
9a0669468bf7: Pull complete 
Digest: sha256:0e06ef5e1945a718b02a8c319e15bae44f47039005530bc617a5d071190ed3fc
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://cloud.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/engine/userguide/
```

Yay!!! It means, Docker was successfully installed and now you are ready to go ahead with the rest of the posts.

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