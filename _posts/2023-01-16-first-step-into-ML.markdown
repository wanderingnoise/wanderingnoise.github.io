---
layout: post
title:  "First step into ML"
date:   2023-01-16
description: My descent into (AI/ML) madness just started
---

<p class="intro"><span class="dropcap">A</span>s promised (to myself) I started to investigate the universe of AI starting from scratch.</p>

As per, Barr & Feigenbaum:

<blockquote>“Artificial Intelligence (AI) is the part of computer science concerned with designing intelligent computer systems, that is, systems that exhibit characteristics we associate with intelligence in human behavior – understanding language, learning, reasoning, solving problems, and so on.”  - (Barr & Feigenbaum, 1981)</blockquote>

There are at least 6 main categories for AI:
1. Machine Learning
2. Neural Network
3. Robotics
4. Expert Systems
5. Fuzzy Logic
6. Natural Language Processing

I started focusing on the first one, Machine Learning, that is split in 3 branches:
1. Supervised Learning
2. Unsupervised Learning
3. Reinforcement Learning

Since my goal is to expand my knowledge from scratch and step-by-step, I started with 1. Supervised Learning.

I found a useful starting point: <a hfref="https://developers.google.com/machine-learning/crash-course">https://developers.google.com/machine-learning/crash-course</a>.

As (not?) expected, ML has lot of math behind.

# Machine Learning key concepts

* Labels: a label is the thing we're predicting, the *y* variable in simple linear regression (e.g., price of wheat, the kind of animal shown in a picture, the meaning of an audio clip).
* Features: a feature is an input variable, the *x* variable in simple linear regression (e.g., words in an email text, sender's address, time of the day the email was sent). A simple machine learning project might use a single feature, while a more sophisticated machine learning project could use millions of features (x1, x2, ..., xN).
* An example is a particular instance of data, **x**. we can have:
    1. **labeled** examples: {features, label}: (x, y) -- use labeled examples to train the model. In our spam detector example, the labeled examples would be individual emails that users have explicitly marked as "spam" or "not spam."
    2. **unlabeled** examples: {features, ?}: (x, ?) -- used to predict y

Once we've trained our model with labeled examples, we use that model to predict the label on unlabeled examples. In the spam detector, unlabeled examples are new emails that humans haven't yet labeled.

* A model defines the relationship between features and label. For example, a spam detection model might associate certain features strongly with "spam". 
* Let's highlight two phases of a model's life:
    * Training means creating or learning the model. That is, you show the model labeled examples and enable the model to gradually learn the relationships between features and label.
    * Inference means applying the trained model to unlabeled examples. That is, you use the trained model to make useful predictions (y'). For example, during inference, you can predict medianHouseValue for new unlabeled examples.

* A **regression model** predicts continuous values. For example, regression models make predictions that answer questions like the following:
    - What is the value of a house in California?
    - What is the probability that a user will click on this ad?

* A **classification model** predicts discrete values. For example, classification models make predictions that answer questions like the following:
    - Is a given email message spam or not spam?
    - Is this an image of a dog, a cat, or a hamster?

To learn a model to predict a relationship, first you need to examine your data by plotting it.
Is this relationship between x and y linear? Could you draw a single straight line to approximate this relationship?

If yes, using the equation for a line, you could write down this relationship as follows:

  y = mx + b

By convention in machine learning, you'll write the equation for a model slightly differently:

y' = w1x1 + b

where:

* y' is the predicted label (a desired output).
* b is the bias (the y-intercept), sometimes referred to as.
* w1 is the weight of feature 1. Weight is the same concept as the "slope" in the traditional equation of a line.
* x1 is a feature (a known input).

Although this model uses only one feature, a more sophisticated model might rely on multiple features, each having a separate weight. For example, a model that relies on three features might look as follows:

y' = b + w1x1 + w2x2 + w3x3

Training a model simply means learning (determining) good values for all the weights and the bias from labeled examples. In supervised learning, a machine learning algorithm builds a model by examining many examples and attempting to find a model that minimizes loss; this process is called **empirical risk minimization**.

**Loss** is the penalty for a bad prediction. That is, loss is a number indicating how bad the model's prediction was on a single example. If the model's prediction is perfect, the loss is zero; otherwise, the loss is greater. **The goal of training a model is to find a set of weights and biases that have low loss, on average, across all examples.**

The linear regression models we'll examine here use a loss function called **squared loss** (also known as L2 loss). The squared loss for a single example is as follows:

  the square of the difference between the label and the prediction = (observation - prediction(x))^2 = (y - y')^2

**Mean square error (MSE)** is the average squared loss per example over the whole dataset. To calculate MSE, sum up all the squared losses for individual examples and then divide by the number of examples:
  MSE = sum(y - prediction (x))^2 / N, where sum is the sum of all (x, y) in D

where (x, y) is an example in which:

* x is the set of features (for example, chirps/minute, age, gender) that the model uses to make predictions.
* y is the example's label (for example, temperature).
* prediction (x) is a function of the weights and bias in combination with the set of features.
* D is a data set containing many labeled examples, which are pairs.
* N is the number of examples in D.

Although MSE is commonly-used in machine learning, it is neither the only practical loss function nor the best loss function for all circumstances.
