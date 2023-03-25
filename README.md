# Continuos Control

This repository corresponds to the second project in Udacity's Deep Reinforcement Learning Nanodegree. The goal is to train and agent control a double-jointed arm to reach a target area.

## The enviroment:

![env screenshot](https://github.com/lccrurod/navigation_drlnd/blob/main/screen%20intro%20enviroment.png)

In this enviroment an agent can observe a 33 variables corresponding to position, rotation, velocity and angular velocity of and arm and each action the arm takes is a vector with 4 entries, ranging from -1 to 1, that map to torques applied to both joints. The agent will receive +0.1 reward for every step the arm's hand is in the goal location, which translates in and objetive to stay in the tarjet location for as long as posible.

The enviroment is solved, in this version with 20 agents training simultaneosly, when each agent achieves 30+ average score in 100 consecutive episodes.

## Getting Started:

This project is aided by the [deep-reinforcement-learning](https://github.com/udacity/deep-reinforcement-learning/blob/master/README.md) repository where in the `/python` folder are the necesary files for unity enviroments, and, Separately in the `Reacher_Windows_x86_64` is located the specific enviroment for the project. The additional prerrequisites are specified in the `requirements.txt` file.

The files `model.py` and `ddpg_agent.py` are based on the available content for the course for defining a Deep Deterministic Policy Gradient and an trainable agent based on the choosen model respectively.

The process of training the agent, as well as enviroment exploration is done in the `Continuous_Control.ipynb` notebook.
