+++ 
title = "How Kaggle makes GPUs accessible to 5 million data scientists" 
date = 2020-11-08T17:03:30-08:00 
draft = false 
tags = ["kaggle", "data science"] 
categories = ["product"] 
description = "Engineers and designers at Kaggle work hard behind the scenes to make it easy for our 5 million data scientist users to focus on learning and improving their deep learning models."
+++

_[This post was first published on NVIDIA's developer blog on Oct 26th 2020](https://news.developer.nvidia.com/how-kaggle-makes-gpus-accessible-to-5-million-data-scientists/)_

Engineers and designers at [Kaggle](https://www.kaggle.com/) work hard behind the scenes to make it easy for our 5 million data scientist users to focus on learning and improving their deep learning models instead of ML ops like environment setup and resource provisioning.

Kaggle’s community comes to the platform to learn and apply their skills in machine learning competitions. To do this, our users use Kaggle Notebooks, a hosted Jupyter-based IDE.

Our mission is to help the world learn from data, so we strive to make powerful resources available to our global community at no cost via Kaggle Notebooks. This includes NVIDIA P100 GPUs. Tens of thousands of users train deep learning models with GPUs on Kaggle every month, so ensuring the experience is a good one is key.

When making accelerators available to our users, we prioritize two things:

-   Maintaining a fast, no-setup experience so users can start writing code within seconds
    
-   Making efficient use of resources so we can extend them to as many users as possible

Achieving this has been no simple feat. In the rest of this post, I’ll describe a sampling of the engineering and design work our team has done to make this possible.

## A fast, no-setup user experience

Kaggle Notebooks come with popular data science packages like TensorFlow and PyTorch pre-installed in Docker containers ([see the Python image GitHub repo](https://github.com/kaggle/docker-python)) that run on Google Compute Engine VMs. Our engineers maintain these Docker images so that our users don’t need to worry about installation and dependency management, a huge barrier to getting started with data science.

We [release updates to our images](https://www.kaggle.com/product-feedback/161327) about every two weeks. This means users always have easy access to the latest package versions which is important in a fast evolving domain such as machine learning.

So that our users have a consistent, reliable experience using GPUs, we have also implemented a suite of tests that runs automatically every hour to catch any regressions in performance.

Reproducibility is also important to a fast, no setup user experience. By default, a notebook will always use the Docker image version that it was created with so that code that runs today will still run months later without any special effort. Users also have the option to refer to the latest available image in case they want to make sure they can access new libraries or library versions.

Given this setup, we have very, very large Docker images (~30GBs) for which we maintain many versions (over 150 so far at a total size of over 1.5TBs). This frequently risks degrading the user experience (e.g., pulling a full image can take around 10 minutes whereas we want our users to be able to begin writing code within seconds) so we’ve also made investments in reducing this pain point.

For example, we now track which libraries are actually used by our community and automatically remove little-used ones. We’ve made other optimizations that together allow a notebook session to start within a matter of seconds.

Finally, we recently made our Docker images compatible with the [Deep Learning VM images used by Cloud AI Notebooks](https://cloud.google.com/deep-learning-vm) so that users could easily [export their notebook and its dependencies to GCP](https://www.kaggle.com/product-feedback/159602). This allows our users to pay for even more powerful compute without running into breaking changes.

## Efficient use of resources

Providing access to GPUs at no cost to our users is an amazing thing, but our ability to do so isn’t unlimited. To make GPUs available to as many people as possible while maintaining a smooth user experience, our team has undertaken various wastage mitigation measures.

Recently, we [re-architected the backend service](https://medium.com/google-cloud/a-multi-cluster-grpc-architecture-on-gke-365bbd757df) that provisions sessions for thousands of concurrent notebooks. One of the important new features we implemented was autoscaling for our VM pools. This allowed us to automatically keep a warm pool of GPU VMs at a capacity that’s a percentage above actual demand as opposed to some fixed size. Ultimately, this helped to reduce our costs by 36% while ensuring our users almost never end up in queues waiting for a machine to become available.

We also continually strive to eliminate abuse. We love to see our community share notebooks like [“RAPIDS/UMAP with Fisher metric on RGB histograms”](https://www.kaggle.com/hubwag/rapids-umap-with-fisher-metric-on-rgb-histograms) on our [melanoma classification competition](https://www.kaggle.com/c/siim-isic-melanoma-classification/notebooks?sortBy=voteCount&group=everyone&pageSize=20&competitionId=20270). Not notebooks used for cryptocurrency mining. Our efforts here have allowed us to continue to extend these powerful resources to legitimate users.

![](https://lh5.googleusercontent.com/tFZpyALE0OhZjforc-AlrQXuiJNLyoKHwjBD8rH_IWnJ6k1fpNOdomR1BxO_8NqVKfOczjtr53MBBgxNvOVzBz1evWWEucqcqyTVpqJABB1uTFtHR8bfW0_d9jkago6h40Q0BPrQWQ)

_[3D UMAP embeddings](https://www.kaggle.com/hubwag/rapids-umap-with-fisher-metric-on-rgb-histograms) of melanoma RBG histograms created by [Hubert Wagner](https://www.kaggle.com/hubwag) using a GPU enabled Kaggle Notebook_

Finally, we’ve made changes in the notebook editor’s frontend to make it easier for our users to more effectively manage their limited accelerator quota (30h/week). For example, we recently made it [easier for users to power a session on and off](https://admin.kaggle.com/product-feedback/152669) within seconds; previously, the session start time could take 30 seconds to a few minutes. Additionally, it’s now possible to edit code interactively without an accelerator and [only use a GPU when saving a new version](https://admin.kaggle.com/product-feedback/161328) (executing the notebook top-to-bottom).

## Get started with GPUs on Kaggle

Kaggle is a great place to learn how to train deep learning models using GPUs. We have a number of [Courses](https://www.kaggle.com/learn/overview), series of lessons and interactive notebooks, including [Deep Learning](https://www.kaggle.com/learn/deep-learning).

You can apply what you learn in a machine learning [Competition](https://www.kaggle.com/competitions), for example our ongoing Getting Started NLP Competition to [predict which tweets are about real disasters or not](https://www.kaggle.com/c/nlp-getting-started).

Finally, you can browse any of the [over 30,000 public GPU notebooks](https://www.kaggle.com/search?q=tag%3Agpu+in%3Anotebooks) shared on Kaggle. Then, simply click the “Copy & Edit” button to begin editing and running code.

We hope it’s fast and easy to get started, but if you have feedback [please let us know](https://www.kaggle.com/product-feedback)!

_Thank you to Vincent Roseberry, Dustin Herbison, Philippe Modard, and Anna Montoya for their feedback on this post._

--

## Reply

Follow the conversation and discuss on Twitter.

{{< tweet user="MeganRisdal" id="1325607215911235584" >}}