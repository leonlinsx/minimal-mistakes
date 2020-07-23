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

### Only human after all

About a week ago, Sharif Shameem shared this video on twitter demonstrating the abilities of a new AI, GPT-3:

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">This is mind blowing.<br><br>With GPT-3, I built a layout generator where you just describe any layout you want, and it generates the JSX code for you.<br><br>W H A T <a href="https://t.co/w8JkrZO4lk">pic.twitter.com/w8JkrZO4lk</a></p>&mdash; Sharif Shameem (@sharifshameem) <a href="https://twitter.com/sharifshameem/status/1282676454690451457?ref_src=twsrc%5Etfw">July 13, 2020</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

And. Twitter. Freaked. Out.

Perhaps realising that their cushy jobs of [copying stack overflow answers](https://www.zdnet.com/article/the-most-copied-stackoverflow-java-code-snippet-contains-a-bug/ "SO") or [following the herd on oversubscribed rounds](https://twitter.com/nbashaw/status/1261328301953445890?s=20 "startup") were at risk \[1\], programmers and VCs alike on twitter started flooding the feed with GPT-3 demos and hot takes on this newest artificial intelligence. They're still going on, if you want to [take a look](https://twitter.com/hashtag/gpt3?lang=en "gpt3")

So, here I am, with my own hot take, to cash in on all that captivated audience for AI.

Hey man, I'm only human.

The article is split into 5 sections:

1. Explanation of what GPT-3 can do, why it's impressive, and why people are concerned
2. Slightly more technical overview of how language models worked before GPT-3
3. Slightly more technical overview of how GPT-3 works
4. How to detect text written by GPT-3
5. Implications of GPT-3

Let's get started.

### 1. GPT-3 is impressive because it can create intelligible outputs for a wide variety of use cases

[GPT-3](https://arxiv.org/pdf/2005.14165.pdf "GPT") was created by [OpenAI](https://openai.com/about/ "Open"), a company trying to "make sure artificial general intelligence benefits all of humanity," i.e. the robots don't kill us all. 

GPT-3 is a general language model, meaning it takes some words as input, and produces more words as output. Because it's a general model, it can solve many different types of tasks. You could ask it to write a paragraph about unicorns, translate a sentence, generate programming code, or more. 

Since it's a general model, you'd expect GPT-3 to be worse at a task than models specialised for that task e.g. when comparing GPT's translation results vs an algorithm only focused on doing translation, GPT won't be as good. 

Surprisingly and impressively, that's not always the case. Below is the table from the [GPT paper](https://arxiv.org/pdf/2005.14165.pdf "GPT") with the results of a translation test. For simplicity, we can just compare the first line representing a "State Of The Art" model against the last line representing the best performing GPT model \[2\]. A higher number is better here. We can see that for some of the translation tasks (particularly for translation to english), GPT is as good, if not better than State Of The Art models.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT preamble 1.png)

OpenAI tested GPT on a large variety of other tasks, such as text prediction, trivia questions without letting it search a seprate dataset, or determining what word a pronoun is referring to \[3\]. While GPT doesn't win on all cases, it gets great results in most of them. If you could only pick one model, you'd probably want to use GPT. It's like the [Simone Biles](https://www.nytimes.com/2019/10/13/sports/simone-biles-worlds.html "Simone") of the AI community, being top at many events and great at the rest.



better marketing department

but is preserved [here](https://antinegationism.tumblr.com/post/182901133106/an-eternal-howl "Moloch")

### 2. Overview of the seq2seq model used before GPT-3

*Disclaimer: The next two sections get slightly technical as I explain the models used. Feel free to skip over to the "How can we detect GPT-3?" section after if not feeling up to the challenge.*

*Further disclaimer: I'm not an ML expert, and the models involved are complicated. I'll be leaning on [this talk](https://www.youtube.com/watch?v=S0KakHcj_rs "talk") plus the other explanations linked at the bottom of this article. Feel free to reply with any corrections.*

**GPT-3 uses a different model** compared to traditional prediction models. However, it's still helpful to get the intuition behind the older models before looking at GPT-3. I'll first walk through an old model, and then walk through GPT-3. 

We'll start with the popular, older [sequence to sequence model.](https://google.github.io/seq2seq/ "seq") This is commonly abbreviated as "seq2seq", but to make things even easier to understand, I'll just refer to it as "old model", and GPT-3 as "new model."

Suppose we had a phrase, and wanted to predict the next phrase. We'd put our phrase through our algorithm, which is a series of functions, and then get the predicted output.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 1.png)

Every word matters, so we have to split up the input phrase and look at it one word at a time. e.g. "Had we but world enough and time" has different connotations vs "Had we but world enough and limes"

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 2.png)

Let's declutter the diagram, and just look at the first word. We pass that word through a function, and then get some temporary output. We know that we can represent words as numbers, since that's how computers process words \[30\]. So think of it as the word being transformed to some amount of numbers, having math done on it, and then getting another set of numbers after that. e.g. (1, 2, 3) times 2 equals (2, 4, 6). If you remember high school math, this is matrix multiplication or linear algebra. **Nearly all of the math below can be represented in some matrix multiplication form as well, for both this section and the next.**

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 3.png)

The function used is a [neural network, so it's more complicated than just multiplying by two.](https://towardsdatascience.com/learn-how-recurrent-neural-networks-work-84e975feaaf7 "neural") I'll gloss over exactly how those work as I've gone over the intuition before [here](https://avoidboringpeople.substack.com/p/the-next-machine-learning-startup "ML"), and it'll overly complicate this walk through. Free subs, email me and I'll forward. 

What's more important to understand here is that the word is transformed into something else. The model can control both how the word is initially turned into numbers, and what function we perform. e.g. instead of (1, 2, 3) times 2, we could have "Had" turned into (2, 3, 4), and then times 3 to equal (6, 9, 12)

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 4.png)

We're done with the first word, so let's move on to the second. What's different here is that we have that temporary output 1 from the first word \[31\]. We'll combine that, together with the second word, apply our function again, and get a new temporary output 2. 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 5.png)

At this point, you can infer where we're going for the rest of the sequence. Indeed, we just keep doing this until we end up at the last word of our input. We use the temporary output from one word to help with generating the temporary output of the next in a recurrent manner. 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 6.png)

Using that temporary output, we apply a different function, and that gets us two things. We get the first word of our output (after translating it back from numbers), and then another temporary output (still in numbers). In our example, we get the word "this". Awesome, finally some tangible progress!

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 7.png)

Now we have a temporary output, one actual output, and our new function. As you might have guessed, we can repeat this same step to get the next predicted word, and another temporary output. It's a recurring pattern again.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 8.png)

And just as in the earlier input scenario, repeat all the way until the end of the phrase.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 9.png)

And we're done with the old model! That was a lot, and obviously overly simplified, but we've gotten a high level understanding of the process. For more detail, you can check out the original paper [here](https://arxiv.org/abs/1409.3215 "paper")

Now here's a critical question that both tests our understanding and hints at the improvements in the new model. In the old model, could we solve any part of the process before we had solved the previous parts? e.g. could we get the temporary output for "time", without solving for "we" first? 

**No, since we had to run everything in sequence.** Both the position and the context of the words matter, so we want to process all of it one word at a time. We can't skip any parts, as every step is dependent on the previous one, in a recurring fashion. This is also why the old model is known as a [recurrent neural network](http://karpathy.github.io/2015/05/21/rnn-effectiveness/ "RNN"). Because of this, the computation of the prediction also becomes slow once our input text becomes large.

Enter the transformer model.

### 3. GPT-3 uses a transformer decoder model, a variation on the transformer model

GPT-3 stands for Generative Pretrained Transformer 3. The transformer in the name stands for the [transformer model, using an "attention" mechanism.](http://jalammar.github.io/illustrated-transformer/ "transformer") Both GPT-2 and GPT-3 use the same type of model, so any explanations you find of the former will generalise as well \[40\]. 

However, what I learnt just before I published this post was that **they actually use [a variation of the transformer model.](https://s3-us-west-2.amazonaws.com/openai-assets/research-covers/language-unsupervised/language_understanding_paper.pdf "variation")** Hence, let's first walk through a simplified version of the new model, what "attention" means, and then see how GPT-3's version is different. I'll indicate when we're leaving the regular transformer and using GPT-3's tweaks. 

For the new model, we'll go back to the start, with our input words and trying to get the output from them.  

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 2.png)

Now though, we want to evaluate all the input words at the same time, in parallel rather than in sequence. This will save us a lot of time computing the result, since we can use matrix math to calculate that in one shot. 

We convert our input words to numbers again, like we always do. This time though, we pass those numbers through 3 different functions, getting 3 temporary outputs for each word, a, b, and c. Note that it's just for simplicity that our word and outputs have 3 numbers; in practice they're hundreds of numbers long. We'll see how these 3 outputs are used shortly \[41\]. 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 10.png)

Let's declutter the diagram, and do those calculations for all the input words. We now have a, b, and c for all of our input words.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 11.png)

Now here's the problem we run into when we don't consider the input sequentially; researchers were stuck on this for a long time before the new model. As mentioned earlier, **both the position as well as the context for words matter. How can we get that when we don't evaluate sequentially?**

For example, take the sentence "The author drank even more coffee to finish his newsletter, because it wasn't done yet". Swapping the position of "coffee" with "newsletter" wouldn't make sense, so the computer needs to know that somehow. Additionally, the "it" here refers to the newsletter, and the computer also needs to know that context. In the old model, all that information is retained since we move one word at a time. In the new model, we need another method to obtain that information right from the start.

Notice from the diagram that we've calculated all those temporary outputs simultaneously, and none depend on the other. What we'll do next is take the first temporary output of the first word, and apply a function on that output with all the second temporary outputs of all the words. In the diagram, I've represented the results of these as the first temporary output "dot" the second temporary output e.g. 1a.2b

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 12.png)

We've taken something that was related to the first word, and linked it with something that was related to all the other words. Importantly, we don't have to do these caclulations sequentially, since the result of one doesn't flow into the other. We can repeat this for the rest of the words. Here I show the same step for word 2, just for clarity.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 13.png)

Let's return back to the first word. We're done with the a and b outputs, but still have c left. To nobody's surprise, we apply yet another function on all of these temporary dot outputs and all the c outputs. After that, we use yet another function, to turn all of those separate outputs into one single output. e.g. in this case we went from 7 outputs, to 1 single output 1z.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 14.png)

Ok, that was a lot of work. I swear, this makes sense to the people who came up with it. What we've just done is gone through [the steps of calculating "attention" for our words](http://jalammar.github.io/illustrated-gpt2/ "attention") \[42\]. The amount of "attention" word A has for another word, is how much word A should focus on it and hence how much context it should get. By associating components of the words with all other words, we solve for the context issue earlier. I'll skip the solving of the position issue for simplicity, just think of it as them adding more numbers to the original word based on word position \[43\].

We now have this new output, z, that has information from that particular word, as well as the context for other words in the input. We run this through another function (a feed forward neural network) to get yet another output, let's call them z\*. Nearly there.

We'll summarise all of the steps we just did and call them an "encoding" step. During "encoding", we transform our initial numbers for the word into new numbers that include more context from the other words around it. e.g. (1, 2, 3) becomes (5, 7, 0). Reminder that each word is actually hundreds of numbers, not just three.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 15.png)

The output z\* has the same number of elements in it as when we first transformed the word into numbers. The new model takes this result, and feeds it through the entire encoding process repeatedly. Think of it as multiple encoding layers e.g. doing the process 96 times.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 16.png)

After all this training, we have a final output from the encoding. Let's call them vf. Note that the calculation of one word's vf is still independent of the calculation of another word's vf. This parallelisation has saved us a lot of time. e.g. I can calculate 7_vf without knowing 1_vf first.

Now, we can use these final outputs, to start predicting our words. We pass all of these final outputs through another "decoding function", to get our first word \[44\]. There are differences between how the decoding function works vs the encoding function, but the steps are similar enough that we'll not walk through them again. You can think of the decoding function as doing all of those encoding steps, but also taking the output from the "encoding function" process \[45\]. I've put just one big block for "decoding functions" here, but the new model repeats this process the same number of times as the encoding process. e.g. if it had 96 encoding layers, it will have 96 decoding layers.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 17.png)

Now that we've got our first predicted word, we'll use that word together with the final outputs, and pass them through the decoding function again. If you squint, this looks really like the process in the previous old model section.  

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 18.png)

And once you repeat that process for all the words, you get the final phrase. Finally.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 19.png)

Alright, so that was the *general* transfomer model. Now let's throw all of that aside and start from scratch for GPT-3's version.

Kidding, don't freak out \[46\]. 

GPT-3 combines the encoding and decoding process, to get a [Transformer Decoder](https://arxiv.org/pdf/1801.10198.pdf "TD"). They combine the input and expected output sequence into a single "sentence" and then run that through the decoding layers. GPT-3 has 96 of these decoding layers \[47\]. The model is used to predict the next input and also the next output. 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 19b.png)

If this sounds a bit hand-wavy, that's because it is. I can't find any explanation of how they combine the steps online, besides the original paper and this random [github comment as confused as I am](https://github.com/openai/gpt-2/issues/157 "github"). It seems like the way they're predicting one word at a time would also imply we're back to the recursive issue, of processing the text sequentially. Maybe just throwing enough compute power at the problem was the solution. If anyone knows more, please email me.

Many people posting online all say that GPT-3 uses the traditional transformer, or transformer encoder-decoder model. They then explain the traditional transformer model in order to describe what's happening in GPT-3. **Yep, all those people are wrong,** just like I was until before I was corrected just before posting this.

If you're still with me, there's two more important features of the algorithm worth mentioning. 

Firstly, remember way back when we split the word into 3 different features, a, b, and c? The new model actually does that 96 times right from the start \[48\]. Each time it uses a different function, such that 96 different triplets are generated. Since these are independent, it runs all of these through the encoding/decoding layers at the same time, for all the input words. The results of these are merged together when getting that output from the encoding/decoding function, z. This is known as having "multiple attention-heads." 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 20.png)

Secondly, every time I mentioned function in this section, you can think of it as a weight or parameter on some number. **When you add up all the weights, the new model has 175bn of them.** No, that's not a typo. When people are referring to the number of parameters that GPT-3 uses, and how it's so much larger than previous models, this is what they are referring to. e.g. if each word was represented as a list of 1000 numbers, then you'd need that many parameters just to go through one function in the entire process outlined above. You can easily see how having a process with 96 layers and 96 alternatives within each layer gets you to a gargantuan number of parameters required. 

This was a long sidetrack, but you now have more intuition about what GPT-3 is doing. It's taking word inputs, performing multiple iterations of transformations via matrix math, and using that to predict or translate words. 

If that was a bit too convoluted, think of this simpler example. Imagine a [choose your own adventure game](https://en.wikipedia.org/wiki/Choose_Your_Own_Adventure "choose your own"), where your choices decide how the story ends. **GPT-3 is like that, except it has billions of available options, layered on top of each other.** The slightest difference in wording your choice will send you down a different direction. And the possible paths are virtually endless.

Having worked through all that, the transformer architecture from the original paper is below for reference. You can see how parts of it map to the simplified diagram we just thought through, with a few boxes that I've left out for simplicity \[49\]. GPT-3 uses the right side of this diagram only. If you're interested in learning more, there are additional references at the bottom of this article. 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 21.png)

### 4. How can we detect GPT-3?

We know GPT-3 is good, and that some samples of the output are difficult to distinguish from a human's writing. The natural question then, is to ask if there are other ways we can detect if text was written by a machine?

Turns out there's some surprisingly simple ways to do so. 

Firstly, [because of the hyperparameters used in GPT-3,](https://medium.com/analytics-vidhya/understanding-the-gpt-2-source-code-part-1-4481328ee10b "temp") **the frequency of words generated will not follow distributions expected from normal humans.** In the screenshot below, Gwern is explaining that this results in common words turning up even more than expected, and uncommon words not turning up at all. Temperature controls the randomness, and the top-k hyperparameter controls where the frequency cutoff point is for the top words chosen.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 22.png)

For those unfamiliar with Zipf's law, I've previously covered it [here](https://avoidboringpeople.substack.com/p/war-of-the-words "Zipf") when talking about searching for aliens (yes, aliens. Free subs email me and I'll forward). Essentially, it states that in a large sample of text, the frequency of any word is inversely proportional to its rank, when ranked by frequency of occurrence. e.g. the most common word is ~2x more frequent than the 2nd most common word.

I've plotted Zipf's law for my newsletter before, and it looks like the top graph. If GPT-3 were to write my articles, you'd expect something like the bottom instead (with more words of course, the example is just for illustrative purposes).

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 23.png)

Secondly, you can use another model to check the text. Analytics Vidhya did a post a while back on [how to detect computer generated articles.](https://www.analyticsvidhya.com/blog/2019/12/detect-fight-neural-fake-news-nlp/ "Vidhya") They provide a few tools such as a GPT-2 detector model or [Grover,](https://grover.allenai.org/detect "Grover") that can take sample text and tell you if they believe it was machine generated \[50\]. These tools were released before GPT-3 and have not been calibrated for it yet, but still perform well. They work because **the models are familiar with the quirks that other models use to generate text.**

Here's a demo. I went to the first sample in the appendix of the [GPT 3 paper (page 49)](https://arxiv.org/pdf/2005.14165.pdf "GPT"), and copied the machine generated poem there. Plugging that in to Grover's site, shows that Grover thinks it was machine generated. I'd probably not have guessed that correctly.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/GPT/GPT 24.png)

Of course, neither of these methods are foolproof. If you don't have a large enough sample size of text, it's hard to do frequency analysis or verify it via the checking models. If someone sends you a boilerplate legal wall of text just once, there might not be enough data to know for sure. I'm wondering how insulting it might be to reply asking if they were a bot...

Grover also gets false positives, such as wrongly claiming that Allen Ginsberg's poem [Howl](https://www.poetryfoundation.org/poems/49303/howl "Howl") was written by a machine \[51\]. And it also gets false negatives, thinking that text generated by GPT-3 was created by a human. [You can try playing around with it and see what works for you](https://grover.allenai.org/detect "Grover")

That said, having such methods still available make me less fearful of the dangers of fake machine generated text. Since both of the tools above rely on structural features of the models, it seems likely that as long as the models have hyperparameters to adjust, the text generated would be identifiable. 

In the worst case scenario, everyone will have to install some browser extension that scans the page and warns you if it thinks the text was fake. Perhaps something like the ad blockers of today? At that point though, should we even care?

### 5. Concluding thoughts

Access to the GPT-3 API is currently [subject to a waitlist,](https://openai.com/blog/openai-api/ "waitlist") as OpenAI wants to be careful about people misusing the model. If you're interested in the concept though, there are some workarounds.

- OpenAI released the code for GPT-2 (the older version of GPT-3) [here](https://openai.com/blog/better-language-models/ "2"), so you can run that yourself if you know how to set it up.

- The team at Hugging Face have built a more user friendly interface for GPT-2, as well as some other transformer based models. You can check that out [here](https://transformer.huggingface.co/ "transformer")

- [Aaron Tay](https://musingsaboutlibrarianship.blogspot.com "Aaron") also posted that using the premium "Dragon" version of [AI Dungeon](https://play.aidungeon.io/ "AI"), a text generator game using GPT, [supposedly gets you access to GPT-3](https://musingsaboutlibrarianship.blogspot.com/2020/07/playing-with-gpt-3-via-ai-dungeon.html "AI")



I'd controversially propose that GPT-3 tells us more about ourselves as humans, rather than about computers. It shows that we have a surprisingly wide range of tolerance for variation in the inputs we receive, whether that's prose, poetry, or pieces of music. Text that a computer would flag as machine generated would pass our instinctual tests, implying we are the more accomodating of the two. Perhaps it's that appreciation for ambiguity, that welcoming of the weird, that separates our synapse signals from bits and bytes. 



### Other interesting commentary

1. [Gwern showcases creative writing by OpenAI’s GPT-3 model, demonstrating poetry, dialogue, puns, literary parodies, and storytelling](https://www.gwern.net/GPT-3 "Gwern")
2. [Max Woolf on Tempering Expectations for GPT-3 and OpenAI’s API](https://minimaxir.com/2020/07/gpt3-expectations/ "Max")
3. [Kevin Lacker on Giving GPT-3 a Turing Test](http://lacker.io/ai/2020/07/06/giving-gpt-3-a-turing-test.html "Lacker")
4. [Michael Nielsen twitter thread](https://twitter.com/michael_nielsen/status/1284937254666768384?s=20 "Nielsen")
5. [Manuel Araoz on how OpenAI's GPT-3 may be the biggest thing since bitcoin](https://maraoz.com/2020/07/18/openai-gpt3/ "Maraoz")

### More detailed explanations

1. [Yannic's youtube video explaining the GPT 3 paper](https://www.youtube.com/watch?v=SY5PvZrJhLE&feature=youtu.be "Yannic"). Plus the GPT 3 paper itself ["Language Models are Few-Shot Learners"](https://arxiv.org/pdf/2005.14165.pdf "GPT3"). [Yannic's youtube video explaining the GPT 2 paper, which GPT 3 bases itself on.](https://www.youtube.com/watch?v=u1_qMdb0kYU "Yannic") Plus the GPT 2 paper itself ["Language Models are Unsupervised Multitask Learners"](https://d4mucfpksywv.cloudfront.net/better-language-models/language_models_are_unsupervised_multitask_learners.pdf "GPT2")
2. [Joseph Palermo](https://twitter.com/j_w_palermo "Joseph") of Dessa [speaking at Insight on Transformers.](https://www.youtube.com/watch?v=S0KakHcj_rs "youtube") I found this helpful due to the questions posed by audience members as lost as I was throughout the presentation.
3. [Andrew Ng on attention models](https://www.youtube.com/watch?v=SysgYptB198 "Ng")
4. [How do Transformers Work in NLP? A Guide to the Latest State-of-the-Art Models](https://www.analyticsvidhya.com/blog/2019/06/understanding-transformers-nlp-state-of-the-art-models/ "Vidhya")
5. [Jay Alammar on the illustrated transformer](http://jalammar.github.io/illustrated-transformer/ "transformer")

### Footnotes

1. I kid, I kid. Occasionally they play ping pong.
2. Apparently there are issues with directly comparing results. I'm not familiar with the details but it seems trying to standardise the primed data used. The paper says "However, our one / few-shot settings aren’t strictly comparable to prior unsupervised work since they make use of a small amount of paired examples (1 or 64). This corresponds to up to a page or two of in-context training data."
3. Context - "The LAMBADA dataset tests the modeling of long-range dependencies in text – the model is asked to predict the last word of sentences which require reading a paragraph of context"; Trivia - "On TriviaQA, we achieve 64.3% in the zero-shot setting, 68.0% in the one-shot setting, and 71.2% in the few-shot setting"; Pronous - "The Winograd Schemas Challenge is a classical task in NLP that involves determining which word a pronoun refers to, when the pronoun is grammatically ambiguous but semantically unambiguous to a human"
30. We're not exactly converting the words to binary representation here, if that's what you were thinking. Instead, we're [using a word embedding such as word2vec](https://towardsdatascience.com/learn-how-recurrent-neural-networks-work-84e975feaaf7 "word2") to generate varying numerical representations of the words that can be used in the algorithms moving forward. True, at the end of the day everything's converted to binary, but that's not at this point of the process.
31. Ok, so I'm pretty sure the first function actually has a [bias unit](https://ayearofai.com/rohan-5-what-are-bias-units-828d942b4f52 "bias"), so it also takes another input. But that overly complicates the main text explanation, so I'm leaving it out.
40. You can verify this in the [GPT-3 paper page 8,](https://arxiv.org/pdf/2005.14165.pdf "paper") where they say "We use the same model and architecture as GPT-2, including the modified initialization, pre-normalization, and reversible tokenization described therein, with the exception that we use alternating dense and locally banded sparse attention patterns in the layers of the transformer, similar to the Sparse Transformer"
41. This is the part of the transformer model where [they embed the word, and then calculate smaller query, key, and value vectors by mapping the embedded word vector on to a pre-trained weighted matrix.](https://youtu.be/S0KakHcj_rs?t=1083 "youtube") I'm still not fully clear on what the query, key, and values represent after watching all this reading and video watching. I'd suggest checking out the extra resources for more detail to see for yourself. My current intuition is that it's a decomposition of the word into something that can carry the weight of the word, the weight when it's compared to another, and a lookup match. 
42. The first step was getting the query, key, value vectors. Then we take the dot product of the query vector with the key vectors of other words to see how much focus to place on other words. Then we divide by the square root of the dimension of the key vectors. Then we do a [softmax function](https://towardsdatascience.com/softmax-function-simplified-714068bf8156 "soft"). Then we take multiply the results by the value vectors. And finally we take the sum of all that, to get one final vector to use in the next part of the process. 
43. They use sine and cosine functions, see [page 6 of the original paper](https://arxiv.org/pdf/1706.03762.pdf "sin"). They needed something periodic so that the model could extend to different interval lengths.
44. Technically there's another linear layer neural network and softmax layer [after the decoding layers](http://jalammar.github.io/illustrated-transformer/ "linear"), but have left out for simplicity. 
45. In the decoder, the outputs can only pay attention to output words that come before it, rather than the entire output sequence. This is known as "masking"
46. Though that's the feeling I had when I realised GPT doesn't use a standard transformer model. I really did think I was going to have to re-create all those diagrams. 
47. Per [page 8 of the paper (n layers)](https://arxiv.org/pdf/2005.14165.pdf "gpt")
48. Coincidentally the same as the number of repeat layers above, but doesn't have to be. Page 8 of the paper as well.
49. Ok, this looks scary, and I spent a long time reading and watching the vids before understanding what was going on. To map this to the model we walked through, let's start from the left. We've got inputs, they get embedded. So far that's the same as how our words got converted to numbers at the start. Then we have "positional encoding", which is the addition of the position numbers that I skipped over. Then we enter this box that starts with "multi-head attention" - we know this, we went through that entire process. There's this "add & norm" box that refers to [layer normalisation](https://mlexplained.com/2018/11/30/an-overview-of-normalization-methods-in-deep-learning/ "norm") that you can think of as scaling the numbers. Then this goes to the "feed forward" box, which is the neural network mentioned to get to z\*. Then we normalise again. This larger box has Nx on the outside, indicating we repeat this N times as desired. On the right, we see the outputs, do the embedding and encoding, and then enter the big box. The steps in there are similar to the left, except we do "masked" multi-head attention, and also take the output from the left box. Repeeat N times as desired. This then goes through a linear layer and a softmax function to get output probabilities for what words to output. Phew. Again, this is for the regular transfomer model. GPT-3 just uses the right hand side.
50. The post also links to a statistical analysis tool, [GLTR,](https://gltr.io/ "GLTR") that would be doing something similar to the Zipf's law analysis mentioned earlier.
51. To be fair, it definitely looks the part.

*If you liked this, sign up for my [finance and tech newsletter:](https://avoidboringpeople.substack.com/ "ABP")*

<div class="iframe-container-4x3">
  <p align="center"><iframe src="https://avoidboringpeople.substack.com/embed" frameborder="0" scrolling="no"> </iframe></p>
</div>
