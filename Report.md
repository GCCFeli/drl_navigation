[//]: # (Image References)

[image1]: https://github.com/GCCFeli/drl_navigation/blob/master/Rewards.png?raw=true "Rewards" 
[image2]: https://github.com/GCCFeli/drl_navigation/blob/master/Navigation.gif?raw=true "Result"  

# Report

## 1. Getting started

Please follow the instructions in README.md to setup the environment.

## 2. Learning Algorithm

DQN with replay buffer and soft update is used to solve this problem. A 2-layer DNN is chosen for this task. Layer sizes are 128, 64. Activation function is ReLU. 

Hyperparameters are listed below:

Replay buffer size: 100000

Batch size: 64

Gamma: 0.99

Soft update target paramater tau: 0.001

Learning rate: 0.0005

Update network every 4 frames

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
