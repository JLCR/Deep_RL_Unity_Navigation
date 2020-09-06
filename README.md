<div style="text-align: justify">

[//]: # (Image References)

# Project Deep Q-Learning: Navigation

### Introduction

**Deep Learning** is part of a broader family of machine learning methods based on artificial neural networks with representation learning. Learning can be supervised, semi-supervised or unsupervised.       
    
**Reinforcement learning** is an area of machine learning concerned with how software agents ought to take actions in an environment in order to maximize the notion of cumulative reward.      
    
**Q-Learning** is a model-free reinforcement learning algorithm to learn a policy telling an agent what action to take under what circumstances. It does not require a model (hence the connotation "model-free") of the environment, and it can handle problems with stochastic transitions and rewards, without requiring adaptations.       
For any finite Markov decision process (FMDP), **Q-Learning** finds an optimal policy in the sense of maximizing the expected value of the total reward over any and all successive steps, starting from the current state. Q-learning can identify an optimal action-selection policy for any given FMDP, given infinite exploration time and a partly-random policy. "Q" names the function that returns the reward used to provide the reinforcement and can be said to stand for the "quality" of an action taken in a given state.
    
Please take the time now to read the [research paper](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf) that introduces the Deep Q-Learning (DQN) algorithm.
    
In the figure is show how the Agent interact with the Environment:

<img src="./Media/Agent-Environment-banana.png" alt="Agent-Environment" width="9500" style="text-align:center"/>

    
For this project, you will train an agent to navigate (and collect bananas!) in a large, square world:  
     
<img src="https://user-images.githubusercontent.com/10624937/42135619-d90f2f28-7d12-11e8-8823-82b970a54d7e.gif" alt="Trained Agent" width="450" style="text-align:center"/>
      
The **environment** is provided by Unity Machine Learning Agents (ML-Agents). This is an open-source plugin that enables games and simulations to serve as environments for design, train, and evaluate intelligent agents. In this project, we are using the version v0.4 interface.     
     
A **reward** of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana.  Thus, the goal of your agent is to collect as many yellow bananas as possible while avoiding blue bananas.  
      
The **state space** has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around agent's forward direction.  Given this information, the agent has to learn how to best select actions.     
Four discrete **actions** are available, corresponding to:
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

  Then, place the file in the `p1_navigation/` folder, and unzip the file.  
    
### Instructions

Follow the instructions in `Navigation.ipynb` to get started with training your own agent!  

### Files description
**- report.md:** This file describes the details of the implementation (model architecture, DQN algorithm, hyperparameters,...) and suggestions for further work.    
**- model.py:** This file specifies the pytorch model architecture used.    
**- dqn_agent.py:** This file contains all of the functions required for the agent to interact with the enviroment.    
**- checkpoint.pth:** This file contains the trained weights of trained agent. You can use this file to straight away test an agent without having to train one yourself.    
**- ipynb file:** This file is a Jupyter notebook used to train your agent.    
    
### References

+ Sutton, Richard & Barto, Andrew. [Reinforcement Learning: An introduction](https://s3-us-west-1.amazonaws.com/udacity-drlnd/bookdraft2018.pdf).   
+ Hongzi Mao?, Mohammad Alizadeh?, Ishai Menache†, Srikanth Kandula†. [Resource Management with Deep Reinforcement Learning](http://people.csail.mit.edu/hongzi/content/publications/DeepRM-HotNets16.pdf).    
+ Wikipedia [Wikipedia](https://en.wikipedia.org/wiki/Main_Page)    
</div>
