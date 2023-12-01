---
layout: post
title: Constructing Strictly Group Equivariant Self-Attention
date: 2023-05-12 15:53:00-0400
description: Injecting Geometric Priors into the Transformer Model
giscus_comments: true
related_posts: true
tags:
  - transformer
  - geometric-deep-learning
---
In the following , we will see the benefits of injecting geometric priors into the transformer model.
The approach we discuss is introduced in a paper of David Romero et al.
To this end we will go through the following concepts:
- Convolutional- and Self-Attention Neural Networks
- Stand-Alone Self-Attention Transformer for Vision
- Group Theory Fundamentals
- Group Convolution  and Group Self-Attention

This is a technical deep dive - for a higher level overview please find this article.
### Motivation
Even though the application of transformers in the vision domain shows promising results, they still can not compete with the best performing models of the domain, which are mainly based on CNNs.
One reason is that CNNs have a natural geometric prior, that is translation equivariance. Further, they are already extended by using group theory. See for example group convolution.
A natural idea would be to inject those same geometric priors into the self-attention operation of the transformer. Luckily, this is possible - and in this article we will figure out how.
Stand-Alone
## Convolutional Neural Networks and Self-Attention Networks

Both, Convolutional Neural Networks (CNNs) and Self-Attention Networks -that appear often in the form of Vision Transformers ( ViT) - are extremely successful neural architectures in the field of computer vision and beyond.

We will review the main ideas of both and then slowly build our way up to extend them with geometric priors by using group theory.
### Convolutional Neural Networks
Convolutional Neural Networks are introduced in [] and are still a popular contestant among state-of-the-art vision models.
Their main idea builds around the idea of the convolution operation.
It is one of the first and most successful neural architecture, which follows the blueprint of Geometric Deep Learning. Due to the way


### Self-Attention Networks

#### Stand-Alone Self-Attention for Vision
As it is introduced in [1], the work-horse of this concept  is the self-attention operation applied to a local receptive field N-k.
Self-Attention for a specific output $yᵢⱼ$ a former article (Stand-Alone Self-Attention for Vision from Scratch) I explain this concept in more detail and show how to implement it in PyTorch.
In the following, we will extend this concept by using group theory to induce geometric priors.

## Group Equivariant Networks

Explain why are they cool :-).
### Group Theory Fundamentals

Group Theory, with its roots in mathematics, provides a formal framework for understanding symmetries and transformation. Leveraging group theory in neural networks allows us to imbue them with desirable properties, such as equivariance to transformations, which we also refer to as geometric priors.

Let us start with the mathematical definition of a group.
A group is a set $\mathfrak{G}$ along with a binary operation $$\circ : \mathfrak{G} × \mathfrak{G} \rightarrow \mathfrak{G}$$ called composition (for brevity we write $\mathfrak{g} \mathfrak{h}$ instead of $\mathfrak{g} \circ \mathfrak{h}$ satisfying the following axioms:
- Associativity: $(\mathfrak{g} \mathfrak{h})\mathscr{k} = \mathfrak{g}(\mathfrak{h}\mathscr{k})$ for all $\mathfrak{g}, \mathfrak{h}, \mathscr{k} \in \mathfrak{G}$.
- Identity: there exists a unique $\mathfrak{e} \in \mathfrak{G}$ satisfying $\mathfrak{e}\mathfrak{g} = \mathfrak{g}\mathfrak{e} = \mathfrak{g}$ for all $\mathfrak{g} \in \mathfrak{G}$.
- Inverse: For each $\mathfrak{g} \in \mathfrak{G}$ there is a unique inverse $\mathfrak{g}^{-1}  \mathfrak{G} \text{ s.t. } \mathfrak{g} \mathfrak{g}^{-1} = \mathfrak{g}^{-1}\mathfrak{g} = \mathfrak{e}$.
- Closure: The group is closed under composition, i.e., for every $\mathfrak{g}, \mathfrak{h} \in \mathfrak{G}$, we have $\mathfrak{g}\mathfrak{h} \in \mathfrak{G}$.

Note that if additionally commutativity holds, then our group is called an Abelian group.
### Group Convolutional Neural Networks



### Group Equivariant Self-Attention