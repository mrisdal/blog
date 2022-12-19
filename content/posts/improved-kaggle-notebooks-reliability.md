+++ 
title = "How our team improved perceived reliability of Kaggle Notebooks" 
date = 2020-08-13T15:18:44-07:00 
draft = false 
tags = ["product management", "data", "kaggle"] 
categories = ["product"] 
description = "I’ve worked at Kaggle on-and-off since 2016. In this time, THE most consistent source of user feedback is about the reliability of Kaggle Notebooks."
+++

I’ve worked at Kaggle on-and-off since 2016. In this time, THE most consistent source of user feedback is about the reliability of [Kaggle Notebooks](https://www.kaggle.com/notebooks). Sessions were slow to start and, far worse, sometimes users would lose hours of work. While progress had been made over the years, we’d never systematically addressed the problems.

Over the past half year or so since I’ve rejoined Kaggle, the Notebooks team renewed its focus on reliability. In this post, I'm proud to share how our team used a systematic approach to significantly improve reliability, both in terms of quantitative metrics as well as user perceptions.

  

## Background

Kaggle Notebooks is a no-cost managed [Jupyter-based](https://jupyter.org/) notebook product. Our users use Python and R notebooks to analyze datasets, train models, and submit predictions to machine learning competitions. Today we manage many thousands of VMs handling thousands of concurrent sessions for users all around the globe.

When I joined in 2020, we felt confident that reliability was the number one thing we could work on to improve our users’ experience using Kaggle Notebooks. We knew this from:

-   A [happiness and tracking survey](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/43221.pdf) we send to a sample of users each month
    
-   The volume of bug reports on our [site feedback forums](https://www.kaggle.com/product-feedback)
    

Improving user experience is a critical priority for Kaggle for a few reasons:

1.  Notebook usage is required for some competitions and we don’t want the user experience to be such a pain that it turns users off participating completely.
    
2.  Many brand new data science learners use Notebooks and if you’re new to something, sometimes it’s hard to tell if bugs and instability are your fault or not.
    
3.  We want users to use Kaggle Notebooks enough to create cool, helpful analyses that they want to share with the community.
    

  

## Our approach

In our approach to the problem, we considered reliability as having two facets: actual and perceived. In the first half of 2020, we prioritized a number of focused improvements to address both facets:

-   We maintained a dedicated working group to address a backlog of issues and monitor and respond to user feedback.
    
-   We implemented a new scalable, highly available backend architecture ([read about it from Mod](https://medium.com/google-cloud/a-multi-cluster-grpc-architecture-on-gke-365bbd757df), the technical lead on the project) with multiregion support.
    
-   We shipped features to improve perceived reliability like “sessionless editing”, a [brand new save workflow](https://www.kaggle.com/product-feedback/139884), and better session start/stop controls in the UI.
    

We feel the biggest game-changer was the [sessionless editing](https://www.kaggle.com/product-feedback/152669) feature that we delivered in June. Previously, rendering the notebook required a running jupyter server. But, starting the session took over a minute at the 95th percentile and about half a minute at the 50th percentile. This was a huge point of frustration for our users that we hypothesized contributed substantially to perceptions of poor reliability. With sessionless editing, we can now render and initialize the notebook editor within seconds.

The gif below illustrates a side-by-side comparison of the experience before and after launching our sessionless editing feature.



<img src="https://lh6.googleusercontent.com/M4JW0ArB84eEPsvv5QPvSfj5mgmiyGShz2Z7G864Xtew7KWHGc-U9-FPlLdPwHDGOsVknZie7SOfDhdJcjbHr79XeaeLgXeRKoz1GmusJ-0XHSDW8vv9MlvCt7gfulhi4sMmJjASOA">
<figcaption>_Less waiting, more coding._</figcaption>

Next, measuring impact was critical. To match actual and perceived reliability, we took a multi-modal approach to quantifying the results of our efforts.

To measure actual reliability, our reliability working group created a dashboard to monitor and set goals against some key metrics like availability and time-to-edit latency.

In part to measure perceived reliability on an ongoing basis, we also started a quarterly one-question survey. It asks recent notebooks users to “Please select any of the issues below that you have experienced on Kaggle Notebooks in the past couple of months”. Users could then select multiple options like “Notebook session was unreliable” and “Insufficient features available”. We fielded the survey twice: once at the end of Q1 and again at the end of Q2.

  

## Results

I’ll focus on the qualitative results in response to the one-question reliability survey. Our quantitative data showed progress, but would require a longer blog post to walk through.

First, you can see the overall results below.



<img src="https://lh5.googleusercontent.com/ZFxsZkuPKlMNm64NdbU8Wf07xhdO3TLfSsKdatZqk_zkjxwo48W6-FKLHLKu3h_amLMHC0Y9AeWnzQn1P4vEaSxcNF_kHPgER34N6e-8o4h1yyKeSn1mLCS3PEnuSry7HZcD4eG0yw">
<figcaption>_Overall issues that survey respondents said they experience using Kaggle Notebooks._</figcaption>

Most users in both quarters reported having no recent issues which is great. But, reliability (i.e., “Notebook session was unreliable”) was the second most common response in both quarters. Reliability concerns definitely still persist among respondents.

When we focus on percentage change between Q1 and Q2, however, it becomes clear that we did successfully make progress in the right direction.



<img src="https://lh3.googleusercontent.com/FSuAei-kyBuW76fb9v0V8va91RgmFGfIB98cFD_St4iWTPfx1GC7qBQfzFh0G26i2OKKBm5L9shfD3Wlagjgn2jO8TbTrQSOJYdHovEAxvG1BqYLRmI_EJsEMHujFHdhy4ahtyPGyA">
<figcaption>_Percentage change from quarter-to-quarter for each issue._</figcaption>

Because most of these items are issues (i.e., pain points), an increase from Q1 to Q2 is generally bad (red) whereas a decrease is generally good (blue). Only some of the changes are actually significant (the solid-filled bars).

We saw statistically significant decreases in users mentioning:

-   📉 33%: Can't depend on notebooks to do serious work
    
-   📉 19%: Session was unreliable
    
-   📉 18%: Session was slow
    

Even though reliability still remains a top concern for our users, we were really pleased with these results. Plus, this is the first time we’ve quantified user perceptions to tell us that we’re making progress.

  

## Takeaways

The biggest takeaway is that we’re not done yet, but we’re trending in the right direction. We remind ourselves regularly that this is a journey and what matters is being on the right track. Based on our results so far, we intend to maintain our dedicated reliability working group, set new goals, and continue to listen to user feedback.

_Massive thanks to everyone on the team who contributed to this effort: [Aurelio](https://www.kaggle.com/aagundez), [Jim](https://www.kaggle.com/jplotts), [Dustin](https://www.kaggle.com/herbison), [Cole](https://www.kaggle.com/noderaider), [Philippe (Mod)](https://www.kaggle.com/gphilmod), [Michael](https://www.kaggle.com/mbooth), [Vincent](https://www.kaggle.com/rosebv), [Erdal](https://www.kaggle.com/erdalsivri), [Einav](https://www.kaggle.com/einavcb), [Chelsea](https://www.kaggle.com/craerek). It’s an honor and a thrill to be part of such a great team.  Special thanks to Jim who co-authored the original internal report that this blog post is based on and to [Jessica](https://www.kaggle.com/jessicali9530) for fielding the survey. Last but far from least, thank you to our users for your invaluable feedback and your patience!_

--

## Reply

Follow the conversation and discuss on Twitter.

{{< tweet user="MeganRisdal" id="1294039078933901312" >}}