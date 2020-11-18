---
title:  "Does value add value?"  
tags: [value investing, value, finance, investing]
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

## Value investing 

We've talked about [whether investment bankers add value](https://avoidboringpeople.substack.com/p/do-investment-bankers-add-value "bank") (probably?), [whether companies add value](https://avoidboringpeople.substack.com/p/do-companies-add-value "co") (less than we think), and this week we'll wrap up the value series \[1\] by looking at whether value investing adds value.

The paper [Is (Systematic) Value Investing Dead?](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3554267 "paper") by Ronen Israel, Kristoffer Laursen, Scott Richardson at well-known investment firm AQR discusses whether value investing still works. This follows [an earlier paper this year](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3525096 "paper") from Fama and French, the professors who popularised value investing as an investment factor, which concluded that the return on value investing has declined in recent years \[2\]. In other words, it's not good to be a value investor anymore.

The AQR paper concludes (surprisingly) that despite weak performance lately, value investing per their definition isn't dead:

> Both from a theoretical and empirical perspective, expectations of fundamental information have been and continue to be an important driver of security returns. We also address a series of critiques levelled at value investing and find them generally lacking in substance. 

The paper first defines what they mean by value investing, then addresses criticisms, and ends with how they add on criteria to value investing to make it work better. It's also 57 pages, so let's summarise it in much less than that. I'll add on thoughts along the way as usual.

## Definitions

What exactly is meant by value investing? If we mean "buy low sell high," then by definition everyone is a value investor. You don't make money by selling something for less than you bought it \[3\].

If we mean "invest by some criteria that makes the company stock price look cheap," then we have a much more manageable problem to explore. 

That's why definitions are important. If your "later" in "I'm doing the dishes later" meant two weeks from now vs their "later tonight," you're going to have problems. 

To begin then, we need to define what is meant by "value", and then use that definition to sort stocks into "good value / cheap" and "bad value / expensive."

Fama and French first popularised the concept of "value" as an investment factor in their [1992 paper](https://rady.ucsd.edu/faculty/directory/valkanov/pub/classes/mfe/docs/fama_french_jfe_1993.pdf "paper"). By "value," they meant some calculable metric for a company that could be used to rank them. The original paper used the company's "book value" to "market value" as the metric, by calculating the ratio between the accounting number book equity value and the company's publicly traded stock equity value \[4\]. If the ratio was low (low book vs stock price), the company was cheap.

Over time, the ratios used have expanded to include other commonly used metrics. The AQR paper uses five as their definition of value: 

1. Book to price, what we just mentioned
2. Earnings to price i.e. net income over market cap
3. Forward earnings to price, i.e. sellside research analyst predicted future earnings over market cap
4. Sales to enterprise value. It's beyond the scope of this article to discuss the difference between enterprise and equity value; just treat them as the same if you're unfamiliar \[5\]
5. Cash flow to enterprise value

If all of that flew over your head, that's alright. Just think of it as AQR coming up with five ways of measuring whether a stock is cheap or not based on publicly available, relatively objective numbers. We need this in order to do value investing systematically based on those criteria. If not, there's no way of judging whether "value" works - what you say is cheap could be expensive to me \[6\].

**The general idea then is to invest in "cheap" companies, and profit when they become less cheap because prices converge to what the company "should" be worth.**

Sounds like it should work right? Well, let's see. 

![post]({{ site.url }}{{ site.baseurl }}/assets/images/value_investing/value 0.png)

## Criticisms

What they find is:

> Over the full sample period systematic value strategies generated positive risk adjusted returns. However, the last decade has seen a marked reduction in the performance of systematic value strategies

You can see this in their graph where they present Sharpe ratios for all their different value strategies over time. For those unfamiliar with Sharpe ratios, just think of them as "excess return," the higher the better. Notice how in the graph below past 2011, **all the returns go down and stay low. That's bad.**

![post]({{ site.url }}{{ site.baseurl }}/assets/images/value_investing/value 1.png)

Why is this happening? The AQR team looks at common criticisms of such a "systematic value investing" strategy that could explain this. They end up rejecting most of these criticisms, and proposing their own.

Criticism #1 is regarding one of the "value metrics," Book to Price. People have said for a while that this particular measure is outdated, and AQR generally agrees. I'll skip over the regression math \[7\]; the summary is that Book to Price doesn't work well, especially if you include Earnings to Price as a factor. However, AQR also adds on: 

> What does this mean for asset owners and asset managers interested in harvesting returns from value strategies? Focusing on just one fundamental anchor for intrinsic value is unlikely to be a successful strategy. Instead, ensure a multitude of fundamental measures are utilized to compare against price

> You need to expand your horizons when it comes to measuring value. Book value is not the only fundamental anchor for price

I suppose that's justfiable, though there's an issue with the above that I want to return to in the conclusion.

Criticism #2 is regarding how companies are doing more share repurchases lately, which could cause the metrics to be faulty and value investing to stop working. AQR finds that the amount of share repurchases hasn't had a significant effect on the performance of value: 

> Turning to the performance of value portfolios across share repurchase intensity partitions we see only mixed evidence of value working less well for the ‘High’ share repurchase sub-sample. 

> A key inference to be drawn here is that the recent under-performance of value strategies extends to value measures that attempt to correct for deficiencies in the financial reporting system. It appears unlikely that the growing importance of intangibles or changes in business models is explaining the underperformance of value strategies. 

> Long-short, industry-neutral value portfolios exhibit little sensitivity with the level of interest rates (either the level of 3-month rates or 10-year yields, or the slope between them). There is, however, some evidence that the performance of value strategies is positively related with changes in the slope of the yield curve for both US and international stocks (i.e., value stocks do poorly when the yield curve flattens)

> If anything, value spreads have widened in recent years making crowding an unlikely explanation for the recent drawdown.

## Adding criteria to value

> When value underperforms the most, it is due to a combination of deterioration in fundamentals of cheap stocks (but not too much greater than normal) and a widening in the gap between prices and fundamentals (but considerably more so than average).

> Consistent with the earlier results, fundamentals do matter for stock returns, but there are periods where stock prices become less connected with fundamental information, and in such periods value strategies under-perform. This has happened before, is happening now, and will likely happen again. 

## Footnotes

1. I would like to say this was planned from the start of this month, but it was a coincidence.
2. I'm simplifying in the main text here, they actually say that although the return has declined in the latter half of the July 1963-June 2019 period, [there's not enough data yet to conclude if value investing as an investment factor works or not.](https://www.institutionalinvestor.com/article/b1k3pd2z3ptx9g/Ken-French-There-Is-No-Way-to-Tell-If-Value-Premium-Is-Disappearing "ii") Note I'm using investment factor here as something specific, i.e. a filterable criteria to weight an investment portfolio by, as mentioned later in the main text.
3. Don't @ me with some contrived hedged insurance strategy when you know the point I'm making here.
4. People also use the reverse, of [price to book](https://en.wikipedia.org/wiki/P/B_ratio "pb"). See the link for details on the calculations.
5. "EV is computed as the sum of total equity market capitalization, preferred stock, minority interest and total debt. The latter three components are based on reported book values, not market values, as it is difficult to get reliable market data for these items for our global sample of firms (and the differences between book and market value is likely to be small for most firms)"
6. This doesn't totally resolve the problem of course, and is why so many people still argue about definitions and measurements today. It's one way of making the problem statement easier to explore though so we'll stick with it for lack of better alternatives.
7. The details are on pdf pg 16. "If you limit the sample to just the largest stocks, and focus on simple sort portfolios, then B/P is not significant in the presence of E/P."

*If you liked this, sign up for my [finance and tech newsletter:](https://avoidboringpeople.substack.com/ "ABP")*

<div class="iframe-container-4x3">
  <p align="center"><iframe src="https://avoidboringpeople.substack.com/embed" frameborder="0" scrolling="no"> </iframe></p>
</div>
