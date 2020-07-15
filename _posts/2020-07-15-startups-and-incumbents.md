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

### Tortoise vs hare

I'll take it for granted that everyone's familiar with the [tortoise vs hare fable.](http://read.gov/aesop/025.html "aesop") Hare races tortoise, falls asleep, loses, and spends the rest of his life living in shame before writing an explosive tell all on how it was [all a shell game](https://en.wikipedia.org/wiki/Shell_game "shell") \[1\].

[Drawing on this post by Farnam Street](https://fs.blog/2016/07/james-march-the-trouble-with-genius/ "FS"), let's extend the analogy further with a bit of math. I know how that scares off half the readership immediately, but let's not freak out yet. Coming from someone who recently wasted 15 min on a math problem because I added 1 + 1 wrongly, I'll be keeping the math simple if only for my sake \[2\]. 

Let's have a race track of 1 km. We'll assume the tortoise takes 100 min to run 1 km, and the hare takes 20 min to run 1km. However, the hare's sleep schedule has been messed up due to covid and there's a 95% chance it will sleep during every separate 20 min block. Put another way, there's a 5% chance it's awake during minutes 0-20, and then another 5% chance it's awake during minutes 20-40, and another 5% chance it's awake during minutes 40-60 etc.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Tortoise vs hare 1.png)

What's the chance that the hare beats the tortoise? 

For those of you that recall secondary school probability, we can calculate this with a [binomial distribution formula.](https://online.stat.psu.edu/stat414/lesson/10/10.3 "binom") The formula looks like this: 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Tortoise vs hare 2.png)

But that looks scary with summation signs and exclamation points, and I did promise to keep the math simple. One way to shortcut the calculation is to observe that there are 5 "20 min blocks" for the hare to fall asleep or be awake, since the hare is 5x faster than the tortoise. As long as the hare is awake once, it'll win. So, the only time the hare loses is when it sleeps all of those times. That's a much easier calculation, since that's just 95% times itself 5 times, or 0.95 to the power of 5 \[3\]. 

That gives us 77%, implying that under our assumptions, the hare loses 77% of the time to the tortoise, and only wins 23% of the time.

Now, let's change our framing slightly. If we ran 100 races, what's the chance that we get at least one race where the hare wins? 

There's only one case where no hares win, which is when all of the races are won by tortoises. Assuming the tortoise mafia didn't rig the game again, the chance of that happening is the 77% times itself 100 times, which rounds to 0%.

In other words, it's nearly guaranteed that at least once, a hare will win.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Tortoise vs hare 3.png)

I've put the math into a google sheet [here](https://docs.google.com/spreadsheets/d/1-_LV1ewb0D4DsERENaM_xp0oy8pHH7xWmAvNX8H9bdE/edit?usp=sharing "sheet") that you can play with. The math is less important than the takeaway though. What we've inferred is that even when the odds of something happening on its own are low, a repeated game will likely ensure the event happens once. Just like how it's unlikely for you to win the lottery, but it's likely there will be at least one lottery winner.

### Tortoise vs tech

Let's relate this to tech. 

Genius is more volatile. 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/a16z gaming market size.png)

*If you liked this, sign up for my [finance and tech newsletter:](https://avoidboringpeople.substack.com/ "ABP")*

### Footnotes

1. Also known as the #Me \[Tu\](https://www.echineselearning.com/blog/chinese-character-tu-rabbit-beginner "tu") movement.
2. Ok so it was 1 - -1 and I got the sign wrong in my head, so wasn't quite that bad. No I'm not getting defensive about it.
3. I've chosen the numbers here specifically to keep the example simple. I was looking for something where the hare would lose most of the time and only have a few intervals.

<div class="iframe-container-4x3">
  <p align="center"><iframe src="https://avoidboringpeople.substack.com/embed" frameborder="0" scrolling="no"> </iframe></p>
</div>
