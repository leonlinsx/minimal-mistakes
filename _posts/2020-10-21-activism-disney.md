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

The activist investment fund Third Point recently published a [letter to Disney,](https://www.valuewalk.com/2020/10/third-point-walt-disney-company/ "disney") suggesting actions the company can take \[1\]. This led to [a rebuttal by another investment firm](https://valueinvestingworld.substack.com/p/chris-bloomstrans-letter-to-the-walt "Semper"), Semper Augustus (h/t Joe Koster). It's less common for investment firms to provide counterarguments against an activist, so let's take a look at both sides \[2\].

To set the stage, let's briefly go over activism and Disney's business, for those unaware.

### Overview on activism

Activist funds like Third Point [usually take a small stake in a company before publicly agitating for company management to take actions which the activists believe will increase company value, usually defined as increasing the stock price.](https://en.wikipedia.org/wiki/Activist_shareholder "activism") These actions could include paying a dividend, selling off bad business units, or replacing company management. They've risen in popularity the past decade; back when I was in banking I even worked on defending a company against an activist proxy fight (which went horribly, but that's a separate story).

Famous funds and investors include Carl Icahn, Bill Ackman's Pershing Square, and David Einhorn's Greenlight Capital. Since activists want to be listened to, they're usually higher profile than other hedge funds. It helps them when they get press.

Success for an activist investor looks like this: buy stock in a company, tell the company what to do, company does it, stock price goes up, everyone's happy, activist sells stock and takes profit. Most activists are short term holders, though there are exceptions.

Failure could be any part of that step failing. For example, a company might not listen to you. And even if they did, maybe the stock price doesn't move.

Now that we have a rough understanding of activism, let's look at Disney.

### Overview of Disney

I never covered Disney when I was in long/short investing; a colleague did. Nevertheless, let's take a look at [the financials](https://thewaltdisneycompany.com/app/uploads/2020/01/2019-Annual-Report.pdf "ar") and learn together how the business is run.

Disney reports four major segments, Media Networks, Parks, Studio Entertainment, and Direct-to-Consumer (DTC)

![post]({{ site.url }}{{ site.baseurl }}/assets/images/disney_activism/disney 1.png)

My first thoughts on the above are:

- Media Networks revenue is growing double digits, but operating income growth is only 2%, suggesting deleverage
- Parks on the other hand is growing rev 6%, but getting operating leverage to grow operating income 11%
- Studio grew rev but shrunk operating income, so that's unexpected
- DTC grew >100% on rev, and its operating loss also grew >100% \[3\]. Unusual to see a large company grow so fast, maybe they're doing great? Was Disney+ so successful?

If we take a look at the operating margins of those segments, they're pretty similar at 20-30%. That was surprising to me, I'd have thought there would be a high margin segment "subsidising" a low margin one. My first guess would have been that Parks are low margin.

If the margin profiles are indeed similar, management should be indifferent to investing in any of them; perhaps preferring Media due to the slightly higher margin \[4\].

![post]({{ site.url }}{{ site.baseurl }}/assets/images/disney_activism/disney 2.png)

Disney takes 17 pages in its annual report to describe its business \[5\], so I'll summarise them to avoid all of you quitting reading.

- Media includes domestic cable networks and TV stations such as Disney and ESPN \[6\]. Revenue comes from affiliate fees people pay them for their content (programming) and advertising on their own networks. 
- Parks includes their theme parks such as Disneyland and licensing of their IP for consumer products. Rev comes from park ticket sales and licensing royalties. There's an interesting mention of how >75% of Disney's capital spend has been on the Parks business, which is helpful to know
- Studio includes movies such as Fox, Marvel, Lucasfilm. Rev comes from the license fees of the movies to theaters
- DTC includes Disney+ streaming services, and they also put international TV here. Rev comes from advertising fees on international TV and subscription fees for streaming

Reading over this section also answers a few questions I had:

There was an acquisition in 2019, which resulted in "extra" rev for both the Media and DTC segments. This explains why DTC growth was so high, and also the acceleration in the Media rev.

If this was me back in banking I'd have spent hours trying to do pro-forma financials to adjust for this and get a "normalised" growth. 

I'm not in banking anymore and can't be bothered, so let's leave it as is. But that also implies the growth rate of Media is lower than I thought. I wouldn't be surprised if it was more similar to the 2018 growth rate of ~3%.

I'd also initially thought DTC was showing Disney+ success, but that's not the case. I also realised Disney+ launched in Nov, so it's probably insignificant for total rev.

Parks are also higher margin than I thought because they lump the IP licensing rev in that segment. I'm assuming that's to avoid showing a low margin segment but don't have context here.

So my revised thoughts are:

- Media (all the TV rev) is large but slow growing
- Parks is large but slow growing, and requires a lot of capital investment
- Studio is smaller but fast growing, due to the popularity of Marvel films I'd imagine
- DTC is smaller and I can't really tell the growth rate, but would assume it's fast as well since Disney+ is new

Now let's take a look at what the investors are saying. I'll present them in pairs and add commentary for my own thoughts

### Third Point's arguments and Semper Augustus' counterarguments



## Footnotes

1. I've linked to a third party site for the letter text, and you can also find it [here](https://thirdpointlimited.com/portfolio-updates "third") on Third Point's official site if interested. That link doesn't seem to be a permanent one for the letter, hence the third party link.
2. But not unheard of. Bill Ackman vs Carl Icahn on Herbalife is a famous example.
3. The 100% in the table stands for >100% growth, similar to the >(100)% standing for more than 100% decline
4. This is a simplistic take, since there could be other costs not accounted for in the operating income reported here. The tax treatment for the businesses or interest expense might be different, just to give examples.
5. It's the first section of its [annual report](https://thewaltdisneycompany.com/app/uploads/2020/01/2019-Annual-Report.pdf "ar"), if you're interested in taking a closer look
6. I think people know that ESPN is the big money maker for Disney from some other publicly disclosed numbers, but I'm not going to dig further unless needed.
7. Disney acquired TFCF, which also gave them a stake in Hulu. "On March 20, 2019, the Company acquired the outstanding capital stock of TFCF, a diversified global media and entertainment company." and "The acquisition purchase price totaled $69.5 billion, of which the Company paid $35.7 billion in cash and $33.8 billion in Disney shares." and "As part of the TFCF acquisition, the Company acquired TFCF’s 30% interest in Hulu increasing our ownership to 60%. As a result, the Company began consolidating Hulu" from pdf page 98 of the 2019 10K.

*If you liked this, sign up for my [finance and tech newsletter:](https://avoidboringpeople.substack.com/ "ABP")*

<div class="iframe-container-4x3">
  <p align="center"><iframe src="https://avoidboringpeople.substack.com/embed" frameborder="0" scrolling="no"> </iframe></p>
</div>
