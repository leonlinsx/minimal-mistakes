---
title:  "Having faith in the Kelly Criterion for Angel Investing"  
tags: [angel investing, investing, finance, tech, simulation, agent based modeling, system, productivity]
published: false
---

## Takeaway

1. The Kelly criterion is a mathematical way of sizing your portfolio, though be careful with your assumptions
2. HASH.ai is making agent based simulations easier; I try to model startup failure rates
3. Feature post by Michael Batko on his productivity system to help prioritise, plan, and reflect

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

## 1. Kelly criterion for portfolio sizing

Sarah is an aspiring angel investor. Her friends Nicholas, Alyson, and Chase have a magical business idea involving pest extermination, and Sarah thinks it's going to be a huge hit.

Sarah was about to invest three lifetime's worth of her savings into this business, when her other group of friends \[1\] Seth, Marc, Emma, and Amber pitch her an equally exciting idea involving bunnies. 

It dawns on Sarah that she has multiple choices, and she isn't sure what to do. She goes to consult with her older friend Anthony, who watches the investing space closely. Anthony says she's on the right path - portfolio allocation and risk/reward payoffs are the key to becoming a successful investor. He also adds that she might want to read about the [Kelly criterion,](https://www.princeton.edu/~wbialek/rome/refs/kelly_56.pdf "Kelly") a formula for bet sizing.

The Kelly formula was developed by John Kelly at Bell Labs. It takes a few inputs and returns you the **optimal percentage of your capital to bet on something,** assuming you want to maximise long term returns. I've posted a simplified derivation in the appendix, and you can also find it [here](https://blogs.cfainstitute.org/investor/2018/06/14/the-kelly-criterion-you-dont-know-the-half-of-it/ "derive") or in the original paper.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 1.png)

I know math is scary, so let's illustrate with an example. You want to know how much to bet on a coin toss, where you either double your money or lose your bet. If you plug in the numbers: 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 2.png)

Yes, you read that right. Kelly says that you should avoid risking anything at all. Why? 

Since you have no edge, and the risk/reward is sized correctly, the best option is to not bet.

Now, imagine instead that the same coin toss paid you 11x return (1000%) on your bet, with everything else staying the same. If you plug in the numbers:

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 3.png)

Kelly says that you should bet 45% of your total capital. Notice that even with such attractive odds, you're not betting all your money \[2\]. You can also see that in games where you can lose all your bet, you never go all in unless you believe you have a 100% chance of winning.

[Michael Mauboussin and Ed Thorp elaborate on the attractive features of the Kelly system:](http://www.capatcolumbia.com/MM%20LMCM%20reports/Size%20Matters.pdf "Michael")

1. The chance of ruin is “small.” Because the Kelly system is based on proportional bets, losing all of your capital is theoretically impossible, though there will still be volatility spikes
2. The Kelly system is highly likely to grow a bankroll faster than other systems
3. You tend to reach a specified level of winnings in the least average time

How can this help us on the angel investing side? We'll have to make some highly simplifying assumptions \[3\], but Kelly can help give us some idea of how much to allocate per investment. 

We know that Kelly takes three inputs - our belief of what the winning probability is, the percentage loss, and the percentage profit. [Correlation Ventures and Seth Levine](https://www.sethlevine.com/archives/2020/10/vc-fund-returns-are-more-skewed-than-you-think.html "Seth") have a nice chart below showing VC returns over time, and I'll use that as the basis for my assumptions.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 4.png)

To simplify things, I'm just going to consider anything that's 10x return (900%) or more as a win, and everything else as a loss. From the graph, that means we win about 5% of the time. I'll simplify even further by assuming that we lose 100% of our bet on a loss, and win that 900% profit on a win. Under these initial assumptions, we get:

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 5.png)

Welp. That's not good. Under our current assumptions, Kelly says that VC investing is a bad deal. When I first saw this, I did a double take, and then wonderered how I was going to finish writing this newsletter issue \[4\]. The answer I came to was to cheat. A lot.

Instead of the 5% win rate, let's say that angel investors go into an investment having faith they're above average, and that their investments will at least return their money. They believe that their win probability is higher than the base rate. You don't bet on something unless you believe you have an edge vs the odds.

In other words, we'll ignore all of that <1x part on the graph, and assume our universe is just the remainder. That 5% win rate jumps to about 14% \[5\]. We'll keep everything else constant. Under these new assumptions, we get: 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 6.png)

Which is at least something we can work with. Bear with the assumptions for now and we'll revisit them later. 

To see what our returns could look like, let's also assume we make 100 such investments in a row. We'll run 1,000 simulations of what such a portfolio could look like i.e. imagine 1,000 universes where we invest in 100 companies under the assumptions above. [I'm using this Colab file here if you want to follow along](https://colab.research.google.com/drive/1YeMnl2QOQdCAGGxCDr2pfDk_HFgCh02D?usp=sharing "Colab")

Unsurprisingly, our rigged game shows us making a lot of money:

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 7.png)

A few things to note though. Look at the huge drawdowns (all the declines) that happen. Many of the portfolios lose more than half their money by the end. Returns have huge volatility spikes.

Also, we ran *one thousand* simulations. While the large returns stand out on the graph, there really aren't that many of them. The majority of the cases are all smushed together near the bottom. 

In order to reduce risk, many people often adopt a "Fractional Kelly" approach, where they bet some smaller percentage of the Kelly recommnended size. We'll do that here as well, simulating scenarios where we only bet half of what was recommended (2%).

Let's take a closer look at the return distribution for both of these cases. It's hard to see, but the box plots show the typical 25th, median, 75th percentile ranges of returns. We started at $100:

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 8.png)

If we ignore the outlier cases, we can see that the 25th to 75th percentile of the returns for all simulations are in a much smaller range. 

And if we zoom into the "safer," Half Kelly approach, we see that most of the time you're getting less than 5x returns.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 9.png)

**The takeaway is that if you're angel investing, you need high conviction, would likely want to do many investments, and only invest small percentages of your capital at a time.** Even then, the likelihood of the mythical 100x return is still low. Bear in mind that this is under the optimal betting strategy, and we already rigged the game in multiple ways:

- We removed a huge section of losers
- We assumed a binomial outcome
- We assumed fixed win and loss payouts
- We assumed bets occur one after the other
- We assumed we could make many bets

None of these are what real life is like; the above is a vast oversimplication. That said, **we can at least use Kelly to reduce the risk of ruin.** 

If you want to dig further, there's a paper by Vasily Nekrasov [here](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2259133 "paper") that has a much better model, but the math is beyond me. The python colab file is [here](https://colab.research.google.com/drive/1YeMnl2QOQdCAGGxCDr2pfDk_HFgCh02D?usp=sharing "colab") if you want to play around with the base simulation assumptions \[6\].

### For more on the Kelly criterion:

1. [The Kelly Criterion: Multiple Investment Opportunities by Christian Aichinger](https://greek0.net/blog/2018/04/17/kelly_criterion2/)
2. [The Kelly Criterion: You Don’t Know the Half of It by Alon Bochman](https://blogs.cfainstitute.org/investor/2018/06/14/the-kelly-criterion-you-dont-know-the-half-of-it/)
3. [Python Risk Management: Kelly Criterion by Lester Leong](https://towardsdatascience.com/python-risk-management-kelly-criterion-526e8fb6d6fd)
4. [Practical Implementation of the Kelly Criterion by Andrea Carta and Claudio Conversano](https://www.frontiersin.org/articles/10.3389/fams.2020.577050/full)
5. [What AngelList Data Says About Power-Law Returns In Venture Capital by AngelList](https://angel.co/blog/what-angellist-data-says-about-power-law-returns-in-venture-capital)

## 2. Using HASH.ai to simulate company survival rates

We'll move on from one model full of assumptions, to another model full of assumptions. I recently heard of the company [HASH.ai](https://hash.ai/ "hash"), which lets you "build multi-agent simulations in minutes." By that, they mean creating multiple objects that can interact with each other, and then seeing what happens. You can read more about agent-based modeling [here](https://hash.ai/blog/what-is-agent-based-modeling "hash")

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 10.png)

I wanted to play around with the tool \[7\], simulating some of the assumptions we made in the earlier sections. Some reasons VC investing is hard are because so many companies fail, or don't grow fast enough vs expectations. Let's model some companies growing in an economy.

Again, I'll make simplifying assumptions:

- We know average company survival rates on a yearly basis. I abuse probability to make an assumption for a daily survival rate
- Based on that I also infer a daily failure rate
- We also know average company revenue growth rates on a yearly basis. From that I infer a hacky daily growth rate

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 11.png)

I put all of that into a HASH.ai project, modifying one of their templates. It took a bunch of tinkering since many files are in Javascript and... I do not know Javascript. But I think I got it to mostly work in the end \[8\].

The model simulates companies as green boxes, growing in height every day, with the height representing company size. At any time period, there's a chance that the company fails, represented by the box burning up in flames \[9\]. We can see how many companies survive over long periods of time. Here's a sample run:

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/HASH.gif)

Under the current assumptions, there were a lot more survivors than I thought there would be, though it took a long time before we saw any 100x companies. Could probably go back and tweak the assumptions. 

HASH.ai also lets you graph stats over time. My current model shows a steady state of survivors vs failures.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 12.png)

Again, this was just for fun, and most of the assumptions need to be adjusted. The final model is [here](https://core.hash.ai/@leonlinsx/wildfires-regrowth-3/main "model") if you want to play around with it. Would be interested in seeing someone create a more sophisticated model of startup growth.

## 3. Edrolo OS - The World as a System

This month's guest post is from [Michael Batko](https://twitter.com/batkomichael "Michael") of [Batko OS](batko.substack.com "batko"), a newsletter about "how to see the World as a System to reduce your cognitive load and come to better outcomes." I normally don't post much productivity advice, but I actually do something similar to what Michael describes below.

Here's Michael:

My best two systems are called [Elephants](https://batko.substack.com/p/elephants-) for life and [Edrolo OS](https://batko.substack.com/p/batko-os-1-world-as-a-system) for work.

So let me tell you about the most effective Work system I've ever come across.

> The biggest struggle at work is always prioritisation of important work over everything else.

What if I told you I have a system that will help you prioritise, plan, reflect, practice gratitude and communicate transparently?

In a work context - this is the single most effective thing I do.

### Edrolo OS 📈

> The Edrolo Operating System (OS) was designed by Edrolo's co-founder Duncan Anderson (his blog [here](https://www.cloudstreaks.com/)). Nick Crocker has a great write-up [here](https://medium.com/things-ive-written/you-need-to-start-tracking-your-time-49592ead5fcc).

Edrolo OS is a weekly email on a Monday morning (take 5 mins for Step #1 right now!).

There are three steps:

1.  Plan your week
2.  Reflect on your week
3.  Share it with the team

### 1. Plan Your Week

Take 5 mins right now and revisit your annual or quarterly goals.

> What are your Top 3 priorities this week which will get you closer to achieving them?

Schedule a meeting with yourself blocking out time for you to work on each priority (this is a crucial part of the process!!).

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 13.png)

### 2. Reflect on Your Week

Next Monday morning, take 15 mins to reflect on your week.

Draft an email with these headers:

- **Summary of the Week** - 2 sentences
- **Learning of the Week**
- **Top 3 Priorities Last Week** - 1 sentence about each
- **Top 3 Priorities This Week** (same as step #1)
- **Kudos** - practice gratitude and mention anyone you'd like to say Thank You to

*👉 [Click here](https://mail.google.com/mail/u/0/?view=cm&fs=1&su=My+Edrolo+OS+-+Week+1&body=Hi%20Team,%0D%0A%0D%0A[Short%20summary%20of%20my%20week]%0D%0A%0D%0AMy%20Learning%20of%20the%20Week%0D%0A%0D%0ATop%203%20Priorities%20Last%20Week%0D%0A%0D%0ATop%203%20Priorities%20This%20Week%0D%0A%0D%0AKudos&tf=1) for the Gmail template ✉️ or [here](https://docs.google.com/document/d/11K9ctc9GUEhI3QpOfm_rH64yLGi4fkPs-Se8Wq1aWfw/edit?usp=sharing) for the text version.*

### 3. Share it with Your Team

This is where the real magic happens.

It will increase your communication transparency, Edrolo consistency and goal accountability.

You just discovered the single most effective system in my toolbox.

These 20mins a week will be your time to practice planning, consistency, reflection and transparency.

The Edrolo OS email will at first make you feel vulnerable. If you are consistent, these feelings will subside and I guarantee you will feel liberated because rather than judge, your colleagues will jump in to help you with your goals. You will feel empowered by the new system, providing you with a newfound communication channel to align you and your team on your goals.

### Questions for Michael

**1. What are you practicing deliberately? E.g in the same way a football player would train drills to consciously improve**

- Speaking and writing in metaphors. Our society is built on stories. Stories which paint a mental picture and trigger an emotional response. I'm a practical, bullet point kind of person. Long form writing and superfluous words and stories don't come naturally to me. 
- I started a note on my phone where I capture metaphors I hear from others as soon as I hear them. Every week I review the metaphors, reflect on what I liked about them, categorise them into themes (sports, cooking, building, etc) and challenge myself to come up with metaphors in a similar area. I also try to include a metaphor in each [substack](http://batko.substack.com) article I write to see what resonates with my readers.

**2. What do you wish you had known earlier?**

- Don't be afraid to reach out. It's easy to be intimidated by people who seem successful, well-known or busy. Especially when someone puts a piece of writing into the world - substack, blog or twitter - they want people to engage with them. Show genuine curiosity, share your thoughts and ask the stupid question.
- People want to hear from you. The worst thing to happen is that you don't hear back, on the other hand, there is the very real possibility of you learning something new.

**3. What's a common belief that you feel is mistaken?**

- Eisenhower matrix. We have been trained in this concept of always working on the Important and Urgent zone. It's a very selfish way of working. I genuinely believe that "you can have everything in life you want, if you will just help other people get what they want." What the framework is missing is to first unblock other people and for yourself not to be a bottleneck for your team. Let's call it the [Batman cape which the Eisenhower matrix](https://batko.substack.com/p/-eisenhower-vs-batman-unpopular-opinion) needs.

**4. What are the top frameworks you use to understand the world?**

- I strip everything back to the one core goal - the 'why' something exists. I then go through the most basic incentives you can or should put in place to motivate the right outcome. I'm a big sucker for behavioural psychology and board games. What rules can you set in place to incentive the intended outcome?

**5. What do you wish more people ask you about?**

- Ask but also challenge me on why things work the way they do. I love stripping back layers and go deep into the psychology and building blocks of difficult challenges. There's nothing better than being challenged on the fundamentals of why something is built the way it is. It always results in myself understanding it better and often the opportunity to make it better.

## Other

1. [Unit economics of vending machines](https://thehustle.co/the-economics-of-vending-machines/ "econs")
2. [Online game networking explained](https://www.pcgamer.com/netcode-explained/ "netcode")
3. [What we can learn from War and Peace and a napkin about risk.](https://refractor.substack.com/p/the-story-range? "refractor")
4. [American PhDs are failing at start-ups](https://marginalrevolution.com/marginalrevolution/2020/12/american-ph-ds-are-failing-at-start-ups.html "phd")
5. [This isn't Sparta](https://acoup.blog/2019/08/16/collections-this-isnt-sparta-part-i-spartan-school/ "sparta")

## Footnotes

1. Sarah's killing it in the friend department
2. There's also the unrelated point that if you ever see such attractive odds, you're probably being scammed
3. I want to re-emphasise how much we're simplifying here. For one, the illiquidity of angel investments is a huge problem since you don't have a repeated, continuous bet nature that we run later in the simulations. Also, sidenote that I could have easily gotten any of the math wrong, please correct me if you see mistakes.
4. Plan ahead, they say...
5. 5% divided by (100% minus 64%)
6. You'll notice that small tweaks to the winning probability from where it currently is will dramatically change the suggested bet percentage and predicted returns
7. Emphasis on play. My final model is super janky.
8. You'll notice references to trees, fires, and more in the code, which is leftover from the original model simulating wildfires.
9. I want to say this was intentional; I couldn't figure out how to change a lot of the features.

## Appendix

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 15.jpg)

*If you liked this, sign up for my [finance and tech newsletter:](https://avoidboringpeople.substack.com/ "ABP")*

<div class="iframe-container-4x3">
  <p align="center"><iframe src="https://avoidboringpeople.substack.com/embed" frameborder="0" scrolling="no"> </iframe></p>
</div>
