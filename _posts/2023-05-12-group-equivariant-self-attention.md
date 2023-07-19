---
layout: post
title: Constructing Group Equivariant Self-Attention
date: 2023-05-12 15:53:00-0400
description: Injecting Geometric Priors into the Transformer Model
tags: self-attention transformer geometric deep learning
categories: blog-post
giscus_comments: true
related_posts: true
---


In this article we will see the benefits of injecting geometric priors into the transformer model by using group theory.
The approach is based on this paper of David Romero et al.
To this end we will go through the following concepts:
Stand-Alone Self-Attention Transformer for Vision
Group Theory Fundamentals
Group Self-Attention

For a  more high level overview see also my other blog post about this topic.

### Motivation
Even though the application of transformers in the vision domain shows promising results, they still can not compete with the best performing models of the domain which are mainly based on CNNs.
One reason is that CNNs have a natural geometric prior, that is translation equivariance. Further, they are already extended by using group theory. See for example group convolution.
A natural idea would be to inject those same geometric priors into the self-attention operation of the transformer. Luckily, this is possible - and in this article we will figure out how.
Stand-Alone Self-Attention for Vision
As it is introduced in [1], the work-horse of this concept  is the self-attention operation applied to a local receptive field N-k.
Self-Attention for a specific output yᵢⱼIn a former article (Stand-Alone Self-Attention for Vision from Scratch) I explain this concept in more detail and show how to implement it in PyTorch.
In the following, we will extend this concept by using group theory to induce geometric priors.

### Group Theory Fundamentals

Group Theory has a rich history with contributions from a variety of fields. CITE MICHAEL BRONSTEIN HERE.
Let us define a group as follows. 
A group is a set G along with a binary operation ◦ : G × G → G called composition (for brevity we write gh instead of g ◦ h) satisfying the following axioms:
- Associativity: (gh)k = g(hk) for all g, h, k ∈ G.
- Identity: there exists a unique e ∈ G satisfying eg = ge = g for all g ∈ G.
- Inverse: For each g∈G there is a unique inverse g⁻¹∈G s.t. gg⁻¹ = g⁻¹g = e.
- Closure: The group is closed under composition, i.e., for every g, h ∈ G, we have gh ∈ G.
Note that if additionally commutativity holds, then our group is called an Abelian group.
Group Equivariant Stand-Alone Self-Attention