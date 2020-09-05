<div style="text-align: justify">

[//]: # (Image References)

# Project Deep Q-Learning: Navigation

### Introduction

**Deep Learning** uses machine learning to make predictions by leveraging vast amounts of training data and a flexible architecture that is able to generalise to previously unseen examples.     
    
In **Reinforcement learning**, the goal is to have an agent learn how to navigate a new enviroment with the goal of maximising cummulative rewards. One approach to this end is **Q-Learning**, where the agent tries to learn the dynamics of the enviroment indirectly by focusing on estimating the value of each state-action pair in the enviroment. This is acheived over the course of training, using it's experiences to produce and improve these estimates.     
    
Please take the time now to read the [research paper](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) that introduces the Deep Q-Learning (DQN) algorithm.
    
In the figure is show how the Agent interact with the Environment:
![Agent-Environment](./Media/Agent-Environment-banana.png "Agent-Environment")
    
For this project, you will train an agent to navigate (and collect bananas!) in a large, square world:  
     
<img src="https://user-images.githubusercontent.com/10624937/42135619-d90f2f28-7d12-11e8-8823-82b970a54d7e.gif" alt="Trained Agent" width="450" style="text-align:center"/>
      
The environment is provided by Unity Machine Learning Agents (ML-Agents). This is an open-source plugin that enables games and simulations to serve as environments for design, train, and evaluate intelligent agents. In this project, we are using the version v0.4 interface.     
     
A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana.  Thus, the goal of your agent is to collect as many yellow bananas as possible while avoiding blue bananas.  
      
The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around agent's forward direction.  Given this information, the agent has to learn how to best select actions.  Four discrete actions are available, corresponding to:
- **`0`** - move forward.
- **`1`** - move backward.
- **`2`** - turn left.
- **`3`** - turn right.
     
The task is episodic, and in order to solve the environment, your agent must get an average score of +13 over 100 consecutive episodes.
     
### Getting Started

Step 1: Clone the DRLND Repository
If you haven't already, please follow the instructions in the DRLND GitHub repository to set up your Python environment. These instructions can be found in README.md at the root of the repository. By following these instructions, you will install PyTorch, the ML-Agents toolkit, and a few more Python packages required to complete the project.

(For Windows users) The ML-Agents toolkit supports Windows 10. While it might be possible to run the ML-Agents toolkit using other versions of Windows, it has not been tested on other versions. Furthermore, the ML-Agents toolkit has not been tested on a Windows VM such as Bootcamp or Parallels.


Step 2: Download the environment from one of the links below.  You need only select the environment that matches your operating system:    
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)    
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)    
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)     
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)       

Then, place the file in the `p1_navigation/` folder in the DRLND GitHub repository, and unzip (or decompress) the file.  
    
### Instructions

Follow the instructions in `Navigation.ipynb` to get started with training your own agent!  

## Files description

**ipynb file:** This file is a Jupyter notebook used to train your agent.

**report.md:** This file describes the details of the implementation (model architecture, DQN algorithm, hyperparameters,...) and suggestions for further work.    

**model.py:** This file specifies the pytorch model architecture used.

**dqn_agent.py:** This file contains all of the functions required for the agent to interact with the enviroment.

**checkpoint.pth:** This file contains the trained weights of trained agent. You can use this file to straight away test an agent without having to train one yourself.

### References

+ Sutton, Richard & Barto, Andrew. [Reinforcement Learning: An introduction](https://s3-us-west-1.amazonaws.com/udacity-drlnd/bookdraft2018.pdf).   
+ Hongzi Mao?, Mohammad Alizadeh?, Ishai Menache†, Srikanth Kandula†. [Resource Management with Deep Reinforcement Learning](http://people.csail.mit.edu/hongzi/content/publications/DeepRM-HotNets16.pdf).
