---
title:  "Chandoo's excel worst practices"
tags: [investment banking, excel]
---

\* *Note: this is a backdated post from something I took notes on in the past*

I've improved my excel skills over the years, partly due to investment banking, and partly due to online excel help sites. There is a certain elegance and sense of satisfaction when putting together a formula that does exactly that niche purpose you wanted it for e.g. doing an index match when you have to dynamically find the row and column. Chandoo's site has been helpful over the years, and one post I like discusses common [worst practices among users.](https://chandoo.org/wp/analysis-worst-practices/ "excel worst practices') He talks about this from project level mistakes down to cell level errors.

Some worst practices to avoid include:

> **Asking wrong people**: In most analysis projects the people who will use outputs (consumers) are not the same people who may pay for it (buyers). For example, you may be designing a customer service dashboard that will be used by supervisors and store managers, but the people paying for it could be in marketing department. 

Understanding end user requirements and how to align incentives is important

> **Duplicate data**: Same data appearing several times across various data sets is a common problem. If you don’t know what is duplicated, you end up doing lots of extra steps even before starting the analysis

Ideally, data should be input once, and then referred to from that location. Particularly for banking, if you need to edit your inputs in more than one location, the chance of refreshing the deck and having missed out something increases dramatically

> **Merged cells**: These can cause a lot of heartache and slow down your workbooks. Keep merged cells to the headers / display part, but don’t merge things inside data section.

Merging is a convenient but annoying way to deal with formatting, since it prevents insertion of additional rows / columns

> **Using wrong tools for the job**: Imagine writing your own VBA code to find matching value in a column and to return corresponding value from another column. You would spend lots of time thinking about all scenarios for the code. But hey, why not use VLOOKUP() instead?

I'm also a fan of keeping models, formulas, and analysis simple. It's easier to understand, audit, and update. I like his table for the recommended tools per area of work

>  **Loyalty**: If you become too loyal to a particular tool / concept of doing things, then you will end up with extra work for solving even simple problems. For example, if you are a super fan of Excel formulas and use them for everything, then you would end up writing long formulas for simple things like removing duplicates from a list. 

This is related to the point above. It's harder to fix though since everyone has their own favourite and familiar formulas they prefer. 
