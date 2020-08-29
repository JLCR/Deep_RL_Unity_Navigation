# Project report

## Learning algorithm
*Actualizar*    
The learning algorithm used is Deep Q-Network (DQN) to solve Unity environment.     
     
As an input the vector of state is used instead of an image so convolutional neural nework is replaced with deep neural network. 
The deep neural network has following layers:

- Fully connected layer - input: 37 (state size) output: 128
- Fully connected layer - input: 128 output 64
- Fully connected layer - input: 64 output: (action size)

### Parameters used in the algorithm:
   
- Maximum number of training episodes:    
**n_episodes (int)= 1000**    
- Maximum number of timesteps per episode:    
**max_t (int)= 500**    
- Starting value of epsilon, for epsilon-greedy action selection:    
**eps_start (float)= 1.0**    
- Minimum value of epsilon:    
**eps_end (float)= 0.01**    
- Multiplicative factor (per episode) for decreasing epsilon:    
**eps_decay (float)= 0.995**    
- Whether to implement Double_DQN modification:    
**Double_DQN (bool)= True**    
- Whether to implement Priority_Replay modification:    
**Priority_Replay (bool)= True**    
- Whether to implement Duel_DQN modification:    
**Duel_DQN (bool)= True**    
- E adds to all priorities, which are raised to power of a, while b is used to de-bias the q-updates:    
**Priority_Replay_Paras (list of e,a,b floats)= [0.5, 0.5, 0.5]**      



## Results

```
Episode 100	Average Score: 0.19
Episode 200	Average Score: 1.38
Episode 300	Average Score: 5.51
Episode 400	Average Score: 8.90
Episode 500	Average Score: 11.13
Episode 600	Average Score: 14.67
Episode 637	Average Score: 15.02
Environment solved in 537 episodes!	Average Score: 15.02
Episode 700	Average Score: 15.54
Episode 800	Average Score: 15.26
Episode 900	Average Score: 17.20
Episode 1000	Average Score: 16.41
```
![results](Media/rewards.png)

### Untrained agent

![untrained](Media/untrained.gif)

### Trained agent

![trained](Media/trained.gif)

## Ideas for future work

1. Extensive hyperparameter optimization
2. Double Deep Q Networks
3. Prioritized Experience Replay
4. Dueling Deep Q Networks
5. RAINBOW Paper
6. Learning from pixels


Additions that might improve the algorithm further are the other 3 modifications of the Rainbow implementation, which acheives state-of-the-art-performance in DQNs.

<img src="https://s3.amazonaws.com/video.udacity-data.com/topher/2018/June/5b3814f1_screen-shot-2018-06-30-at-6.40.09-pm/screen-shot-2018-06-30-at-6.40.09-pm.png" alt="Rainbow" width="400"/>

**Namely these are:**

1.  Learning from multi-step bootstrap targets -  https://arxiv.org/abs/1602.01783
2.  Distributional DQN - https://arxiv.org/abs/1707.06887
3.  Noisy DQN - https://arxiv.org/abs/1706.10295
