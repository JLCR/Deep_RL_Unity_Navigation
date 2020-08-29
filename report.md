# Project report

## Learning algorithm
*Actualizar*
The learning algorithm used is Deep Q Learning. 
As an input the vector of state is used instead of an image so convolutional neural nework is replaced with deep neural network. 
The deep neural network has following layers:

- Fully connected layer - input: 37 (state size) output: 128
- Fully connected layer - input: 128 output 64
- Fully connected layer - input: 64 output: (action size)

### Parameters used in the algorithm:

**n_episodes (int): maximum number of training episodes**\
the model was found to converge after ~1000 episodes.

**max_t (int): maximum number of timesteps per episode**\
this is useful for envioments that permit infinite exploration as it helps reset the enviroment.

**eps_start (float): starting value of epsilon, for epsilon-greedy action selection**\
to encourage early exploration of the state-action space we're using an epsilon-greedy apporach with epsilon starting at 1.

**eps_end (float): minimum value of epsilon**\
Epsilon should never reach 0 or else in the limit we might not explore all state-action pairs, so this sets a lower bound at 0.01

**eps_decay (float): multiplicative factor (per episode) for decreasing epsilon**\
we want epsilon to decay over the course of training as the agent transitions from exploration to exploitation. This was set to 0.995.

**Double_DQN (bool): whether to implement Double_DQN modification**\
Non-functional currently, leave as True

**Priority_Replay (bool): whether to implement Priority_Replay modification**\
Non-functional currently, leave as True

**Duel_DQN (bool): whether to implement Duel_DQN modification**\
Non-functional currently, leave as True

**Priority_Replay_Paras (list of e,a,b floats):**\
These determine the parameters of the priority modification. e adds some priority to all experiences to prevent over-fitting to a subset of the state-action space. Priorities are raised to the power of a, where a value close to 0 encourages uniform sampling whereas close to 1 emphasises priorities. Lastly the update rule itself becomes biased due to non-uniform sampling, as so must be corrected, with b controling the degree of correction, which is increased over the course of training. How these parameters relate to one another can be seen below:

<img src="https://github.com/Remtasya/DRLND-project-1-navigation/blob/master/project_images/priority_replay.PNG" alt="replay" width="600"/>

**GAMMA (float): discount rate**\
Close to 1 will cause the agent to value all future rewards equally, while close to 0 will cause the agent to prioritise more immediate rewards. Unlike most hyperparameters, this will not only effect convergence but also the optimal policy converged to. For example if an agent must choose between collecting 1 bananna and then waiting 20 timeseteps versus collecting 2 banannas after 20 timesteps, then the optimal policy depends on the reard discount rate. Close to 1 is often best so I chose 0.99.


**LR (float): model hyperparameter - learning rate**\
This determines how large the model weight updates are after each learning step. Too large and instability is caused, while too small and the model may never converge. I chose the small 5e-4, since we can increase epsiodes until we reach convergence. 

**BATCH_SIZE (int): model hyperparameter - number of experiences sampled for a model minibatch**\
Too low will cause learning instability and poor convergence, too high can cause convergence to local optima. I chose 64 as a default.


**BUFFER_SIZE (int): replay buffer size**\
this is the size of the experience buffer, which when exceeded will drop old experiences. This is mainly limited by your available RAM - if you experience issues with RAM try lowering it


**TAU (float): how closely the target-network should track the current network**\
After every learning step the target-network weights are updated closer to the current network, so that the target-network weights are a moving average over time of the current network past weights. i chose a relatively small value (1e-3) although haven't experimented with tuning it.

**UPDATE_EVERY (int): how often to update the network**\
How many steps should pass before an update of the current network takes place. I chose every 4 timesteps.




## Results

![results](media/rewards.png)

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

### Untrained agent

![untrained](media/untrained.gif)

### Trained agent

![trained](media/trained.gif)

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
