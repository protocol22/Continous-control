[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/10624937/43851024-320ba930-9aff-11e8-8493-ee547c6af349.gif "Trained Agent"
[image2]: https://user-images.githubusercontent.com/10624937/43851646-d899bf20-9b00-11e8-858c-29b5c2c94ccc.png "Crawler"


# Project 2: Continuous Control

### Introduction

The aim of this project is to train a double-jointed arm to move to target location. For this project, we will work with the [Reacher](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher) environment.

![Trained Agent][image1]

A reward of +0.1 is provided for each step that the agent's hand is in the goal location. Thus, the goal of your agent is to maintain its position at the target location for as many time steps as possible.

The observation space consists of 33 variables corresponding to position, rotation, velocity, and angular velocities of the arm. Each action is a vector with four numbers, corresponding to torque applicable to two joints. Every entry in the action vector should be a number between -1 and 1.

### Distributed Training

In this project, there are two separate versions of the Unity environment:
- The first version contains a single agent.
- The second version contains 20 identical agents, each with its own copy of the environment.  

### Solving the Environment

For the purpose of the project only the second environment is considered and all the details henceforth will be provided only  for the implementation of the second environment with 20 agents. The task is episodic. As this version consists of multiple agents. The criteria for solving the environment is as follows.The agents must get an average score of +30 (over 100 consecutive episodes, and over all agents).   
- After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent.  This yields 20 (potentially different) scores.  We then take the average of these 20 scores. 
- This yields an **average score** for each episode (where the average is over all 20 agents).

### Getting Started
1. Setup the environment required for running the solution by following the instruction in the [click here](https://github.com/udacity/deep-reinforcement-learning.git) in the dependencies section. 

1. Download the environment from one of the links below.  You need only select the environment that matches your operating system:

    - **_ Twenty (20) Agents_**
        - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
        - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip)
        - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip)
        - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)
    
    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

3. Clone the repository and place the extracted file in the home director of the repository and run the model using the `Continuous_Control.ipynb` file


### Solution

The agent is solved using a ddpg algorithm refer to `ddpg_agent.py` for the algorithm, the neural network model used for this purpose is given in the file `model.py` and the solution can be found in `Continuous_Control.ipynb` along with trained actor and critic weights in `checkpoint_actor.pth` and `checkpoint_critic.pth`  
