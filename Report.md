[//]: # (Image References)

[image1]: https://github.com/GCCFeli/drl_navigation/blob/master/Rewards.png?raw=true "Rewards" 
[image2]: https://github.com/GCCFeli/drl_navigation/blob/master/Navigation.gif?raw=true "Result"  

# Report

## 1. Getting started

Please follow the instructions in README.md to setup the environment.

## 2. Learning Algorithm

### 2.1 DQN

This RL problem's state space is continous, and action space is descrete. So we choose the well known DQN([Deep Q-Networks](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf "Deep Q-Networks")) which perfectly matches the problem. 
DQN is able to combine reinforcement learning with a class of artificial neural network known as deep neural networks (DNN).

In this problem, we choose a simple 2-layer neural network to approximate the optimal action-value function. Nerual network input is just the state. Action input is omitted since it is not related to action-value approximation. Layer sizes are 128, 64. Activation function is ReLU. Loss function is MSE. Optimizer is Adam. Replay buffer and soft update is used to make learning stable.

### 2.2 Hyperparameters

| Hyperparameter | Value | Desctiption |
| -------------- | ----- | ----------- |
| minibatch size | 64 | Number of training cases over each stochastic gradient descent (SGD) update is computed. |
| replay buffer size | 100000 | SGD updates are sampled from this number of most recent frames. |
| learning frequency | 4 | SGD update is applied every 4 frame. |
| soft update target paramater | 0.001 | Soft update target parameter  τ used to lerp between local network and target network. |
| discount factor | 0.99 | Discount factor gamma used in the Q-learning update. |
| learning rate | 0.0005 | The init learning rate used by Adam. |
| initial exploration | 1.0 | Initial value of ε in ε-greedy exploration. |
| final exploration | 0.01 | Final value of ε in ε-greedy exploration. |

## 3. Plot of Rewards
![Rewards][image1]

## 4. Result
![Result][image2]

## 5. Ideas for Future Work

A simple DQN is enough to solve this problem. However, some techniques can be used to improve training efficiency or final agent performance:
* Double DQN (DDQN)
* Prioritized experience replay
* Dueling DQN
* Rainbow DQN

Hyperparameters are manually chosen for this problem. Grid search will be helpful to choose a better hyperparameter set.
