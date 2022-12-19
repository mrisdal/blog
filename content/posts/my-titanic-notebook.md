+++ 
title = "Making public mistakes & code memes: The origin of my famous Titanic notebook" 
date = 2020-08-25T13:38:46-07:00 
draft = false 
tags = ["data science", "kaggle", "code", "learning"] 
categories = ["career"] 
description = "Yesterday, it was a great honor to be a guest on Nick Wan's data science livestream on Twitch to talk through bad (and less bad) data viz that I've created."
+++

Yesterday, it was a great honor to be a guest on [Nick Wan's](https://twitter.com/nickwan) data science livestream on Twitch to [talk through bad (and less bad) data viz that I've created](https://www.twitch.tv/videos/720567732?t=00h20m40s).

<!-- In case I can get this working later
<iframe
    src="https://player.twitch.tv/?video=v720567732&time=00h20m40s"
    height="300"
    width="400"
    frameborder="0"
    scrolling="no"
    allowfullscreen="false">
</iframe>
-->

It was a lot of fun! Talking about the history of my popular Titanic R notebook on Kaggle was a great opportunity for me to reflect on my data science journey. Its explosive success was very unintended. But as a result I've got a couple of cool insights to share about this experience and how I apply them in my role as a product manager at Kaggle today.

## The history

If you haven't come across my introductory ML tutorial on the Titanic Getting Started Competition, then I guess I can't count you among the over half million views it's received in the past 4+ years. ["Exploring Survival on the Titanic"](https://www.kaggle.com/mrisdal/exploring-survival-on-the-titanic) was my very first public notebook on Kaggle. According to the notebook's history, I created it in March 2016. And the story behind it is perhaps semi-interesting!

Flashback to late 2015, I had recently joined Kaggle as a user. After mastering out of my PhD in linguistics and getting my first job doing data science for market research, I was hoping to tap into and learn from the machine learning community. While I was waiting for Kaggle to launch a good tabular dataset competition to dip my toes into (still waiting ...), I was mostly playing around with their newly launched public datasets.

A few months later, Kaggle's newsletter landed in my inbox. They were hiring a part-time content marketing intern. Yes! This could be perfect for me. As the only data scientist at my job, I was eager to make connections and learn in this field. So an opportunity to create content, get feedback, and interview top data scientists was a dream. I applied and after doing an interview and submitting a writing sample, I was asked to do a short test project creating a tutorial notebook.

This short project ended up becoming the legendary Titanic notebook! In addition to receiving (at time of writing) 542,816 views, it's been upvoted 3,388 times, forked 6,135 times, and has almost 1,000 comments. I never imagined my work test would become one of the top pieces of content on the platform, even 4+ years later.

## Lessons learned

### Imperfections reborn as blessings

In my interview with Nick, we focused mostly on the bad data viz aspects of my notebook. I explained that the time constraints of the short job test forced me to focus on the aspects which I considered most important: 

1. Delivering an end-to-end tutorial
2. A technical yet fun narrative that showed off my writing skills

I definitely didn't focus on the quality of the data visualizations in the couple of hours I spent on this notebook. Instead, once I got one part working, I moved on to the next. In some places, I wanted to test what was possible in this new-to-me platform which leads to some unusual choices in retrospect which gave us plenty to talk about (what was I thinking with that mosaic plot?).

<img src="https://www.kaggleusercontent.com/kf/2020416/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..7O_SLGfRoS5-KMTnn7m1Gg.TzoJE1yl45bOs1NUIWjrLDScObr1oa4TzMVCkRCgjem3WZDCYGuH9UjCTDSlKF4h270qrX_23Gc9u8LtRtUmfj30gg1PYE4cefcnT8o3WMc_ioQOuOKa8gAXumqgNypgD_VgDW6Lkifbt89thT_C9lDAxzgA7Gdnmz_quoh3ikWeKR6nFL77UYWruoiMbGXdhKGzG2RxaNWEx0C1dNZbDChh0JDR_5LWpUteLSEvuSBpTn5twMGBU8iMddALf7r0KOa49iQk29u5s3BcTElRZfTSkda8yJLmQIg8strYj54kONVCReqZkzo4NsjrZi7Ravo9KAON86eB8MQ_Ic8NUpiJOZ5XxnpBRznRk-7dQ2ESv8T54VmYh4HftGdHIRd3C6jJUeKbJ74CVE6Rupu9RqFsbV_uBcFKVvaCRNV4G1dGWzg2eOu2UOedlfoL6-3yB4louD3LnYE8_MZDVyOdF2TW7DGNiM8n0qX15ZuVlVmBLKAyyg8AyC6zW8TxXG4iHvU2GaEFGMDk970T09xVZcidIGvEYk1Ey7TnBQowLnQqL8IgVnE8DVrN1tfjJfXQEz_ZbrtTXMPjJ0t6r4h4wKoVNO7bgwvoDMFEGU7lU0H2rgEFqkypI6PZ0hHTBHbvLNIo-GZcbhyUO6lz7fnntQ.LTbN0FfZK44JvhmQM0TTqA/__results___files/figure-html/unnamed-chunk-7-1.png"><figcaption>_I can make a mosaic plot! But why?_</figcaption>


In the end, I'm glad I focused on writing over data visualization or even quality of my code (because this is what I was evaluated on and I got the job, after all). Now that the notebook has seen such success with newcomers to machine learning, I think its flaws are actually a good thing in two ways. 

First, as you might be able to glean from the comments if you read them, it's very easy to find areas to improve upon my work. This makes this notebook a great launching pad. 

Second, if you can improve upon something that's as popular as my Titanic notebook, hopefully that gives you a (well deserved) confidence boost as a learner! These kinds of wins are really motivating early on and to the extent this notebook as enabled that feeling for many people, I'm really proud of it!

In all of this, I experienced how much you stand to learn from the community when you put yourself out there early and often even if it requires knowingly making mistakes in public. Today, as a product manager at Kaggle, this reinforces for me how important it is for Kaggle's community to be open to people from all over the world who are putting themselves out there to ask questions and learn.

### Code snippets as memes

Another observation that I shared in my interview with Nick was about how I'd see other people copy distinctive bits of my data visualization code in their notebooks. I'd notice my plots repurposed for different datasets in my Kaggle newsfeed or just browsing others' notebooks. Since I'm not particularly enamored with my own data viz work here, it was kind of embarrassing to see my mistakes proliferate!

<img src="https://www.kaggleusercontent.com/kf/2020416/eyJhbGciOiJkaXIiLCJlbmMiOiJBMTI4Q0JDLUhTMjU2In0..7O_SLGfRoS5-KMTnn7m1Gg.TzoJE1yl45bOs1NUIWjrLDScObr1oa4TzMVCkRCgjem3WZDCYGuH9UjCTDSlKF4h270qrX_23Gc9u8LtRtUmfj30gg1PYE4cefcnT8o3WMc_ioQOuOKa8gAXumqgNypgD_VgDW6Lkifbt89thT_C9lDAxzgA7Gdnmz_quoh3ikWeKR6nFL77UYWruoiMbGXdhKGzG2RxaNWEx0C1dNZbDChh0JDR_5LWpUteLSEvuSBpTn5twMGBU8iMddALf7r0KOa49iQk29u5s3BcTElRZfTSkda8yJLmQIg8strYj54kONVCReqZkzo4NsjrZi7Ravo9KAON86eB8MQ_Ic8NUpiJOZ5XxnpBRznRk-7dQ2ESv8T54VmYh4HftGdHIRd3C6jJUeKbJ74CVE6Rupu9RqFsbV_uBcFKVvaCRNV4G1dGWzg2eOu2UOedlfoL6-3yB4louD3LnYE8_MZDVyOdF2TW7DGNiM8n0qX15ZuVlVmBLKAyyg8AyC6zW8TxXG4iHvU2GaEFGMDk970T09xVZcidIGvEYk1Ey7TnBQowLnQqL8IgVnE8DVrN1tfjJfXQEz_ZbrtTXMPjJ0t6r4h4wKoVNO7bgwvoDMFEGU7lU0H2rgEFqkypI6PZ0hHTBHbvLNIo-GZcbhyUO6lz7fnntQ.LTbN0FfZK44JvhmQM0TTqA/__results___files/figure-html/unnamed-chunk-11-1.png"><figcaption>_A strobe light in boxplot form, complete with hardcoded values._</figcaption>

Code snippets are kind of like chunks of genetic material. Probably stuff that tends to work pretty well will replicate successfully in an ecosystem. And my notebook had a lot of signals of being a "good idea" in general: lots of views and upvotes, lots of forks, lots of comments, and highish score on the competition.

In general, I'd argue that publicly sharing and reusing reproducible code under an open license has been a good thing for developer productivity. But there are plenty of traps, too, as I witnessed my own flawed code go viral like it was some meme. This is something that I think a lot about now in my capacity as a product manager for Kaggle Notebooks (and as someone who previously worked at Stack Overflow). Questions like:

1. What signals do you use to know some code you're looking at is high quality and trustworthy?
2. How can we make it easier to find and effectively reuse useful, high quality code snippets? 
3. How do you safely and easily update code snippets (mine are over four years old and probably still circulating)

Especially if you have thoughts about how to measure quality, I'm interested in chatting more!

## Conclusion

Thanks to my willingness to publish what you could call "bad data viz" today, I've come a really long ways in my career. It's been an awesome journey from doing a small work test in a notebook to now managing that very notebook product in a few years. In a fun twist of fate, I suppose now I'm even responsible for how slowly this page loads due to its popularity!

If you want to hear more about my journey and my perspectives on data visualization (including an example of a "good" data viz), check out [my interview on Nick Wan's Twitch](https://www.twitch.tv/videos/720567732?t=00h20m40s).

--

## Reply

Follow the conversation and discuss on Twitter.

{{< tweet user="MeganRisdal" id="1298398384529633280" >}}