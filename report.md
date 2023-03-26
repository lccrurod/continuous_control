# Project Report

## Learning Algorithm
The method choosen for this challenge was Deep Deterministic Policy Gradient, inspired by the ddpg-bipedal implementations, adatpted to the current enviroment. The algorithm DDPG is a combination of DQN and DPG, it is specifically adapted for enviroments with continuos action spaces, what it does is concurrently learn both an approximation of the optimal Q-function and optimal action.

### Arquitecture

The agent is composed of actor/critic networks with the following structure:

#### Actor Network
 * **First Layer.** 33 (state dimensions) input - 128 output
 * **Second Layer.** 128 input - 128 output
 * **Third Layer.** 128 input - 4 (actions) output

#### Critic Network
 * **First Layer.** 33 (state dimensions) input - 128 output
 * **Second Layer.** 132 (128 first layer + 4 actions) input - 128 output
 * **Third Layer.** 128 input - 1 (state value) output


### Parameters

 * replay buffer size: 10.000
 * minibatch size: 128
 * discount factor: 0.99
 * tau: 0.001
 * actor network learning rate: 0.0001
 * critic network learning rate: 0.0001
 * L2 weight decay = 0

## Training Results

```
Episode 10	Average Score: 0.74
Episode 20	Average Score: 1.58
Episode 30	Average Score: 3.23
Episode 40	Average Score: 5.57
Episode 50	Average Score: 8.76
Episode 60	Average Score: 12.45
Episode 70	Average Score: 15.44
Episode 80	Average Score: 17.73
Episode 90	Average Score: 19.57
Episode 100	Average Score: 21.15
Episode 110	Average Score: 24.77
Episode 120	Average Score: 28.22

Environment solved in 26 episodes!	Average Score: 30.12
```
![results graph](https://github.com/lccrurod/continuous_control_drlnd/blob/main/training%20results.png)

Also there is a video of the trained agent performing the reacher task.

[<img src="https://github.com/lccrurod/continuous_control_drlnd/blob/main/thumbnail%20trained%20agent.png" width="272" height="151">](https://www.youtube.com/watch?v=_AtHZEgRJvk)

## Improvement Opportunities

As seen in the video of the trained agent solving the task, the arms aren't really tracking the target location well enough, something observed was that the tracking started really well and, as time goes by, the tracking gets all over the place. So that would be the main area of improvement, experiment around episode time and layer architecture to get at the bottom of the issue.

Another ideas for improvement are:

- Implement A3C algorithm that would allow the agent to get insights of how good rewards were compared to it's expectation therefore enhancing the learning process.
- Implement A2C that could replicate A3C perfomance while being more efficient and having the alternative to do parallelize training.
- Also exploring with prioritized experience replays would definitely help extract the value in the episodes experimented by the agents thereby improving learning.
