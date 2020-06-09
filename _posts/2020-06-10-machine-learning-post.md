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



*If you liked this, sign up for my [finance and tech newsletter:](https://avoidboringpeople.substack.com/ "ABP")*

### Footnotes

1. I'll use machine learning (ML), deep learning(DL), or artifical intelligence (AI) interchangeably throughout the post, but technically they're different things, [some being a subset of the other.](https://towardsdatascience.com/clearing-the-confusion-ai-vs-machine-learning-vs-deep-learning-differences-fce69b21d5eb "ML") For the sake of the post it doesn't really matter though.

<div class="iframe-container-4x3">
  <p align="center"><iframe src="https://avoidboringpeople.substack.com/embed" frameborder="0" scrolling="no"> </iframe></p>
</div>
