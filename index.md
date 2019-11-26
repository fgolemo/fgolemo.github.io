---
layout: page
title: Research Projects
---

## 1) Sim2Real Transfer

<!--
![Two Poppy Ergo Jr robots swordfighting]({{ "/images/ergo-swordfight.gif"}})
-->

Whenever you want to teach a robot a new skill, it's easier to start in simulation and then transfer what you've learned 
to the real robot. This rarely works perfectly though, which motivates my research into how to make that transition smoother.
We're specifically investigating low-cost "shoddy" robots since sim2real problems are exaggerated here. Here are some 
current and past projects:

**Active Domain Randomization**

<iframe src="https://giphy.com/embed/XBvMaXxKKnsGiRCqbj" width="200" frameBorder="0" class="giphy-embed"></iframe>
Domain Randomization is a recent and very powerful method for sim2real transfer. The idea is to uniformly randomize all the 
things that can be different between simulator and real robot, like frictions, masses, joint torques, etc. However, we found 
that it's also very inefficient and sensitive to randomization parameter ranges. With [Active Domain Randomization, ADR](https://arxiv.org/pdf/1904.04762.pdf), 
(not to be mistaken with the later work ["Automatic Domain Randomization" from OpenAI](https://arxiv.org/abs/1910.07113) that cites ours) we introduced 
a way to create an automatic randomization curriculum that explores the randomization parameters as the policy gets better.

**Neural-Augmented Simulator++**

<iframe src="https://giphy.com/embed/L2fJJ1dZOFfLiHQco5" width="200" frameBorder="0" class="giphy-embed"></iframe>
The idea behind the [Neural-Augmented Simulator](http://proceedings.mlr.press/v87/golemo18a.html) was to learn a model of the discrepancies between simulation and real robot.
This learnt discrepancy model can be used to "correct" a simulator's internal state; and a policy that is trained in this
augmented simulator transfers better to the real world. In our ongoing work, we're investigating how the data
that is collected for the discrepancy model affects its performance down the line in policies that cover different portions
of state space. We're also exploring metrics for how well a policy is expected to transfer before the sim2real transfer 
takes place.

**Physics Distillation**

![Isaac in a petri dish]({{ "/images/isaac-smol.jpg"}})
In this ongoing work, we're investigating how we can learn a model of the transition dynamics of the simulated environments
and use those for visually planning on the real robot. 

## 2) 3D Perception

**Pix2Surfel**

<iframe src="https://giphy.com/embed/IbrOx3Ud9D0SFXH7Ib" width="200" frameBorder="0" class="giphy-embed"></iframe>
3D understanding of scenes is necessary for many kinds of robots acting in the real world. Getting this 3D data from RGB-D sensors is very noisy and usually limited to a minimum distance from the camera. In the ongoing project, we are investigating techniques to infer depth in an unsupervised way from single 2D images, by using [shading cues, learned geometry](https://openreview.net/forum?id=BJeem3C9F7), or rotation-invariance.  

**SEVN**

<iframe src="https://giphy.com/embed/lSn6QaUqJ0LD1aJUhN" width="200" frameBorder="0" class="giphy-embed"></iframe>
The goal of the SEVN project is to provide a navigation assistant for the blind or visually impaired. In order to start training agents, we tried finding a suitable simulator for sidewalk navigation. We found that existing datasets were unsuitable since they were captured from a street perspective or house numbers were unreadable. This resulted in us [gathering and annotating our own data](https://mweiss17.github.io/SEVN/). To speed up development, we provided our own simulator. 

**DiffSim**

Humans can look at a scene and immediately understand what kind of objects are present and estimate their physical properties. In this ongoing project, we're trying to imbue a machine learning system with the same knowledge and ultimately have it look at videos, identify the objects and reason over their properties.
