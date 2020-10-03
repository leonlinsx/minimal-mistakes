---
title:  ""  
tags: [history, machine learning, prediction, random, complex]
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

## Predicting history

We live in historic times.

Do we really though? Put another way, would you know whether an event is historic or not, while you're living through it?

The paper ["Predicting history"](https://www.gwern.net/docs/history/2019-risi.pdf "predict") \[1\] makes the claims that:

- many events that will one day be viewed as historic attract little attention at the time
- machine learning models show increasing, rather than decreasing error rates the more data they're given to predict
- there are limits to predictability in complex social systems, and historical significance is difficult to predict

The paper's a short six pages, but rather dense, so I'm going to just pull out the highlights and give more context to their conclusions.

They start by giving an anecdote:

> Danto imagined a hypothetical entity—the ideal chronicler—that possesses complete information about the state of the world, along with its entire history up to that point, and unlimited ability to integrate and analyse that information. 

How would this chronicler fare on judging if an event was significant?

> Danto then argued that the ideal chronicler would still be unable to anticipate the significance that will be assigned to contemporaneous events by future historians because their judgements are inevitably informed by events that have not yet taken place.

This is a strong claim to make, since many events seem to be "easily" classified as historic:

> One can also easily think of other events, such as Einstein’s formulation of special relativity, the moon landing, the fall of the Berlin Wall and the discovery of the double-helical structure of DNA, that were immediately hailed as historic and continue to be viewed that way decades later

To formulate the problem in a way that's conducive for a hypothesis, the team then looked at a collection of US Department of State records \[2\]. They scored each record based on 1) how important historians at the time would have viewed that event, and 2) how important historians now view that event.

For example, Record A "Travel schedule of Ambassador Alex" would likely be unimportant then and now. Record B "Secret plans for [Iran hostage crisis](https://en.wikipedia.org/wiki/Iran_hostage_crisis "crisis") would probably be important then and now. Record C "Check out this new movie Star Wars" might be unimportant then, important now.

They then trained a machine learning model on the categorised data, aiming to see if:

1. An event's importance as it was happening can predict how historians now view it
2. The model could accurately classify events that would become important

One big problem in this approach is that, by definition, there are more "unimportant" events than "important" events. To make this more concrete: Imagine if you only had to pick between two events, choosing one of them to be important. It's easier to do so, compared to picking one important event out of a thousand unimportant ones.

Building on that, the researchers found that as the dataset approached a more realistic distribution (i.e. more unimportant events), the correlation between 1) how important historians in the past viewed an event, vs 2) how important historians now view that event, dropped a lot. 

In the graph below, the x-axis is the ratio of non-important events to important events (as defined by historians now). The y-axis is the correlation between views in the past and views now. As you can see, the correlation keeps dropping. If historians of the past were good at predicting significance, you'd have seen a flatter line.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/historical 1.png)

This implies that it is difficult on average to know if an event is significant while it is happening; there's too much noise vs signal. There's no evidence for statement 1 above.

On to statement 2, whether a well-trained machine learning model can do a better job. The team was able to use more metadata associated with the dataset, such as date, length, subject title etc, in training the model. Additionally, they could train the model iteratively, as is standard in any machine learning process \[3\].

They found that this model does better than the humans mentioned earlier. As seen in the graph below, the blue line (model) has a higher score at every point compared to the red line (humans). That's promising.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/historical 2.png)

However, the score is still terrible (low) once you get closer to a real world distribution, where you have many unimportant events vs important events. That's a problem.

The researchers conclude:

> Therefore, on balance, our results suggest that Danto was substantively correct. As the number of events being evaluated grows, successful predictions will be increasingly outnumbered by events that seem insignificant at the time, but which come to be viewed as important by future historians in part because of events that have not yet taken place. 

It's hard to identify significance ahead of time. The researchers believe that this can be explained due to: 

> More generally, our results provide further evidence for the observation that the combination of nonlinearity, stochasticity and competition for scarce attention that is inherent to human systems poses serious difficulties for ex ante prediction

Essentially saying the world is a complex system, and things can only be evaluated on hindsight.

If you want to follow this line of thinking, some additional reading of interest would be Nassim Taleb's Fooled by Randomness (I've written notes on it [here](https://www.leonlinsx.com/fooled-by-randomness-notes/ "lls")), or content on [complex systems](https://en.wikipedia.org/wiki/Complex_system "complex"), such as the work [Santa Fe Institute](https://www.santafe.edu/ "SF") is doing. 

## Footnotes

1. By Joseph Risi, Amit Sharma, Rohan Shah, Matthew Connelly, Duncan Watts. h/t [Josh Wolfe](https://twitter.com/wolfejosh?s=20 "Josh")
2. Specifically, they used a now declassified collection of 1,952,029 state department cables from [1973-1979](http://history-lab.org/cables "cable"), treating each cable as a single event. Cables were the main form of communicating important information then, and while the dataset only captures a small bit of all international events, the team thought it should capture any important US events. The majority of cables were also unimportant matters, giving more data to work with for the hypothesis.
3. They used [gradient boost](https://www.youtube.com/watch?v=3CC4N4z3GJc "grad"), included "many thousands of features, including additional metadata as well as the cable’s content (that is, the message text)", and also an unsupervised topic model in order to characterise the cable topics. Machine learning is iterative, in that the entire aim is to retrain so that you can get better weights for the model to use in the next run.

*If you liked this, sign up for my [finance and tech newsletter:](https://avoidboringpeople.substack.com/ "ABP")*

<div class="iframe-container-4x3">
  <p align="center"><iframe src="https://avoidboringpeople.substack.com/embed" frameborder="0" scrolling="no"> </iframe></p>
</div>
