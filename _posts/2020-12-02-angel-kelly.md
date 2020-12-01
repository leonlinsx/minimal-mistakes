---
title:  ""  
tags: []
published: false
---

## Takeaway

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

## 1. 

Sarah is an aspiring angel investor. Her friends Nicholas, Alyson, and Chase have a magical business idea involving selling wooden sticks, and Sarah thinks it's going to be a huge hit.

Sarah was about to invest three lifetime's worth of her savings into this business, when her other group of friends \[1\] Seth, Marc, Emma, and Amber pitch her an equally exciting idea involving bunnies. 

Now realising that she has choices, Sarah isn't sure what to do. She goes to consult with her older friend Anthony, who watches the investing space closely. Anthony says she's on the right path - portfolio allocation and risk/reward payoffs are the key to becoming a successful investor. He also adds that she might want to read about the [Kelly criterion,](https://www.princeton.edu/~wbialek/rome/refs/kelly_56.pdf "Kelly") a formula for bet sizing.

The Kelly formula was developed by John Kelly at Bell Labs. It takes a few inputs and returns you the optimal percentage of your capital to bet on something, assuming you want to maximise long term returns. 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 1.png)

I know math is scary, so let's illustrate with an example. You want to know how much to bet on a coin toss, where you either double your money or lose your bet. If you plug in the numbers: 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 2.png)

Yes, you read that right. Kelly says that you should avoid risking anything at all. Since you have no edge, and the risk/reward is sized correctly, the best option is to not bet.

Now, imagine instead that the same coin toss paid you 10x profit (1000%) on your bet, with everything else staying the same. If you plug in the numbers:

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 3.png)

Kelly says that you should bet 45% of your total capital. Notice that even with such attractive odds, you're not betting all your money \[2\]. You can also see that as long as you lose all your bet, you never go all in unless you believe you have a 100% chance of winning.

[Michael Mauboussin and Ed Thorp elaborate on the attractive features of the Kelly system:](http://www.capatcolumbia.com/MM%20LMCM%20reports/Size%20Matters.pdf "Michael")

1. The chance of ruin is “small.” Because the Kelly system is based on proportional bets, losing all of your capital is theoretically impossible, though there will still be large volatility
2. The Kelly system is highly likely to grow a bankroll faster than other systems
3. You tend to reach a specified level of winnings in the least average time

How can this help us on the angel investing side? We'll have to make some highly simplifying assumptions \[3\], but Kelly can help give us some idea of how much to allocate per investment. 

We know that Kelly takes three inputs - our belief of what the winning probability is, the percentage loss, and the percentage profit. [Correlation Ventures and Seth Levine](https://www.sethlevine.com/archives/2020/10/vc-fund-returns-are-more-skewed-than-you-think.html "Seth") have a nice chart below showing VC returns over time, and I'll use that as the basis for my assumptions.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 3.png)

To simplify things, I'm just going to consider anything that's 10x return (900%) or more as a win, and everything else as a loss. From the graph, that means we win about 5% of the time. I'll simplify even further by assuming that we lose 100% of our bet on a loss, and win that 900% profit on a win. We'll revisit these assumptions in a bit, just bear with it for now. Under these initial assumptions, we get:

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Kelly_criterion/Kelly 4.png)

Welp. That's not good. When I first saw this, I did a double take, and then wonderered how I was going to finish writing this newsletter issue \[4\]. The answer I came to was to cheat. I'll revisit the 5% assumption above, and say that we'll just 


## 2. 

## 3. Edrolo OS - The World as a System


## Footnotes

1. Sarah's killing it in the friend department
2. There's also the unrelated point that if you ever see such attractive odds, you're probably being scammed
3. I want to re-emphasise how much we're simplifying here. For one, the illiquidity of angel investments is a huge problem.
4. Plan ahead, they say...


*If you liked this, sign up for my [finance and tech newsletter:](https://avoidboringpeople.substack.com/ "ABP")*

<div class="iframe-container-4x3">
  <p align="center"><iframe src="https://avoidboringpeople.substack.com/embed" frameborder="0" scrolling="no"> </iframe></p>
</div>
