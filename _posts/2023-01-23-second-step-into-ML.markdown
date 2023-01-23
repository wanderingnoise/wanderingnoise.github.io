---
layout: post
title:  "Second step into ML"
date:   2023-01-23
description: How to stick with parameters
---

<p class="intro"><span class="dropcap">E</span>ven if I thought I was able to stick with my plan, as usual I had to stop a bit my learning.</p>

This resulted in a next step with a week of delay. GG.

The next step of my descent into AI/ML madness is strictly adherent with the "step" concept.

In fact, it's related to step-by-step find the best "compute loss" value.

To do so, we need to iterate the model guessing the values iteratively, starting from a value (e.g., w1 = 0) and then trying another one (e.g., w1 = 0.5) and so on until you find the best possible model. 

N.B.: in ML, one of the problems is to find the best possible model as efficiently as possible. 

Trying to plot every single value we can chose, the result is a **convex** function (i.e., a kind of "U" plotted).
We can't iterate every single value because is (of course) inefficient.

Thus, there's an algorithm that iterates the next point using the **gradients**: a gradient of a function is the vector of partial derivates.

There you need to select two parameters:
* the gradient magnitude
* the learning rate (also called "step size")

If the learning rate is too small, learning will take too long.
If the learning rate is too large, learning could potentially never be completed.

There are some tricks (e.g., **Goldilocks learning rate**) to expand the learning rate to a smaller or larger rate dinamically.

In gradient descent, a batch is the total number of examples you use to calculate the gradient in a single iteration. A very large batch may cause even a single iteration to take a very long time to compute.

**Stochastic gradient descent (SGD)** takes this idea to the extreme--it uses only a single example (a batch size of 1) per iteration. Given enough iterations, SGD works but is very noisy. The term "stochastic" indicates that the one example comprising each batch is chosen at random.

**Mini-batch stochastic gradient descent (mini-batch SGD)** is a compromise between full-batch iteration and SGD. A mini-batch is typically between 10 and 1,000 examples, chosen at random. Mini-batch SGD reduces the amount of noise in SGD but is still more efficient than full-batch.
