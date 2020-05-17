# Project 1: Navigation
### Author: Angelo Antonio Manzatto 
------------------------------
### Introduction

For this project, you will train an agent to navigate (and collect bananas!) in a large, square world.  

A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana.  Thus, the goal of your agent is to collect as many yellow bananas as possible while avoiding blue bananas.  

### Space State
------------------------------------------------------

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around agent's forward direction.  Given this information, the agent has to learn how to best select actions.  

### Action State
------------------------------------------------------

Four discrete actions are available, corresponding to:
- **`0`** - move forward.
- **`1`** - move backward.
- **`2`** - turn left.
- **`3`** - turn right.

### Acceptance Criteria
------------------------------------------------------
The task is episodic, and in order to solve the environment, your agent must get an average score of +13 over 100 consecutive episodes.

### Algorithm 
------------------------------------------------------
This project uses a **Deep Q-Networks (DQN)** algorithm to train an agent on collecting the yellow bananas on the environment at the same time it avoids the blue ones.

### Model 
------------------------------------------------------
The Aritficial Neural Network models used on this project contains just fully connected layers using ReLU activation using the following architecture:

* FC Layer 1 (states, 32)
* FC Layer 2 (32, 32)
* FC Layer 3 (32, actions)

The number of states are 37 while for the actions are 4 like described above. I tried to use just a few number of neurons (32) on the hidden layers to get the simplest model capable of solving the problem and it worked as much the as using the double (64).

###  Hyperparameters
------------------------------------------------------
The parameters used during training were:

| Hyperparameter | Value     | Description |
| ----------- | ----------- | ----------- |
|BUFFER_SIZE | 10000 |replay buffer size|
|BATCH_SIZE | 64 |minibatch size|
|GAMMA | 0.99 |discount factor|
|TAU | 0.001 |for soft update of target parameters|
|LR | 0.0005| learning rate|
|UPDATE_EVERY | 4 |how often to update the network|

### Evalutation
-----------------------------------------------------
The problem was solved after 411 episodes meaning that a simple ANN model can beat it using just some minimal information from the environment.

Below we can see  a plot of rewards per episode.

![Plot](/images/results.png)

### Ideas for the future
-----------------------------------------------------
The next step towards a more rewarding challenge should be using the image data like the original DQN paper used when learning the Atari games.

There is also other more advanced Deep Learning Algorithms that could be put on test for this challenge like:
* Double DQN
* Dueling DQN
* Rainbow

The ultimate challenge would be to build a C++ solution instead of a Python one.
