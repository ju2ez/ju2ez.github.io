---
layout: post
title: adam vs adamW
date: 2024-04-04 14:10:00
description: the difference between adam and adamW
tags:
  - deep-learning
  - optimizers
categories: scratchpad
published: false
---

Adam is a popular optimizer in deep learning. It is an adaptive learning rate optimization algorithm that is designed to combine the advantages of two other extensions of stochastic gradient descent: AdaGrad and RMSProp. Adam stands for Adaptive Moment Estimation, and it is introduced by Kingma and Ba in their paper [Adam: A Method for Stochastic Optimization](https://arxiv.org/abs/1412.6980).

It is hugely popular in the deep learning community because it is computationally efficient, has little memory requirements, is invariant to diagonal rescaling of the gradients, and is well suited for problems that are large in terms of data and/or parameters. However, it is proposed with a wrong formulation of weight decay, which is corrected in the AdamW optimizer.

### Stochastic Gradient Descent

To get the full picture of what AdamW improves, it is useful to recapture the stochastic gradient descent algorithm. The stochastic gradient descent algorithm is a simple optimization algorithm that is used to minimize a function. It works by iteratively moving in the direction of the negative gradient of the function at the current point. The negative gradient points in the direction of the steepest descent, and moving in this direction will decrease the value of the function.


