# Project report

## Learning algorithm

The learning algorithm used to solve Unity environment (bananas) is **Deep Q-Network (DQN)**.     
     
As an input the vector of state is used instead of an image so convolutional neural nework is replaced with deep neural network. 
The deep neural network has following layers:    
- Layer: input= 37 (state size) -> output= 64    
- Layer: input= 64 -> output= 32    
- Layer: input= 32 -> output= 4 (action size)    
     
Unfortunately, reinforcement learning is notoriously unstable when neural networks are used to represent the action values. 
Then, to improve the algorithm some extensions to the Deep Q-Networks (DQN) have been developed.     
Each extension address a different issue with the original DQN algorithm:    
  1 - Double DQN    
  2 - Prioritized Experience Replay    
  3 - Dueling DQN    
  4 - Multi-step bootstrap targets    
  5 - Distributional DQN    
  6 - Noisy DQN    
    
Researchers at Google DeepMind tested the performance of an agent that incorporated all six of these modifications.     
The corresponding algorithm was termed **Rainbow**.    

### Parameters used in the algorithm:
   
- Maximum number of training episodes:    
**n_episodes** (int)= 1000    
- Maximum number of timesteps per episode:    
**max_t** (int)= 500   
- Starting value of epsilon, for epsilon-greedy action selection:    
**eps_start** (float)= 1.0    
- Minimum value of epsilon:    
**eps_end** (float)= 0.01    
- Multiplicative factor (per episode) for decreasing epsilon:    
**eps_decay** (float)= 0.995    
- Whether to implement Double_DQN modification:    
  **Double_DQN** (bool)= True    
- Whether to implement Priority_Replay modification:    
  **Priority_Replay** (bool)= True    
- Whether to implement Duel_DQN modification:    
  **Duel_DQN** (bool)= True    
- These parameters determinte the priority modification. e adds to all priorities, which are raised to power of a, while b is used to de-bias the q-updates:    
  **Priority_Replay_Paras* (list of e,a,b floats)= [0.5, 0.5, 0.5]    
- Discount factor: Close to 1 will cause the agent to value all future rewards equally:    
  **GAMMA** (float): 0.99      
- Learning rate: Too large and instability is caused, while too small and the model could never converge:    
  **LR** (float): 5e-4    
- Minibatch size: Too low will cause learning instability and poor convergence, too high can cause convergence to local optima:     
  **BATCH_SIZE** (int): 64     
- Replay buffer size: size of the experience buffer. If you experience issues with RAM try lowering it:    
  **BUFFER_SIZE** (int): 1e5      
- TAU: for soft update of target parameters. How closely the target-network should track the current network:     
  **TAU** (float): 1e-3     
- Timesteps: how often to update the network:     
  **UPDATE_EVERY** (int): 4      
    
## Results

```
Episode 100	Average Score: 0.42
Episode 200	Average Score: 3.20
Episode 300	Average Score: 7.78
Episode 400	Average Score: 10.28
Episode 500	Average Score: 13.44
Episode 600	Average Score: 14.64
Episode 662	Average Score: 15.01
Environment solved in 562 episodes!	Average Score: 15.01
Episode 700	Average Score: 14.81
Episode 800	Average Score: 15.83
Episode 900	Average Score: 15.95
Episode 1000	Average Score: 16.36
```
![results](Media/scores.png)    
    
### Trained agent

![trained](Media/UnityEnvTrained.gif)

## Ideas for future work

**Agent57**, the first deep reinforcement learning agent to obtain a score that is above the  human baseline on all 57 Atari 2600 games.
Agent57 combines an algorithm for efficient exploration with a meta-controller that adapts the exploration and long vs. short-term behaviour of the agent.
Agent57 is also a distributed RL agent that decouples the data collection and the learning processes.

![Agent57](Media/Agent57.png)

FIGURE 2. AGENTS THAT USE A DISTRIBUTED SETUP ARE BLUE, WHEREAS SINGLE-ACTOR AGENTS ARE TEAL. THE 5TH PERCENTILE ANALYSIS SHOWS THAT STATE OF THE ART ALGORITHMS SUCH AS MUZERO AND R2D2 PERFORM DRAMATICALLY BELOW THE HUMAN BENCHMARK (PURPLE DOTTED LINE), WHEREAS AGENT57 PERFORMS BETTER THAN HUMANS ON THE HARDEST ATARI GAMES.

## References:
+ AGENT57 deep reinforcement learning agent. (https://deepmind.com/blog/article/Agent57-Outperforming-the-human-Atari-benchmark)


