# Navigation - deep reinforcement learning

Navigation problem in a Unity environment solved with Deep Q Learning algorithm

## Project Details

The project aims at training an agent to navigate and collect bananas in a large, square world.

A reward of +1 is provided for collecting a yellow banana, and a reward of -1 is provided for collecting a blue banana. 

The state space has 37 dimensions and contains the agent's velocity, along with ray-based perception of objects around the agent's forward direction. Given this information, the agent has to learn how to best select actions. Four discrete actions are available, corresponding to:

    0 - move forward.
    1 - move backward.
    2 - turn left.
    3 - turn right.
    
The task is episodic, and in order to solve the environment, the agent must get an average score of +13 over 100 consecutive episodes.

## Getting Started

To run this repo on your local machine, first clone this repository https://github.com/udacity/deep-reinforcement-learning

Follow the instruction in the README file in the root of the folder to install the Python environment needed to run the whole project. 

Follow the instructions in the README of p1_naviagtion (https://github.com/udacity/deep-reinforcement-learning/tree/master/p1_navigation) to install the correct environment for Your operating system.
You don't need to install Unity separately, as Unity Agents are already configured in the environment. 

Make sure you have CUDA Drivers installed.

Finally place the files from this repo into the p1_navigation folder of the deep-reinforcement-learning repository and run the Jupyter Notebook Navigation.ipynb. Make sure the name of the environment you downloaded matches the one specified in the code 
`env = UnityEnvironment(file_name="/data/Banana_Linux_NoVis/Banana.x86_64")`

## Instructions

To run the code, simply open the Navigation.ipynb notebook. 

If you want to train an agent from scratch just tuning the hiperparametrs, just run the dqn function with the chosen values of hyperparameters. 

You can also load the two provided checkpoints to see how the already trained agents are doing. To do this, just run the code cells in chapter 5.
