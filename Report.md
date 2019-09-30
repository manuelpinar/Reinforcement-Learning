                                          Project 1. Navigation
1.	Environment

I will train an agent to navigate (and collect bananas!) in a large, square world.
A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana. Thus, the goal of your agent is to collect as many yellow bananas as possible while avoiding blue bananas.
The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select actions. Four discrete actions are available, corresponding to:

0 - move forward.

1 - move backward.

2 - turn left.

3 - turn right.


The task is episodic, and in order to solve the environment, your agent must get an average score of +13 over 100 consecutive episodes.

2.	Hyperparameters

I used the same hyperparaters used in the lesson when we coded the dqn agent:
BUFFER_SIZE = int(1e5)      # replay buffer size

BATCH_SIZE = 64             # minibatch size

GAMMA = 0.99                # discount factor

TAU = 1e-3                  # for soft update of target parameters

LR = 5e-4                   # learning rate 

UPDATE_EVERY = 4            # how often to update the network


3.	Learning algorithm

I used the DQN algorithm used in the lesson. I only changed the neural network model, adding one more linear layer.


In DQN algorithm  we use non linear aproximators to calculate the value action based directly on observation from the environment. We 
represented it as a DEEP NEURAL NETWORK instead of a table.
The Neural Network learns the value of each action at each state. The input of the neural network has dimension of 37 because the environment's state has 37 dimension and the output of the network is an array of 4 values because there are 4 possible actions for the agent.

This could be unstable, to solve this we can use:

- EXPERIENCE REPLAY

- FIXED Q-TARGET

This implementation could be improve using:

- Dueling networks

- Double DQN

- Prioritized experience replay 

Our neural network in model.py:

FC1 (128 unit) with relu  --> FC2 (64 units) with relu --> FC3 (64 units) 

4.	Results

Episode 100	Average Score: 0.92

Episode 200	Average Score: 4.75

Episode 300	Average Score: 7.83

Episode 400	Average Score: 11.09

Episode 471	Average Score: 13.02


Environment solved in 371 episodes!	Average Score: 13.02

![](https://github.com/manuelpinar/Reinforcement-Learning/blob/master/results.png)

