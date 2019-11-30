# Report

## Learning Algorithm

The navigation problem was framed as a reinforcement learning task. To solve it the Deep Q-Learning Algorithm was chosen.

The basis for the implementation was the research paper [*'Human-level control through deep reinforcement
learning'*](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf).

The algorithm is based on the combinantion of basic reinforcement learning principles and deep neural networks.

The algorithm basically replaces the Q-table (which is good for descrete features) with a function q* (which calculates the expected reward for all possible actions in all possible states) which is estimated via a neural network.
To find the optimal policy the agent needs to maximaze the q* function.

To go through the whiole algorithm the agent first selects actions randomly and collects a pool of (state, action, reward, new state) tuples (experience tuples) that are used in further learnig. With every change of state all the possible rewards for all possible actions are estimated and the action with the highest estimated value is chosen.
To combat the correlation between the variables we try to optimise (that is weights constructing the q* function) and the values we use to calculate them, two neural nets were used. Bowt networks have identical architecture, but we optimise the values of the 'local function' on the basis of the rewards calculated one time step earlier (by the target function). After the update, the target function receives the previous weights of the local function, ant thus the cycle goes on.
To maximze the use of already examined experience tuples a so called Experience Replay mechanism is used. It basically puts the experience tuples in a fixed size pool, from which they are sampled randomly. This also helps to avoid any unwanted correlation between chronologically adjacent actions.

The local and target neural networks both have the same architecture (defined in model.py) and consist of three fully connected layers, out of which two use ReLu activation Functions.

The files *model.py* and *dqn_agent.py* were taken from the Deep Q-Learning Coding Exercise in the Udacity Deep Reinforcement Learning Nanodegree.

**Hyperparameter values**

First hyperparameters values were directly inspired by the 'Human-level control through deep reinforcement
learning' research paper. They are used as default values in dqn function. As the training took many apisodes to converge, Another set of values was chosen. 
To make the convergence faster the best way seemed to be allowing the agent for more exploration. 
To this end the minimum value of epsilon was set to a higher value (from 0.01 to 0.02). 
To make up for this however, the decay of epsilon was set to a lower value (from 0.995 to 0.95), which means that the epsilon would decay faster. 

## Plot of Rewards



## Ideas for Future Work

1. Further hyperparameter tuning and longer training, with a goal set to a higher value (like 15), to make the agent get better results.
2. Using Prioritized Experience Replay, to emphesisze the more important or rarest experience tuples.
3. Using of Dueling DQN, which are based on two separate neural networks, one for state and one for action advantage. In the end thety are both used to get the Q-value. This helps the  agent to generalize and works better with many similarly rewarded actions.
