---
layout: post
title: My Notes on Uncertainty - Thinking Like an Experimental Physicist
excerpt: "One of the most thought-provoking sessions of the ICTS-SSWP 2026 program was the talk on ... "
mathjax: true
tags:
  - Physics
  - SSWP-2026
---
One of the most thought-provoking sessions of the [ICTS-SSWP 2026](https://www.icts.res.in/program/SWWP2026)[^1] program was the talk on **Uncertainties** delivered by **[Prof. Shirish Pathare](https://www.hbcse.tifr.res.in/people/scientific/shirish-r-pathare)** from [HBCSE](https://www.hbcse.tifr.res.in/). Rather than focusing on formulas and calculations alone, the session encouraged us to rethink what it really means to perform an experiment.

Usually when we do experiments at school/college labs, we tend to follow a standard pattern: 
- begin with an aim
- gather the prescribed apparatus
- follow a given procedure
- record observations
- analyze the data, and 
- finally arrive at conclusions 

While this approach helps us learn experimental techniques, it often overlooks an important aspect of scientific inquiry - *procedural understanding*, which focuses on:
- How do we decide what measurements to make?
- Why do we choose a particular method?
- How do limitations of our instruments affect the conclusions we draw?

These were some of the questions that formed the foundation of the discussion.

The session began with an intriguing problem involving the verification of the inverse-square law. Suppose we have a photodiode to measure light intensity and a ruler to measure distance. We collect data for intensity as a function of distance and then plot two graphs: 
(1) $I$ vs $\frac{1}{d^2}$ and 
(2) $\frac{1}{\sqrt{I}}$ vs $d$

According to the inverse-square law, both plots should be straight lines. However, we observe that:
	*The graph of $\frac{1}{\sqrt{I}}$ vs $d$ is a straight line as expected, however, the graph of $I$ vs $\frac{1}{d^2}$ is not a straight line.

At first glance, this appears contradictory. The question was left open for us to think, and the answer was in the talk itself - **errors in measurement**.

The answer is
	Every measuring instrument has a least count. For example, a lab ruler has a least count of 1 mm. We measured the distance $d$ with an instrument that has a least count 1mm. Suppose the error in measurement is $\Delta d$, then the distance we got is $d + \Delta d$. When we plot the $\frac{1}{\sqrt{I}}$ vs $d$ curve, it  primarily affects the intercept and spread of the data points. However, when the same uncertainty appears in the denominator and is squared, as in, $\frac{1}{d^2}$, we get a curve instead of a straight line. This can be shown mathematically. 

This simple example highlighted an important lesson: understanding **uncertainties** is often just as important as understanding the underlying principles.

The session became even more engaging when we were challenged to design experiments on our own using a syringe filled with water and a measuring tape. The first task was to determine the value of $g$, the acceleration due to gravity, and the second was to estimate the radius of a water drop from the syringe.

These problems made us to think like experimental physicists. There was no predefined procedure, no list of steps to follow, and no "correct" method provided. Instead, we had to decide what quantities could be measured, what assumptions were reasonable, and whether the experiment was practically feasible.

While we came up with several possible solutions to the experimental challenges, one of the most valuable lessons was the importance of evaluating feasibility. For example, a natural approach to measuring $g$ might be to drop a water droplet, start a stopwatch, and record the time taken to reach the ground. However, this method introduces significant errors in the form of manual reaction-time. The instant the drop begins to fall is not the same instant at which we can start or stop the stopwatch.

This led to a deeper insight: designing an experiment is not simply about finding a method that works in principle. It is about finding a method that produces reliable measurements while minimising uncertainties. Sometimes, the best strategy is to work backwards from the quantity we wish to determine and use our understanding of the underlying physics to develop a more robust experimental design.

Another theme of the talk was the importance of **linearisation**. In experimental physics, we often prefer to transform equations into forms that produce straight line graphs. Straight lines are easier to interpret, easier to fit, and make deviations caused by experimental uncertainties more apparent. Since real data always contains some degree of error, we rely on best-fit lines to extract meaningful information rather than expecting every point to lie perfectly on a theoretical curve.

Towards the end of the session, we watched clips from the film _Hidden Figures_, which illustrated the practical importance of linearisation, error analysis, and accurate data reporting. We also saw visualisations related to spacecraft re-entry trajectories and the critical "go/no-go" decision point for retroburns, providing a fascinating real world application of the concepts we had been discussing.

The session was a good reminder that experimentation is much more than following instructions. It is a creative process that requires careful thought, critical reasoning, and an appreciation of the uncertainties that come with every measurement. In many ways, learning how to design an experiment is just as important as obtaining the final result.

---
<br>

[^1]: ICTS SSWP-2026: The ICTS Summer School for Women in Physics (SSWP) 2026 is a 10-day residential program designed to encourage undergraduate women to pursue careers in physics through hands-on experiments, conceptual discussions, and lectures. For more details, visit [ICTS](https://www.icts.res.in/program/SWWP2026).
