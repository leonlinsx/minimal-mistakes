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

You can imagine more complex instructions that can calculate results for other problems in life. Interest rates, web search rankings, or social media feeds are all based on the output of algorithms. The book goes through many such algorithms, and relates them to problems you might face personally.

It's too difficult to explain every algorithm they mention \[2\], so instead I'll be doing short highlights from some of them, and usually concentrating on the qualitative, not quantitative takeaways.

Also, most of the algorithms rely on certain assumptions; rather than specify that every time, take that as a given when reading. I'll add some of the assumptions in footnotes for those interested.

Some of the problems discussed include:
- When to stop interviewing for the max chance of the best outcome
- When you should stop exploring new options to enjoy the ones you already know
- How to schedule your tasks based on what your goal is
- The types of distributions in life and Baye's rule
- Game theory

Let's look at our first algorithm, on when you should stop working on a problem.

## Optimal stopping

If you're evaluating options (job applicants, housing offers, parking spaces etc), there's a tradeoff between how long you spend choosing, and the chance of picking the "best" option. This is known as the [secretary problem](https://en.wikipedia.org/wiki/Secretary_problem "prob") - suppose you were hiring a secretary, how many interviews should you do to get the best chance of finding the best one?

In this case, there's a precise percentage to use. You should wait after seeing 37% of the applicant pool, and then take the next best applicant you see \[3\]. For example, if you had 100 applicants, wait after you've seen the first 37, and then pick the next applicant that is better than all you've seen so far. 

That is the mathematically optimal point with the highest chance of picking the best person for the job. If you stop too early, you might miss someone interviewing later. If you stop too late, you waste time \[4\].

## Explore exploit

Similar to the optimal stopping situation, there's a tradeoff between information gathering (explore) and enjoying (exploit). Suppose you're at a casino, and want to decide which machines to play. You want to maximise your winnings, but don't know the exact odds for the machines (if you did, you'd play the best one).

In this case, there's a number, known as the [Gittins Index](https://www.cs.cornell.edu/courses/cs6840/2017sp/lecnotes/6840sp17R_Kleinberg.pdf "gittins"), that gives you the optimal machine to play \[5\]. Some interesting properties:

- If you're playing the optimal machine and win again, it makes sense to continue playing that machine
- If you're playing the optimal machine and once, it might still make sense to continue playing that machine
- An entirely unknown machine can be preferable to machines that are known to win often, and gets more valuable the more you value future gains

Some other related implications:

- Exploration has a higher impact younger in life; babies putting everything in their mouth makes sense from their standpoint
- Exploiting has a higher impact later in life; hence older people cutting down their social network and preferring to return to favourite restaurants 

## Sorting

The book gave a few examples of sorting algorithms, which are commonly used in programming. For example, returning search results requires a sorting of the most relevant ones for you. 

I'll save more detailed discussion of sorting algos for another day since they require understanding [time complexity](https://www.bigocheatsheet.com/ "time"). Here are some qualitative takeaways:

- Some ways of sorting can be drastically more efficient than others (>10x faster)
- Some scenarios do not desire sort efficiency only. For example, arranging a sports season matchup calendar also requires taking into account how exciting the season will be. You could optimise sort efficiency, but the season will seem less thrilling
- The more efficient a sort, the more fragile it might be against accidental mistakes. For example, the "best" team might accidentally get knocked out in a single elimination tournament like the World Cup \[6\]. 

## Caching

The idea of having a cache is to have 1) a small, fast memory (storage) section, and 2) a large, slow memory section. We'll then alternate between the two depending on what our intention is. This lets us get both some amount of speed and some amount of size when recalling things. For example, you might have your favourite clothes in your wardrobe, and your unused ones in the attic.

The problem then is to decide what items should be put in the fast section, and what items in the slow section? 

In this case, keeping the most recently used items in the small and fast section is the optimal choice, due to something known as [temporal locality](https://www.geeksforgeeks.org/difference-between-spatial-locality-and-temporal-locality/ "temp"). You're more likely to need something again that's something you've recently used.

## Scheduling

A key point about scheduling and prioritisation is defining your goal metric \[7\]. 

 Tradeoff between responsiveness and throughput.

If you want to minimise the max lateness of all your projects \[8\], the [Earliest Due Date](https://en.wikipedia.org/wiki/Single-machine_scheduling "EDT") algorithm tells you to start with the project due earliest. 

If you want to minimise the total completion time, the [Shortest Processing Time](https://en.wikipedia.org/wiki/Single-machine_scheduling "spt") algorithm tells you to just do the quickest task first. 

If your tasks are not equal in importance, then placing a weight on each task and calculating the weight over time required ratio will help you decide which task to do; pick the project with highest weight over time.

Context switching is wasted time since it's not real work.

At its worst, context switching turns to thrash, when you get nothing productive done because you're too busy with only switching. Ways to avoid thrash include:

- Saying no to tasks, though the authors acknowledge we're often unable to do so
- Working dumber and more inefficently. Rather than think about the optimal way to get through your tasks, just start on something and get it done

## Bayes rule

Depends on the distribution. Power law, Normal, or Erlang. 

- Power law: the longer something has gone on, the longer we expect it to continue going on
- Normal: early events are surprising, late events are expected. 
- Erlang: events are never any more or less surprising e.g. a memoryless distribution like a roulette wheel

## Game theory

- If you play too many levels above your opponent, you're going to think they have information they don't actually have and they won't be able to think what you want them to think
- Every two player game has at least one [Nash Equilibrium,](https://en.wikipedia.org/wiki/Nash_equilibrium "nash") where both players are choosing the optimal strategy for themselve
- Finding Nash equilibrium though is an intractable problem
- The equilibrium may not be the outcome that is best for all players. We can quantify this as the "price of anarchy", which measures the gap between cooperation and competition. 
- [Mechanism design](https://en.wikipedia.org/wiki/Mechanism_design "mech") has a counterintuitive finding, that we can worsen every outcome but make everyone's lives better, by shifting the equilibrium

information cascades

## Footnotes

1. Easy enough to teach children, by telling them to memorise sums and when to carry a number, but surprisingly not obvious when trying to implement on a computer, see [full adder logic gate](https://www.electronics-tutorials.ws/combination/comb_7.html "full")
2. You might say that by the time I explain everything, I might as well have [written the entire book](https://en.wikipedia.org/wiki/P_versus_NP_problem "p np")
3. The percentage is 1 divided by e, euler's number
4. The base secretary problem assumes that you can't go back to a candidate that you passed on, but there are variations that resemble real life a bit more closely.
5. This problem is intractable if the probabilities of a payoff on a machine change over time; essentially meaning it's unsolvable. Some problems are intractable. In these cases, relaxing some constraints and accepting solutions that are "close enough" helps us significantly in structuring the problem.
6. Or March Madness, for the Americans
7. Only 9% of all scheduling problems can be solved efficiently.
8. As in, take all your projects that are late, and then the maximum of those. That's the metric you want to minimise.
9. 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/a16z gaming market size.png)

*If you liked this, sign up for my [finance and tech newsletter:](https://avoidboringpeople.substack.com/ "ABP")*

<div class="iframe-container-4x3">
  <p align="center"><iframe src="https://avoidboringpeople.substack.com/embed" frameborder="0" scrolling="no"> </iframe></p>
</div>
