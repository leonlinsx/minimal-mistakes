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

Last week, we looked at [how companies use machine learning to take data, process it, and come to a conclusion.](https://avoidboringpeople.substack.com/p/the-next-machine-learning-startup "ML") 

This week, we'll look at a more human oriented process, by walking through how analysts at an investment firm obtain data, analyse it, and form an investment thesis. We read that investors [are spending >$30bn on data](https://www.ft.com/content/222855de-4fbf-11e9-9c76-bf4a0ce37d49 "spend"), so where is all that money going to? 

I'll be doing this from a typical [long/short fundamental hedge fund](https://en.wikipedia.org/wiki/Long/short_equity "LS") point of view, rather than a quantitative firm \[1\]. For convenience I'll also be discussing this from a US company perspective, though the general process below applies internationally.

My goal is for you as a retail investor to have a better understanding of the edge that professionals have, and what that implies on the edge that you can have \[2\].

#### Public data

Publicly listed companies [have to file financial statements regularly with the SEC.](https://www.sec.gov/edgar.shtml "SEC") These are publicly available on both the company investor relations pages and [SEC Edgar](https://www.sec.gov/edgar/searchedgar/companysearch.html "Edgar") for you to search through. 

Companies also hold regular earnings calls for each major earnings announcement, which anyone can dial into \[3\]. The call transcripts can sometimes be found on the investor relations pages as well, or at [Seeking Alpha.](https://seekingalpha.com/earnings/earnings-call-transcripts "SA") However, they can be harder to track down than the financial statements.

Companies usually release news via [PR newswire](https://prnewswire.mediaroom.com/about-pr-newswire "PR") while also posting it on their own website. Such news could be the financial filings mentioned above, or special events such as acquisitions and management changes. The news gets distributed via PR newswire to other news sites.

Besides the public data mentioned above, an analyst would be spending time taking in twitter, googling google, or reading reddit. Primary or secondary information found there is also helpful. 

This is one part of the investment research process, the discovery and usage of publicly available information that everyone can do as well. From the above, you already have enough data to build a company financial model, analyse trends, and form an investment thesis. In fact, many retail investors never go beyond this part, and still do well for themselves. As I've mentioned before, there's many ways to be successful in investing.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Invst data 1.png)

#### Access to public data

So if that's all that's needed, why do so many other companies exist to provide information to investors? How does Bloomberg make [$20k a year a single subscription?](https://www.vox.com/2020-presidential-election/2019/12/11/21005008/michael-bloomberg-terminal-net-worth-2020 "Bloomberg")

Well, it turns out that:

1. Obtaining data directly from SEC Edgar is a huge pain
2. People always want more data, since they believe more data is better
3. There's a lot of other non-public data that you can get

In this section I'll discuss the first point, that of the user experience.

Let's say you wanted to quickly look at a company's revenue over time. If you did it the traditional way on Edgar, you'd have to search for the company, resulting in a page like this:

![post]({{ site.url }}{{ site.baseurl }}/assets/images/SEC Edgar screen.png)

You'd then have to look for each filing that you wanted, download all of them, and copy the data into a spreadsheet \[4\]. After you cleaned the data and added in rows to do the year over year calculations, you'd finally get the trends you wanted. 

That was a lot of work for very little payoff, which is why companies like Bloomberg, FactSet, Thomson exist. They gather financial data, and have it easily accessible within the platform. 

All that work you did in finding one company's reveues? FactSet has it available, for all public companies:

![post]({{ site.url }}{{ site.baseurl }}/assets/images/FactSet screenshot.png)

Of course, the data stored is not always perfect \[5\]. However, for all the times you need something quick to reference, platforms that have already done all the work in an easily digestible format are invaluable. You don't need to spend hours pulling data when it's available from a few keyboard entries.

There are also copmanies like BamSEC and Last10K, which aim to make finding the filings easier. For example, BamSEC will categorise different types of filings together, show titles for the filings, and allow you to quickly find previous editions of filings. These companies don't have as much features as the platforms above, but still save time for an analyst.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Invst data 2.png)

#### Access to sellside research data 

Besides providing aggregated financial data on companies, the Bloomberg etc platforms also provide sellside research estimates. As a reminder, these researchers are people at investment banks that publish reports on the company. These are usually the people being referenced when the news says "an analyst downgraded a company to a sell" or "banks raise the price target of a company."

Sellside research comes up with their own financial models with estimates for future company financials, supposedly using the model to come on a price target \[6\]. They provide this data to the platforms, who then show it to the investor community.

Many investors like to see these sellside numbers, in order to get an idea of where market consensus is. For example, if the mean of all estimates for next year's revenue is $100, but you think it'll be $1000, you're either about to have a really good time or a really bad one.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Invst data 3.png)

#### Access to company management



### Footnotes

1. I don't have experience in a quant firm, so can't speak to that personally. I do know they pay for order flow though, and that's likely included in the $30bn figure. Separately, note that an investment firm like a hedge fund is different from an investment bank; most investment analysts do compeletely different jobs than investment bankers. [Sellside equity research is the role most similar to a hedge fund analyst, but researchers don't actually invest money.](https://avoidboringpeople.substack.com/p/you-dont-want-quality-time-you-want "Sellside") 
2. Edge here refers to the relative advantage you have against your competition. We discussed [why this was important in investing last month.](https://avoidboringpeople.substack.com/p/relatively-speaking-the-billionaire "edge") Shoutout to Barak Paz for nudging me to write on this based on a convo we had.
3. But usually not ask questions. Some rare companies let the public ask questions, most of the times the questions are coming from sellside research (not buyside investment analysts)
4. It's even worse if you're pulling data from 8Ks rather than 10Q/Ks. Notice how there are no titles because the SEC likes seeing you suffer.
5. A large part of investment banking is actually downloading the data and then making the adjustments needed to "accurately" reflect the company. Accurately here referring to whatever your boss feels like showing.
6. Whether they have a price target in mind and then adjust the numbers to fit, or the other way round, I'll leave you to decide. Note that this critique can apply both to sellside and to buyside investors

*If you liked this, sign up for my [finance and tech newsletter:](https://avoidboringpeople.substack.com/ "ABP")*

<div class="iframe-container-4x3">
  <p align="center"><iframe src="https://avoidboringpeople.substack.com/embed" frameborder="0" scrolling="no"> </iframe></p>
</div>
