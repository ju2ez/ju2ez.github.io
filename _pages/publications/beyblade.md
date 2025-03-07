---
layout: page
title: A Multi-brain Approach for Multiple Tasks in Evolvable Robots
permalink: /beyblade/
date: 2024-03-03 16:40:16
tags: evolutionary-robotics
categories: robotics evolutionary-algorithms
published: true
---

# A Multi-brain Approach for Multiple Tasks in Evolvable Robots

[Our paper](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=MIqK3DgAAAAJ&citation_for_view=MIqK3DgAAAAJ:d1gkVwhDpl0C) discusses the idea of evolving body and brain for two tasks: rotation and moving forward on a straight line.
We can combine these two actions to give the robot the ability to search for a target by rotating, and then to move to it.

## How does the result look like?

In the end we have a controller that can switch between two brains. One brain that has evolved and learned to let the robot rotate, and the other brain that moves the robot straight ahead on a line.

<video width="100%" controls autoplay loop muted>
  <source src="/assets/video/beyblade/one_target.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

<video width="100%" controls autoplay loop muted>
  <source src="/assets/video/beyblade/two_targets_first.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>


You can see the results that enables the robot to chase after its target. First it rotates to find it, then it moves straight towards it.
Moreover, in the second video, we demonstrate that this approach can be extended to look for and chase multiple targets.


## Why this might be relevant?

Being able to achieve a more complex chain of actions to solve certain tasks is crucial for the survival of a species. 
For the robot, we mimik the behaviour to look for and move towards an object that could be a battery charger.

Having energy is crucial for the robot to survive.




## The approach

We follow a two-stage approach to get robot morphologies that are able to perform the two tasks of rotation and targeted locomotion effectively.
In the first stage we evolve the robot brain and morphology together with NSGA2 and in the second stage - the learning stage - we evolve the brain of the robot with one of the two objectives. 

![Two-stage approach](../assets/img/beyblade/two_stage_approach.png)

The first stage is to evolve a population of robots with NSGA2 that can perform the two tasks.
We choose the robots from the pareto front of the NSGA2 run.

In the second stage, we evolve a population of robots with a n




We first evolved a population of robots with NSGA2.
The two objectives were rotation and targeted locomotion.
In this

![NSGA2 with orange pareto front](../assets/img/beyblade/nsga2.gif)

## Results


## Future Outlook

### By creating unique action spaces, we are laying the foundation for reinforcement learning
....

### Neuroevolution alongside RL 


