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

## Main

I recently re-read [Algorithms to Live By](https://algorithmstoliveby.com/ "algo"), a book by Brian Christian and Tom Griffiths on how algorithms can help us deal with daily life better. Having [picked up programming last year,](https://avoidboringpeople.substack.com/p/avoid-boring-people-in-2020-be8 "prog") I got more out of this time around. 

An algorithm is a process, and you can think of it as instructions to follow to complete some task. For example, learning how to add numbers together is a simple algorithm \[1\]. 

You can imagine more complex instructions that can calculate results for other problems in life, such as interest rates, search rankings, or social media feeds. The book goes through many such algorithms, and relates them to problems you might face personally.

It's too difficult to explain every algorithm they mention \[2\], so instead I'll be doing short highlights from some of them, and usually concentrating on the qualitative, not quantitative takeaways.

Also, most of the algorithms rely on certain assumptions. Rather than specify that every time, take that as a given when reading; I'll add some of the assumptions in footnotes for those interested.

Some of the problems discussed include:
- When to stop working on something for the max chance of the best outcome
- When you should 

Let's look at our first algorithm, on when you should stop working on a problem.

## Optimal stopping

If you're evaluating options (job applicants, housing offers, parking spaces etc), there's a tradeoff between how long you spend choosing, and the chance of picking the "best" option. This is known as the [secretary problem](https://en.wikipedia.org/wiki/Secretary_problem "prob") - suppose you were hiring a secretary, how many interviews should you do to get the best chance of finding the best one?

In this case, there's a precise percentage to use. You should wait after seeing 37% of the applicant pool, and then take the next best applicant you see \[3\]. For example, if you had 100 applicants, wait after you've seen the first 37, and then pick the next applicant that is better than all you've seen so far.

## Explore exploit

Similar to the optimal stopping situation, there's a tradeoff between information gathering (explore) and enjoying (exploit). Suppose you're at a casino, and want to decide which machines to play. You want to maximise your winnings, but don't know the exact odds for the machines (if you did, you'd play the best one).

In this case, there's a number, known as the [Gittins Index](https://www.cs.cornell.edu/courses/cs6840/2017sp/lecnotes/6840sp17R_Kleinberg.pdf "gittins"), that gives you the optimal machine to play \[2\]. Some interesting properties:

- If you're playing the optimal machine and win again, it makes sense to continue playing that machine
- If you're playing the optimal machine and once, it might still make sense to continue playing that machine
- An entirely unknown machine can be preferable to machines that are known to win often, and gets more valuable the more you value future gains

Some other related implications:

- Exploration has a higher impact younger in life; babies putting everything in their mouth makes sense from their standpoint
- Exploiting has a higher impact later in life; hence older people cutting down their social network and preferring to return to favourite restaurants 

## Sorting

The book gave a few examples of sorting algorithms, which are commonly used in programming. For example, returning search results requires a sorting of the most relevant ones for you. 

I'll save more detailed discussion of sorting algos for another day since they require understanding [time complexity](https://www.bigocheatsheet.com/ "time"), and here are some qualitative takeaways:

- Some ways of sorting can be drastically more efficient than others
- Some scenarios do not desire sort efficiency only. For example, arranging a sports season matchup calendar also requires taking into account how exciting the season will be
- The more efficient a sort, the more fragile it might be against accidental mistakes. For example, the "best" team might accidentally get knocked out in a single elimination tournament like the World Cup \[3\]

## Caching

The idea of having a cache is to have 1) a small, fast memory (storage) section, and 2) a large, slow memory section. We'll then alternate between the two depending on what our intention is.

In this case, keeping the most recently used items in the small and fast section is the optimal choice, due to something known as [temporal locality](https://www.geeksforgeeks.org/difference-between-spatial-locality-and-temporal-locality/ "temp").

## Scheduling

A key point about scheduling and prioritisation is defining your goal metric. Only 9% of all scheduling problems can be solved efficiently. Tradeoff between responsiveness and throughput.

If you want to minimise the max lateness of all your projects \[4\], the [Earliest Due Date](https://en.wikipedia.org/wiki/Single-machine_scheduling "EDT") algorithm tells you to start with the project due earliest. 

If you want to minimise the total completion time, the [Shortest Processing Time](https://en.wikipedia.org/wiki/Single-machine_scheduling "spt") algorithm tells you to just do the quickest task first. 

If your tasks are not equal in importance, then placing a weight on each task and calculating the weight over time required ratio will help you decide which task to do; pick the project with highest weight over time.

Context switching is wasted time since it's not real work.

At its worse, context switching turns to thrash. Ways to avoid thrash:

- Saying no (the authors acknowledge we're often unable to do so)
- Working dumber, inefficently

## Bayes rule

Depends on the distribution. Power law, Normal, or Erlang. 

- Power law: the longer something has gone on, the longer we expect it to continue going on
- Normal: early events are surprising, late events are expected. 
- Erlang: events are never any more or less surprising e.g. a memoryless distribution like a roulette wheel

## Relaxation

Some problems are intractable. In these cases, relaxing some constraints and accepting solutions that are "close enough" helps us significantly in structuring the problem. 

## Game theory

- If you play too many levels above your opponent, you're going to think they have information they don't actually have and they won't be able to think what you want them to think
- Every two player game has at least one [Nash Equilibrium,](https://en.wikipedia.org/wiki/Nash_equilibrium "nash") where both players are choosing the optimal strategy for themselve
- Finding Nash equilibrium though is an intractable problem
- The equilibrium may not be the outcome that is best for all players. We cant quantify this as the "price of anarchy", which measures the gap between cooperation and competition. 
- [Mechanism design](https://en.wikipedia.org/wiki/Mechanism_design "mech") has a counterintuitive finding, that we can worsen every outcome but make everyone's lives better, by shifting the equilibrium

information cascades

## Footnotes

1. Easy enough to teach children, by telling them to memorise sums and when to carry a number, but surprisingly not obvious when trying to implement on a computer, see [full adder logic gate](https://www.electronics-tutorials.ws/combination/comb_7.html "full")
2. You might say that by the time I explain everything, I might as well have [written the entire book](https://en.wikipedia.org/wiki/P_versus_NP_problem "p np")
3. The percentage is 1 divided by e, euler's number
4. This problem is intractable if the probabilities of a payoff on a machine change over time
5. Or March Madness, for the Americans
6. As in, take all your projects that are late, and then the maximum of those. That's the metric you want to minimise.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/a16z gaming market size.png)

*If you liked this, sign up for my [finance and tech newsletter:](https://avoidboringpeople.substack.com/ "ABP")*

<div class="iframe-container-4x3">
  <p align="center"><iframe src="https://avoidboringpeople.substack.com/embed" frameborder="0" scrolling="no"> </iframe></p>
</div>
