---
title:  "Would you buy the Libra Neopet Kin token?"  
tags: []
published: false
---

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

**Takeaways**

**Question of the month**

If you have been affected by the crisis and think I could help, please reply directly to this email and we'll problem solve together.

****

You use rating systems all the time: apps on mobile, drivers on uber, restaurants on google maps \[1\]. You've also probably noticed how most of them are flawed, not giving you enough precise information to decide if the thing is actually good. A 4.5 star rating doesn't mean much when everyone is also above 4 stars. [Josh Breinlinger of Jackson Square](https://acrowdedspace.com/ "JSV") discusses why this happens to marketplaces [here](https://www.slideshare.net/jbreinlinger/marketplace-pricing-and-feedback "Feedback") and proposes some solutions.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/JSV/JSV 1 optimise retain expel.png)

> Ppl focus too much on screening initially, when they should focus on optimisation post acceptance

To make sure we're on the same page, we'll define a marketplace as a [platform that matches buyers and sellers](https://a16z.com/marketplace-100/ "a16z"). Amazon, AirBnB, Upwork are all marketplaces.

Most marketplaces have some quality screening process at the start, and once you pass that you rarely get taken off the platform. Josh is saying that marketplaces should focus on the optimisation, retention, and expulsion processes more than the screening process, as these will be more effective in maintaining quality. It's the difference between measuring potential vs actual service by the provider.

This makes sense, and the difficulty here is one of scale. If you run a screen and then don't care about quality after, you only need to run it once for every new participant. If you invest in regular quality evaluations, you'll have to run it multiple times, on a participant base that gets larger over time. The costs of doing the latter are likely to continue scaling with your growth as well \[2\].

![post]({{ site.url }}{{ site.baseurl }}/assets/images/JSV/JSV 2 five star bad remove.png)

> 5 star ratings can separate bad sellers but don't have enough granularity to separate good vs great

5 star systems give people a false sense of precision. Since people choose 5 as the default, "average" rating, differentiating between good vs great is close to impossible. Even if the ratings start out effective, [grade inflation over time leads to their irrelevance.](http://john-joseph-horton.com/papers/longrun.pdf "Reputation")

You can get a sense of the terrible sellers, since a 1 star review pulls down the average dramatically \[3\], but the difference between a 4.7 vs a 4.5 is likely [noise rather than signal.](https://www.quora.com/Whats-a-simple-way-to-explain-the-signals-vs-noise-idea "signal") Since you'd prefer knowing who the best sellers are rather than the worst, 5 star ratings aren't that helpful.

Something I wonder about is when the assumption of the normal distribution of sellers doesn't hold. I can't think of many cases at the moment, outside of artificially restricted platforms where the selection process is exclusive rather than inclusive. For example, if you were to create [a membership club for top restaurants,](https://www.inhousenewyork.com/ "inhouse") the sellers wouldn't be normally distributed. This doesn't affect the validity of the point though, and perhaps even supplements it, since you want even finer granularity between the top sellers. 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/JSV/JSV 3 relative vs absolute.png)

> A relative rating rather than an absolute will be better in separating the good from great

Josh gives the example of [ELO ratings,](https://en.wikipedia.org/wiki/Elo_rating_system "ELO") most commonly used in chess, as a way to mitigate this review problem. ELO ratings compare the results of a competition between two players, awarding points for wins and deducting points for losses. By making ratings a result of comparing one game or one seller to another, we'll get better quality information of who is good and who is great.

Besides user feedback, Josh also suggests to use actual buyer behaviour as another signal of quality. If users are presented 3 different babysitting providers and consistently pick one, that provider should be given a better score. Sellers that are consistently closing sales will be seen more often.

This does create a problem where new entrants find it hard to break in. For example, Amazon's first page of organic results usually returns the larger, longer tenured sellers. This is good for the marketplace in the short term since buyers can trust in the quality of the product. I'm less certain it's good in the long term since it might hide new sellers that have better quality at a lower price, who never get enough traction to survive.

In a separate post, Josh talks about [using response rate as a quality signal as well.](https://acrowdedspace.com/post/186004771432/response-rate-is-a-quality-signal "response rate") All else equal, having a higher response rate in feedback means the feedback is better quality. A TV series that has 4 stars with a 100% response rate is better than a series that has 4 stars with a 10% response rate. The idea behind this is whether users like the thing enough that they can overcome the initial hurdle of providing feedback. If they didn't have a strong feeling on the subject, they wouldn't bother rating. Ambivalence is bad; the opposite of love is not hate but being ignored.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/JSV/JSV 4 response rate.png)

Josh also discusses pricing models of marketplaces, which you can check out in [the slides linked](https://www.slideshare.net/jbreinlinger/marketplace-pricing-and-feedback "JSV"). His main points there are that marketplaces should charge fees less than the efficiency gained, that there are three primary pricing models, and optics matter in who is paying fees. I'm not going to cover these in order to keep this section on topic.

If you're building a marketplace, Josh's points can be summarised as:

  1. evaluate actual rather than potential quality
  2. use relative rather than absolute ratings to get more granularity
  3. use other signals beyond user feedback scores, such as actual behaviour or response rate

**Fluctuat nec mergitur**

> Goodness is not goodness that seeks advantage. Good is good in the final hour, in the deepest pit, without hope, without witness, without reward. Virtue is only virtue in extremis \[30\]

I can't predict when this crisis will end. [I hope it's soon, though I fear it's not.](https://www.theatlantic.com/health/archive/2020/03/how-will-coronavirus-end/608719/ "Atlantic")

What I can predict is that this crisis will show people for who they really are. Crises reveal the best but also the worst in us. There will be [those that help](https://www.washingtonpost.com/world/europe/italy-coronavirus-doctors-retired/2020/03/28/075dbda0-6f0f-11ea-a156-0048b62cdb51_story.html "doctor") and [those that harm](https://www.independent.ie/world-news/coronavirus/they-could-kill-someone-gang-of-youths-cough-on-nurse-39074300.html "youth"). Those that keep their word and those that break it. Those that make their reputation and those that disgrace it. 

Choose which group you want to be. Choose wisely. 

The city of Paris has a motto, [Fluctuat nec mergitur,](https://en.wikipedia.org/wiki/Coat_of_arms_of_Paris "Paris") meaning "tossed by the waves, but does not sink". I'd like to believe this applies to all of us. We're in for a rocky time, but will weather this storm as we always have, by helping each other. 

I have no doubt that we will pull through this. Bruised but not broken, we'll recover having reassessed who and what matters most. And one day we'll be telling stories of how we survived by coming together as a community \[31\]. 

I also have no doubt that these will sound like hollow platitudes if you've been personally affected by the crisis. In my biggest failures, I heard them all - time heals all wounds, failure is one step to success, losing opens up new opportunities. I instinctively knew them to be true, but honestly didn't give a shit then. 

And that's ok. It's ok to be feeling what you're feeling now. Frightened. Distraught. Lost. 

But know that those feelings will fade, and you're better than your temporary temperaments. [For man is not made for defeat. A man can be destroyed but not defeated.](https://www.goodreads.com/quotes/111352-but-man-is-not-made-for-defeat-he-said-a "Defeat") And when you're ready, there are people standing by to help. 

If you do need help, there are some resources in the "Other" section below that might be worth checking out.

And if you're fortunate enough to be able to help, the "Other" section also highlights ways to do so. 

In these trying times, we'll be tossed by waves of fear and hopelessness, but will not sink to despair. If we all help rather than harm, we can get through this. Reach out, even if it's just to one person. You can make a larger difference than you think. 

> If I can stop one heart from breaking,
> I shall not live in vain;
> If I can ease one life the aching,
> Or cool one pain,
> Or help one fainting robin
> Unto his nest again,
> I shall not live in vain \[32\]

**Shoutouts**

1. I met with Nick Arkinson of [Levatso Holdings](https://www.levatsoholdings.com/ "Levatso"), who's looking to buy a majority stake in a growing company. Companies that fit their model typically have $5M - 20M annual rev, recurring rev model, 15%+ operating margin
2. If you're in Manhattan and need an hourly retail worker, my friend who's a chocolate expert was laid off and is looking for work
3. If you're in Chicago and need food, Ben Arnstein of [Kaliflower](https://www.eatkaliflower.com/ "Kaliflower") could use the support

**Other resources to help or get helped**

1. If you're an hourly worker that was laid off, [Sari Azout](https://twitter.com/sariazout "Sari") is donating her ad revenue to people like you. Fill up your info [here](https://docs.google.com/spreadsheets/d/1FiGwSc4aXcNiXOLLDD5SiLl_rt-NlKxpE8Y7ItZG7wo/edit#gid=332470286 "Sari")
2. If you're a startup employee that was laid off, [Julia Lipton](https://twitter.com/JuliaLipton "Julia") has a form [here](https://docs.google.com/forms/d/e/1FAIpQLSdVmqb4iYasGhDy2SQIG-qlLhsNV_d6CxrkfFwF6shLPYa3uA/viewform "Julia") that's matching employees to companies hiring
3. If you're in tech and are looking for a job, [Candor](https://twitter.com/teamcandor "Candor") has a list showing which companies are still hiring [here](https://candor.co/hiring-freezes/ "Candor")
4. If you're in NY and want to buy merchandise from restaurants to show support, Eater NY has a list [here](https://ny.eater.com/2020/3/27/21192544/nyc-restaurant-merchandise-list-coronavirus-support "Eater")
5. If you want to volunteer for a COVID project, Help with Covid has a list [here](https://helpwithcovid.com/ "Covid")

**Footnotes**

1. I have a personal bias against yelp due to anecdotes of restaurant complaints
2. I believe it's the difference between a linear (screen once) vs a polynomial (evaluate constantly) function but someone correct me if I'm wrong here
3. For example, 95% 5 star ratings and 5% 1 star ratings give an average of 4.8, which many people would think is significantly lower than a 5.
30. Doctor Who
31. I was going to write about the trend of niche irl communities that have been gaining popularity this month such as Not Boring Club, Inter Intellect, Get Real etc. Given the situation though I'll reserve that for later.
32. Emily Dickinson

*If you liked this, you'll like* ***[my monthly newsletter.](https://avoidboringpeople.substack.com/ "ABP")*** *Sign up here:*

<div class="iframe-container-4x3">
  <p align="center"><iframe src="https://avoidboringpeople.substack.com/embed" frameborder="0" scrolling="no"> </iframe></p>
</div>
