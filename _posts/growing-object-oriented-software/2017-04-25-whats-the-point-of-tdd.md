---
layout: post
title:  "Getting Started"
date:   2017-04-25 14:53
categories: growing-object-oriented-software
---

This post contains a summary about the first Chapter of the book.
> Growing Object Oriented Software, Guided by Tests <br>
> By Steve Freeman and Nat Pryce.

When we are creating software we have to bear in mind that feedback cycles at every level of development are quite important. We are going to mention some of them: 
- Pair programming
- Unit tests
- Acceptance tests
- Daily meetings
- Iterations
- Releases, and so on.
 
# What Is the Point of Test-Driven Development?
Feedback is the matter of TDD. Each cycle should expose the team for receiving feedback and correct any misconception

## Supporting Changes
Testing is helpful for catching errors on regressions and gives us confidence for modifying the existing code.

The code should follow the [KISS principle](https://en.wikipedia.org/wiki/KISS_principle).

Apply TDD for everything and follow the golden rule "Never write new functionality without a failing test."

After implement a new feature, we need an Acceptance Test

**Write a failing acceptance test**, then: 
> (1) write failing unit test | (2) make the test pass | (3) refactor -> Go to step (1)

<script async src="//pagead2.googlesyndication.com/pagead/js/adsbygoogle.js"></script>
<!-- inferior -->
<ins class="adsbygoogle"
     style="display:inline-block;width:728px;height:90px"
     data-ad-client="ca-pub-5428825449848403"
     data-ad-slot="1328012179"></ins>
<script>
(adsbygoogle = window.adsbygoogle || []).push({});
</script>

**Note:**
> Failing unit tests should never be committed to the source repository.

## Acceptance Test
Usually end-to-end tests, it interacts with the system from the outside without directly calling its internal code.

## Levels of Testing
>**Acceptance**: Does the whole system work?<br>
>**Integration**: Does our code work against code we can’t change?<br>
>**Unit**: Do our objects do the right thing, are they convenient to work with?

## External and Internal Quality
Internal quality is directly proportional to the amount of feedback received.

External quality is directly proportional to the tests you have done: 
>unit->integration->end-to-end.

On unit-test, the class must have explicit dependencies that can easily be substituted and clear responsibilities that can easily be invoked and verified. It provides valuable and immediate feedback about our design.
Features with “high” coherence are easier to maintain. Imagine a machine to wash clothes and dishes (crazy and untestable).


If you like this post please pay me with a click on the ads :) 

If you have any questions about this summary, feel free to send me an email and we can discuss anything more in deep.

Don't forget to subscribe us using the link at the right-upper corner to receive next posts
