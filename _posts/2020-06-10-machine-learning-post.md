---
title:  ""  
tags: []
published: false
---

### Takeaway

Machine learning is less scary than you think, and more common than you think.

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

### Machine learning magic

We hear about machine learning (ML), deep learning, or artifical intelligence all the time now \[1\]. 

From search interest: 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/ML search trends.png)

To mentions in books: 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/ML book trends.png)

To newspaper headlines about robots taking over our jobs:

![post]({{ site.url }}{{ site.baseurl }}/assets/images/NYT ML.png)

There's increased interest in ML, and it seems that every other day there's a new startup raising $100mm based on their newfangled ML technology. 

However, most people are intimidated by ML, equating it to magic that only cutting edge startups do. It doesn't help that the math can be intimidating: 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/ML andrew ng math.png)

Today I want to help you get a better intuition of ML, by first looking at a company using ML, and then walking through the basics of how a neural net works. My goal at the end of this is for you to feel less scared whenever someone throws around the term "ML" as though they're too cool for school.

### Machine learning case study

Imagine I came to you looking for investment in a company using ML. Here's the pitch:

"Company M uses ML and [optical character recognition (OCR)](https://en.wikipedia.org/wiki/Optical_character_recognition "OCR") to match input data against hundreds of millions of records within fractions of a second. It already has partnerships with Amazon, the US government, and Fedex. Company M has already scaled up to allow >100bn transactions yearly, and has expanded coverage to all of the US."

Sounds exciting right? I cherry-picked some of the language, but it isn't too far off from [actual press releases by other companies:](https://www.eu-startups.com/2020/01/anyline_raises_over_10_million_and_zooms_to_us/ "eu")

"Anyline, a leading startup in Optical Character Recognition (OCR) using AI for text recognition, has raised €10.7 million in Series A funding. The Austrian startup, which is already working with big names like Toyota, IBM, Canon, the UN and PepsiCo, will use the funds to open its first US office in Boston"

But back to company M. The OCR part refers to them looking at an image and recognising what it says via ML. It looks like they do that efficiently, accurately, and at scale. Their partnerships also seem respectable. You probably think they're a promising startup led by Stanford grads who started coding in diapers.

Would you invest?

If you said yes, you just invested in the [United States Postal Service](https://www.enterpriseai.news/solution_content/hpe/governmentacademia/machine-learning-applications-for-the-modern-enterprise/ "USPS"). 

No, really, the post office has been using ML for a long time. [They started trialing it in 1997, and by 2014 were already mostly recognising addresses via ML algorithms.](https://www.buffalo.edu/content/dam/www/research/pdf/Postal-Automation-Highlights_20160516.pdf "ML") Not quite the startup stereotype you were imagining.

My point here isn't to crap on Anyline, or startups similar to it. I'm sure they're solving difficult problems and are not pure hype \[2\]. Rather, I want to make you realise that ML is being used in mundane sounding scenarios, and has been for some time now. The next time someone pitches you on ML, keep that in mind.

### Machine learning intuition

Now that we know where ML is used, let's walk through how ML can work. I'll use a [neural network](http://news.mit.edu/2017/explained-neural-networks-deep-learning-0414 "NN") for this, though there are many other ways ML can be run. 

Neural networks are modelled after the brain's connection of neurons. Here's what a neuron looks like:

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Neuron design.jpg)

While we still [aren't quite sure how the brain works, a leading theory is that the neurons can take inputs, do some computation, and then send outputs.](https://www.quantamagazine.org/neural-dendrites-reveal-their-computational-power-20200114/ "neural") \[3\] A simplified way of representing two neurons interacting could be like this:

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Neuron 1.png)

And if you had three pairs of neurons, it could look like this:

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Neuron 2.png)

And if the neurons could interact with each other, it could look like this \[4\]: 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Neuron 3.png)



*If you liked this, sign up for my [finance and tech newsletter:](https://avoidboringpeople.substack.com/ "ABP")*

### Footnotes

1. I'll use machine learning (ML), deep learning(DL), or artifical intelligence (AI) interchangeably throughout the post, but technically they're different things, [some being a subset of the other.](https://towardsdatascience.com/clearing-the-confusion-ai-vs-machine-learning-vs-deep-learning-differences-fce69b21d5eb "ML") For the sake of the post it doesn't really matter though.
2. Well, some are probably complete cons
3. I'm not a scientist, correct me if I'm wrong here.
4. I've shown all the inputs into one neuron as one colour and size for ease of understanding, especially when translating it to the neural network math. You could think of the groupings in other ways though, such as all the outputs from one neuron as one colour. 

<div class="iframe-container-4x3">
  <p align="center"><iframe src="https://avoidboringpeople.substack.com/embed" frameborder="0" scrolling="no"> </iframe></p>
</div>
