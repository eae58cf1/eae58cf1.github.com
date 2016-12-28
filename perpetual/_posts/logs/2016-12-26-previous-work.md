---
layout: post
categories: perpetual logs
title: Previous work on Solar UAVs
excerpt: |
  This is something I probably should've done from the get-go. Here, I review previous work done on Solar UAVs and how they can help me get this up in the air quicker.
---
Would've made more sense to do this at the very beginning, but here goes. It's good that we still haven't started building anything so this is still a good stage to take a look at previous attempts made in the Solar UAV space, and to see what we can learn from them.

## "So Long" - 48 hour flight in 2005
The previous record held by a small UAV was the [48 hour flight](http://machinedesign.com/news/solar-powered-uav-flies-two-days-straight) by AC propulsion's So Long vehicle, designed by Alan Cocconi. The flight took place in 2005, but one thing that's noteworthy is that they had to ride thermals during the day (with the motor off) in order to stay aloft. That's like cheating, because you're not always guaranteed access to thermals &mdash; oh well.

### What I learned from it
- The use of a load cell to measure the thrust vs. power on the motor/propeller combination was very interesting. This lead me to do some research, after which I discovered [this great video](https://youtu.be/PfVJmci9IQQ) and [this accompanying repo](https://github.com/iforce2d/thrustTester) which explains how to do this in mind-numbing detail.
- The use of thermals is an interesting side-note. I'll look into the possibility of detecting and automatically exploiting these thermals in order to increase flight time.

## Solar UAV project at UMN, 2015 &mdash; 2019
This is a very similar to the project I'm currently working on &mdash; a team at the University of Minnesota led by Prof. Nikolaos Papanikolopoulos recently received a [$1.5M research grant by the NSF](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1531330&HistoricalAwards=false) to develop this over the next 3 years.
- There are 3 papers published to date as part of this research:
  1. [Solar powered unmanned aerial vehicle for continuous flight: Conceptual overview and optimization](http://ieeexplore.ieee.org/document/6630659/) &mdash; published in 2013
  2. [Solar powered UAV: Design and experiments](http://ieeexplore.ieee.org/document/7353711/) &mdash; published Oct 2015
  3. [Two Meter Solar UAV: Design Approach and Performance Prediction for Autonomous Sensing Applications](http://ieeexplore.ieee.org/document/7759272/) &mdash; publised Oct 2016
- I noticed alot of overlap between what I've already done and some of the work published in these research papers. In research #2, they actually ran an experiment with a working prototype of their design &mdash; and were able to capture enough solar power to account for "over 300% of a conservative estimate of the power required for level flight". The prototype they are using has a 4m wing span, and is super-light, using the same Sunpower C60 cells that I'm using.
- They even have a *very similar* flow chart to [the one I had made in the masterplan](/perpetual/masterplan/) showing how the various calculations influence each other: ![Flow chart from #1 - Solar powered unmanned aerial vehicle for continuous flight research](/assets/projects/perpetual/previous-work-umn-chart.png) .. Insane huh?

### What I learned from it
- They've done a lot of solid work on the theoretical side of things. The paper is very easy to read (not normal for research papers, btw), and follows a logical approach when determining the different design characteristics of the plane. I was planning on using a brute force approach to things, whereby I write a script to run through a range of characteristics and calculate the expected flight times as a result. Their approach is more scientific, methodical and it makes perfect sense. For example, they do an excellent job of tying the aerodynamic characteristics of the plane with the power consumption and generation aspects of the battery &amp; solar systems respectively. The results are great: 

![Solar weight vs. Battery weight vs. Hours of spare charge](/assets/projects/perpetual/previous-work-umn-solar-vs-flight.png)
- The 2m-ish wing span that I was aiming for isn't going to cut it. Paper #3 above (Two Meter Solar UAV) talks about what *can* be accomplished in a sub-2m wing span aircraft: "Maximum flight time for the two meter airframe considered is estimated to be greater than ten hours", which is conservative considering that the theoretical limit is closer to 40 hours. I may consider using the optimized results shared below in building the initial version on the plane (I do not want to build a 4m monster of a plane): ![Optimized results for 2m winged Solar UAV - Source: 3. Two Meter Solar UAV: &copy; IEEE](/assets/projects/perpetual/previous-work-2m-results.png)
- I'm going to be doing a deep-dive into the mathematics involved in these papers. Will update this link once that's done.
