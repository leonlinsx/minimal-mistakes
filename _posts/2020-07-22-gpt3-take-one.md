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

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">This is mind blowing.<br><br>With GPT-3, I built a layout generator where you just describe any layout you want, and it generates the JSX code for you.<br><br>W H A T <a href="https://t.co/w8JkrZO4lk">pic.twitter.com/w8JkrZO4lk</a></p>&mdash; Sharif Shameem (@sharifshameem) <a href="https://twitter.com/sharifshameem/status/1282676454690451457?ref_src=twsrc%5Etfw">July 13, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>


but is preserved [here](https://antinegationism.tumblr.com/post/182901133106/an-eternal-howl "Moloch")

### Overview of the seq2seq model before GPT-3

*Disclaimer: The next two sections get slightly technical as I explain the models used, feel free to skip over to the "Detecting GPT-3" section after if not feeling up to the challenge.*

*Further disclaimer: I'm not an ML expert, and the models involved are complicated. I'll be leaning on [this talk](https://www.youtube.com/watch?v=S0KakHcj_rs "talk") plus the other explanations linked at the bottom of this article. Feel free to reply with any corrections.*

GPT-3 uses a different model compared to traditional prediction models. However, it's still helpful to get the intuition behind the older models before looking at GPT-3. I'll first walk through an old model, and then walk through GPT-3. 

We'll start with the popular older [sequence to sequence model.](https://google.github.io/seq2seq/ "seq") This is commonly abbreviated as "seq2seq", but to make things even easier to understand, I'll just refer to it as "old model", and GPT-3 as "new model."

Suppose we had a phrase, and wanted to predict the next phrase. We'd put our phrase through a series of functions, and then get the predicted output.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 1.png)

Every word matters, so we have to split up the input phrase and look at it one word at a time. e.g. "Had we but world enough and time" has different connotations vs "Had we but world enough and limes"

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 2.png)

Let's declutter the diagram, and just look at the first word. We pass that word through a function, and then get some temporary output. We know that we can represent words as numbers, since that's how computers process words \[30\]. So think of it as the word being transformed to some amount of numbers, having math done on it, and then getting another set of numbers after that. e.g. (1, 2, 3) times 2 equals (2, 4, 6)

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 3.png)

The function used is a [neural network, so it's more complicated than just one step arithmetic.](https://towardsdatascience.com/learn-how-recurrent-neural-networks-work-84e975feaaf7 "neural") I'll gloss over exactly how those work as I've gone over the intuition before [here](https://avoidboringpeople.substack.com/p/the-next-machine-learning-startup "ML"), and it'll overly complicate this walk through. Free subs, email me and I'll forward. 

What we need to understand here is that the word is transformed into something else. The model can control both how the word is initially turned into numbers, and what function we perform. e.g. instead of (1, 2, 3) times 2, we could have "Had" turned into (2, 3, 4), and then times 3 to equal (6, 9, 12)

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 4.png)

We're done with the first word, so let's move on to the second. What's different here is that we have that temporary output 1 from the first word \[31\]. We'll combine that, together with the second word, apply our function again, and get a new temporary output 2. 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 5.png)

At this point, you can infer where we're going for the rest of the sequence. Indeed, we just keep doing this until we end up at the last word of our input, in a recurring pattern.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 6.png)

Using that temporary output, we apply a different function, and that gets us two things. We get the first word of our output (translated back from numbers), and then another temporary output (still in numbers). In our example, we get the word "this". Awesome, finally some tangible progress!

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 7.png)

Now we have a temporary output, one actual output, and our new function. As you might have guessed, we can repeat this same step to get the next predicted word, and another temporary output. It's a recurring pattern again.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 8.png)

And just as in the earlier input scenario, repeat all the way until the end of the phrase.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 9.png)

And we're done with the old model! That was a lot, and obviously overly simplified, but we've gotten a high level understanding of the process. For more detail, you can check out the original paper [here](https://arxiv.org/abs/1409.3215 "paper")

Now here's a critical question that both tests our understanding and shows the improvements in the new model. In the old model, could we solve any part of the process before we had solved the previous parts?

**No, since we had to run everything in sequence.** We need the result from the previous step, in order to predict the next step. We can't skip any parts, as every step is dependent on the previous one, in a recurring fashion. This is also why the old model is known as a [recurrent neural network](http://karpathy.github.io/2015/05/21/rnn-effectiveness/ "RNN"). Because of this, the computation of the prediction also becomes slow once our input text becomes large.

Enter the transformer model.

### Overview of GPT-3 model

GPT-3 stands for Generative Pretrained Transformer 3. The transformer in the name stands for the [transformer model, with attention.](http://jalammar.github.io/illustrated-transformer/ "transformer") Both GPT-2 and GPT-3 use the same type of model, so any explanations you find of the former will generalise as well \[40\]. Let's walk through a simplified version of the new model.

We'll go back to the start, with our input words and trying to get the output from them.  

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 2.png)

Now though, we want to evaluate all the input words at the same time, in parallel rather than in sequence. This will save us a lot of time computing the result. 

We convert our input words to numbers again, like we always do. This time though, we pass those numbers through 3 different functions, getting 3 temporary outputs for each word. Note that it's just for simplicity that our word and outputs have 3 numbers; in practice they're hundreds of numbers long \[41\]. 

### Detecting GPT-3

Zipf

Analytics Vidhya did a post a while back on [how to detect computer generated articles.](https://www.analyticsvidhya.com/blog/2019/12/detect-fight-neural-fake-news-nlp/ "Vidhya") They provide a few tools and links, such as [Grover,](https://grover.allenai.org/detect "Grover") that can take the text and tell you if they believe it was machine generated.

Here's a demo. I went to the first sample in the appendix of the [GPT 3 paper (page 49)](https://arxiv.org/pdf/2005.14165.pdf "GPT"), and copied the machine generated poem there. Plugging that in to Grover's site, shows me that Grover thinks it was machine generated. 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/a16z gaming market size.png)



### Other interesting commentary

1. [Gwern showcases creative writing by OpenAI’s GPT-3 model, demonstrating poetry, dialogue, puns, literary parodies, and storytelling](https://www.gwern.net/GPT-3 "Gwern")
2. [Max Woolf on Tempering Expectations for GPT-3 and OpenAI’s API](https://minimaxir.com/2020/07/gpt3-expectations/ "Max")
3. [Kevin Lacker on Giving GPT-3 a Turing Test](http://lacker.io/ai/2020/07/06/giving-gpt-3-a-turing-test.html "Lacker")
4. [Michael Nielsen twitter thread](https://twitter.com/michael_nielsen/status/1284937254666768384?s=20 "Nielsen")
5. [Manuel Araoz on how OpenAI's GPT-3 may be the biggest thing since bitcoin](https://maraoz.com/2020/07/18/openai-gpt3/ "Maraoz")

### More detailed explanations

1. [Yannic's youtube video explaining the GPT 3 paper](https://www.youtube.com/watch?v=SY5PvZrJhLE&feature=youtu.be "Yannic") and the GPT 3 paper itself ["Language Models are Few-Shot Learners"](https://arxiv.org/pdf/2005.14165.pdf "GPT3")
2. [Yannic's youtube video explaining the GPT 2 paper, which GPT 3 bases itself on.](https://www.youtube.com/watch?v=u1_qMdb0kYU "Yannic") Plus the GPT 2 paper itself ["Language Models are Unsupervised Multitask Learners"](https://d4mucfpksywv.cloudfront.net/better-language-models/language_models_are_unsupervised_multitask_learners.pdf "GPT2")
3. [Andrew Ng on attention models](https://www.youtube.com/watch?v=SysgYptB198 "Ng")
4. [How do Transformers Work in NLP? A Guide to the Latest State-of-the-Art Models](https://www.analyticsvidhya.com/blog/2019/06/understanding-transformers-nlp-state-of-the-art-models/ "Vidhya")
5. [Jay Alammar on the illustrated transformer](http://jalammar.github.io/illustrated-transformer/ "transformer")

### Footnotes

1. 
30. We're not exactly converting the words to binary representation, if that's what you were thinking. Instead, we're [using a word embedding such as word2vec](https://towardsdatascience.com/learn-how-recurrent-neural-networks-work-84e975feaaf7 "word2") to generate varying numerical representations
31. Ok, so I'm pretty sure the first function actually has a [bias unit](https://ayearofai.com/rohan-5-what-are-bias-units-828d942b4f52 "bias"), so it also takes another input. But that overly complicates the main text explanation, so I'm leaving it out.
40. You can verify this in the [GPT-3 paper page 8,](https://arxiv.org/pdf/2005.14165.pdf "paper") where they say "We use the same model and architecture as GPT-2, including the modified initialization, pre-normalization, and reversible tokenization described therein, with the exception that we use alternating dense and locally banded sparse attention patterns in the layers of the transformer, similar to the Sparse Transformer"
41. This is the part of the transformer model where [they embed the word, and then calculate smaller query, key, and value vectors by mapping the embedded word vector on to a pre-trained weighted matrix](https://youtu.be/S0KakHcj_rs?t=1083 "youtube")

*If you liked this, sign up for my [finance and tech newsletter:](https://avoidboringpeople.substack.com/ "ABP")*

<div class="iframe-container-4x3">
  <p align="center"><iframe src="https://avoidboringpeople.substack.com/embed" frameborder="0" scrolling="no"> </iframe></p>
</div>
