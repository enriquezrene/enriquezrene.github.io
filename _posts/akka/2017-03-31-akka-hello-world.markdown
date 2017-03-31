---
layout: post
title:  "AKKA Hello World"
date:   2017-03-30 16:33
categories: AKKA
---
Let's create the most well known application for us, the HELLO WORLD APP  

In order to have the required actor of an AKKA application, we will need:

- A message 
- An actor

# A message
This is quite simple, we only need one line of code:

{% highlight scala %}
case class Task(taskName: String)
{% endhighlight %}

# An actor
Don't be afraid, this is quite simple too. You just have to inherit from akka.actor.Actor and provide an implementation for the receive method.
This method will be executed when the actor receives the message.

{% highlight scala %}
class Employee extends Actor {
  override def receive: Receive = {
    case Task(taskName) => println(s"I'm working on $taskName")
  }
}
{% endhighlight %}

For finish, we only need to send the message to the Actor. Let's say that someone has sent me a message to work on the Hello World app, the app should looks like:

{% highlight scala %}
val system = ActorSystem("HelloWorld-App")
val developer = system.actorOf(Props[Employee], "Rene")
// Send the task to the developer
developer ! Task("Write an AKKA Hello World app")
{% endhighlight %}

I love Scala because it help us to keep the things really simple, the whole application can reside in just one file:

{% highlight scala %}
import akka.actor.{Actor, ActorSystem, Props}

// A message with what to do
case class Task(taskName: String)

// Who will do
class Employee extends Actor {
  override def receive: Receive = {
    case Task(taskName) => println(s"I'm working on $taskName")
  }
}


object HelloWorld {

  def main(args: Array[String]): Unit = {
    val system = ActorSystem("HelloWorld-App")
    val developer = system.actorOf(Props[Employee], "Rene")
    // Send the task to the developer
    developer ! Task("Write an AKKA Hello World app")
  }

}
{% endhighlight %}

The code is available [on Github], if you want to run it just type:
{% highlight scala %}
$ sbt
> run-main io.github.enriquezrene.akka01.HelloWorld
#=> prints 'I'm working on Write an AKKA Hello World app' to STDOUT.
{% endhighlight %}

[on Github]: https://github.com/enriquezrene/akka-in-a-nutshell/blob/master/src/main/scala/io/github/enriquezrene/akka01/HelloWorld.scala