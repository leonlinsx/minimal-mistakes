---
title:  "Would you buy the Libra Neopet Kin token?"  
tags: []
published: false
---

*This is a lightly edited version of* ***[my monthly newsletter.](https://avoidboringpeople.substack.com/ "ABP")*** *Sign up here:*

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

**Takeaways**


**Decision making**

Decision making becomes more difficult as your organisation grows. You want to involve everyone and make them feel included, but that could spiral into multiple meetings where people give input but nothing gets done. [This summary of decision making principles by Devon Zuegel](https://devonzuegel.com/post/no-kings-how-do-you-make-good-decisions-efficiently-in-a-flat-organization "Devon") \[30\] has advice I haven't seen before:

> We reject: kings, presidents and voting.

> We believe in: rough consensus and running code.

The part about rejecting individual decision makers and voting is straightforward. Running code can be thought of as getting things done; preferring action over theory. More interestingly, what does rough consensus mean?

> If \[...\] the working group has made an informed decision that the objection has been answered or is not enough of a technical problem to prevent moving forward, \[...\] there is rough consensus to go forward, the objection notwithstanding

The key insight here is that objections that are "not enough of a problem" can be overruled. This implies that you will go ahead with decisions that some people in the group dislike, as long as the issue isn't critical to success or failure. **You don't need everyone to agree.**

> Rough consensus relies on the distinction between two types of objections:

> 1) "Not the best choice" feedback: "I don’t believe Solution A is the best choice, because XYZ. I believe Solution B would be better, but I accept that Solution A can work too."

> 2) Fundamental flaws: "I believe Solution A is unacceptable because XYZ."

During a discussion, clarify which type of objection you're getting, since people communicate with various degrees of subtlety \[31\]. My "worth taking a look at" is usually a "pretty sure this is key so I hope we have a plan". Once clarified, spend the majority of your time on fundamental flaws rather than "not the best choice" feedback.

How you define a fundamental flaw depends on your team, and should be decided beforehand. Devon cites substantial technical debt, inability to scale, or too much work as some suitable reasons. You probably can't have too many reasons, as that would lead to nothing getting done. Once you've settled on your reasons, there should be a high bar to accepting new ones during the discussion itself.

I'd also assume that most people talk during meetings for the sake of talking \[32\]. This implies that most objections should fall under the "not the best choice" category, and you should feel alright moving forward despite them.

![post]({{ site.url }}{{ site.baseurl }}/assets/images/Two types of objections.jpg)

> A chair who asks, "Is everyone OK with choice A?" is going to get objections. But a chair who asks, "Can anyone not live with choice A?" is more likely to only hear from folks who think that choice A is impossible to engineer given some constraints

I like the reframing of the question, and intend to use it more often in meetings. 

There are further clarifications on useful and not useful consensus:

> An engineering solution that has no objections, but also has no base of support and is met with complete apathy, is not a solution that has any useful sort of consensus

> conceding when there is a real outstanding technical objection is not coming to consensus

> Even worse is the "horse-trading" sort of compromise: "\[...\] Neither of us agree. If you stop objecting to my proposal, I'll stop objecting to your proposal and we'll put them both in."

All these are related to people giving up on caring about the issue. This is problematic, and unfortunately I'm unsure what the best way is to revive the interest of the group. Perhaps taking a break and coming back another week?

> One hundred people for and five people against might not be rough consensus

> Five people for and one hundred people against might still be rough consensus

[The original document](https://tools.ietf.org/html/rfc7282 "IETF") gives more detailed examples \[33\], with the main takeaway coming back to what determing whether the objection is a fundamental flaw or not. The number of people for or against does not matter. 

> We may use the "hell yeah" principle for hiring and some other decisions, but we use the quick iteration principle when we ship things. We don’t aim for perfection the first time — we build fast, we ship, we learn, we iterate, and we ship again

I agree. As can be inferred from my writing, I'm biased towards experimenting. You don't know what you don't know, and you can't find out until you try. There's too many slide decks and too much theorising compared to people actually executing, since the former is easier to do and still feels productive, whereas the latter is harder and uncomfortable. Unless the flaw is going to ruin your business - and few do - err on the side of getting things done.

I like the idea of rough consensus because I ~~care about very little~~ prefer efficient meetings. Since most organisations incentivise people to speak up, you usually end up with more opinions and objections than needed. While adopting a rough consensus approach may seem against the principle of inclusivity, I'd think it leads to more effective decision making. 

**Shoutouts**

1. Thomas Guthrie at [onejob](https://onejob.substack.com/ "onejob") is helping people find their next roles at top startups.
2. 

**Other**

1. [Could a text prediction algorithm (like gmail or your phone keyboard) be used to play chess?](https://slatestarcodex.com/2020/01/06/a-very-unlikely-chess-game/ "Slate")
2. [Self-disclosing weakness at work could help or hinder, depending on your status](https://faculty.wharton.upenn.edu/wp-content/uploads/2019/10/when_sharing_hurts.pdf "Wharton"). See [here](https://twitter.com/Leonlinsx/status/1221891694964113409?s=20 "twitter") for a tweet summary
3. [Examples of games made by China tech companies for Chinese new year](https://a16z.com/2020/01/24/tech-and-chinese-new-year/ "a16z")
4. [How some restaurants PR their way to success and best-of lists](https://ny.eater.com/2020/1/13/21009796/restaurant-publicists-pr-agencies-nyc "Eater") 
5. [How to design complex and aesthetically pleasing mazes](http://www.cgl.uwaterloo.ca/csk/projects/mazes/ "Mazes")

**Footnotes**

30. Forwarded by [Eitan on twitter](https://twitter.com/cool_idea "Eitan"). The original IETF document can be found [here](https://tools.ietf.org/html/rfc7282 "IETF")
31. This also applies to feedback generally, as I summarise [here](https://www.leonlinsx.com/thanks-for-the-feedback/ "Feedback") about how to get better at taking feedback
32. To be clear, I'm agreeing that you should speak up at work as much as possible; I just dislike the fact it's necessary
33. "So, in a large working group with over 100 active participants and broad agreement to go forward with a particular protocol, if a few participants say, "This protocol is going to cause congestion on the network, and it has no mechanism to back off when congestion occurs; we object to going forward without such a mechanism in place", and the objection is met with silence on the mailing list, there is no consensus.  Even if the working group chair makes a working group "last call" on the document, and 100 people actively reply and say, "This document is ready to go forward", if the open issue hasn't been addressed, there's still no consensus, not even rough consensus. It's the existence of the unaddressed open issue, not the number of people, which is determinative in judging consensus.""

*If you liked this, you'll like* ***[my monthly newsletter.](https://avoidboringpeople.substack.com/ "ABP")*** *Sign up here:*

<div class="iframe-container-4x3">
  <p align="center"><iframe src="https://avoidboringpeople.substack.com/embed" frameborder="0" scrolling="no"> </iframe></p>
</div>
