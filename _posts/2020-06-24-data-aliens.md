---
title:  ""  
tags: []
published: false
---

### Takeaway

<style>
      .iframe-container {
        overflow: hidden;        
        padding-top: 50%; <!-- Calculated from the aspect ration of the content (in case of 16:9 it is 9/16= 0.5625) -->
        position: relative;
      }
      .iframe-container iframe { 
         border: 0;
         height: 100%; <!-- Finally, width and height are set to 100% so the iframe takes up 100% of the containers space. -->
         left: 0;
         position: absolute;
         top: 0;
         width: 100%;
         display: block;
         margin: 0 auto; <!-- center image -->
      }
      <!-- 4x3 Aspect Ratio -->
      .iframe-container-4x3 {
        padding-top: 75%;
      }
</style> 

<div class="iframe-container-4x3">
  <p align="center"><iframe src="https://avoidboringpeople.substack.com/embed" frameborder="0" scrolling="no"> </iframe></p>
</div>

### Main

We've talked about [how machine learning companies use data to recognise text](https://avoidboringpeople.substack.com/p/the-next-machine-learning-startup "ML") and how [investors use data to pick companies.](https://avoidboringpeople.substack.com/p/not-everything-is-insider-trading "invest")

This week, let's talk about how scientists are using data to look for aliens. Some of the content below will draw from [Laurance Doyle's talk with the Long Now group.](http://longnow.org/seminars/02020/apr/29/interspecies-communication-and-search-extraterrestrial-intelligence/ "Long")

#### Framing the problem

The search for extraterrestrial intelligence institute (SETI) is the most famous of the research institutes that are looking for alien life. Its mission is to ["to explore, understand and explain the origin and nature of life in the universe and the evolution of intelligence."](https://www.seti.org/about-us/mission "mission")

How do we even go about scoping a problem like that? 

Well, if we're trying to find alien life, they have to exist on a planet somewhere else. So we know that trying to find planets is a potential starting point.

From elementary science we also know that planets form around stars. So we know that trying to find stars that can support planets is also a relevant point.

We know that most planets have harsh environments. So let's restrict that list just down to planets we think can support life \[1\].

Of those planets, not all of them will actually have life appear, so let's take the proportion that actually do.

We might think that we're good here, and have enough features to start looking. There are still some features we can add though to narrow down our search precision. 

When we're looking at planets, we want to find some signal coming from the planet, as that will be much stronger proof that the planet has life. Imagine you were looking at a house vs a house where someone was playing music. It's much easier to conclude that there's a living thing in the second scenario. 

So, let's narrow down the planets where life actually appears, to the planets where "intelligent" species appear.

And of those "intelligent species", let's only take the ones that end up developing communications technology. 

Lastly, even if the species developed communications, if they're no longer alive to send those communications, we'd never receive them. So we need to account for how long those civilisations live for as well.

That was a lot. But now we have all the major factors we need to frame our problem, and look for the number of intelligent alien civilisations that can send signals.

Putting it all together, what we've done is come up with the [Drake equation](https://en.wikipedia.org/wiki/Drake_equation#:~:text=The%20Drake%20equation%20is%20a%20statement%20that%20stimulates%20intellectual%20curiosity,a%20part%20of%20that%20universe. "Drake"), a famous way of estimating intelligent life \[2\]. Notice how all the points we just covered are multiplied together to get a guess of how many smart aliens are out there:

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Long Now drake equation.jpg)

#### Narrowing the scope 

That's a lot of variables though, so let's just focus on one part of that equation for today, that of the fraction of "intelligent" species. 

How would we 

### Footnotes

1. Defining what is habitable vs not [is difficult of course,](https://en.wikipedia.org/wiki/Circumstellar_habitable_zone "zone") since what works for us may not work for alien life. Some people might believe in silicon-based life rather than carbon-based (what we are), though [there are difficulties with that assumption](https://astronomy.stackexchange.com/questions/20858/why-do-aliens-have-to-be-carbon-based-lifeforms "carbon")
2. Note that "the usefulness of the Drake equation is not in the solving, but rather in the contemplation of all the various concepts which scientists must incorporate when considering the question of life elsewhere, and gives the question of life elsewhere a basis for scientific analysis"

*If you liked this, sign up for my [finance and tech newsletter:](https://avoidboringpeople.substack.com/ "ABP")*

<div class="iframe-container-4x3">
  <p align="center"><iframe src="https://avoidboringpeople.substack.com/embed" frameborder="0" scrolling="no"> </iframe></p>
</div>
