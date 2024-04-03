---
layout: post
title: Einstein sum (einsum)
date: 2024-03-03 16:40:16
description: Einstein sum is an elegant way to manipulate tensors in deep learning. In this article, we will discuss the einsum operation and how we can use it to manipulate tensors in deep learning.
tags: deep-learning tensor einsum einops
categories: scratchpad draft WiP
---

### Einstein Sum

Back in the days, German was widely used in the sciences, and what Einstein essentially proposes here is that if an index occurs two times within a summation term - and if not stated otherwise - we take a sum over it. 
Using this convention, we can drop the summation sign to simplify the equation.

For instance, let us simplify the following equation:
$$
y = \sum_{i=1}^{3} c_i x_i = c_1 x^1 + c_2 x^2 + c_3 x^3
$$

Breaking it down, we can see that the index $i$ is repeated twice in the equation, and therefore we can drop the summation sign.
$$
y = c_i x^i
$$

This leaves us with a much shorter equation.

Now let us see how we can use this convention to do the tensor manipulation we typically need in Deep Learning.

### Einops Is All You Need

We use the einops library to manipulate tensors in Deep Learning. It is a powerful library that allows us to manipulate tensors in a very concise way.

Best, we can avoid the need to remember the order of dimensions in the tensor, since we can specify them explicitly in the operation.


### Fundamental Operations

The fundamental operations are *rearrange*, *reduce*, and *repeat*. We can use these operations to manipulate tensors in a very concise way.

Let's discuss them one by one.
Rearrange can be used to change the order of dimensions in a tensor. For instance, we can use it to change the order of dimensions in a tensor from `NCHW` to `NHWC`.

{::nomarkdown}
{% assign jupyter_path = 'assets/jupyter/einops.ipynb' | relative_url %}
{% capture notebook_exists %}{% file_exists assets/jupyter/blog.ipynb %}{% endcapture %}
{% if notebook_exists == 'true' %}
  {% jupyter_notebook jupyter_path %}
{% else %}
  <p>Sorry, the notebook you are looking for does not exist.</p>
{% endif %}
{:/nomarkdown}


### Deep Learning Applications

We can use the einops library to manipulate tensors for various deep learning applications and architecture. In this article I would like to introduce you to the dot product and to the self-attention operation of the transformer model.

