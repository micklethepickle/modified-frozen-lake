# Modified Frozen Lake Environment

## Description
The environment is based on the [OpenAI gym](https://gym.openai.com) implementation of FrozenLake. It is the same environment, but we are allowed to modify the slip_rate of the agent to whatever we choose.
The other difference in this environment are the rewards: a reward of -1 is observed for every transition until one of three things happen. (1) the agent falls into a hole, giving a reward of -100,
(2) the agent takes over 100 steps, all of the ice melts and the agent gets a reward of -50, and (3) the agent reaches the goal state, rewarding it a reward of 0. 

## How to use
This environment follows the OpenAI gym API. For a short introduction and installation guide you can refer to <https://gym.openai.com/docs/>, but basic instructions on how to use it are shown here.
Suppose you instantiate the environment like so: `env = FrozenLakeEnv(map\_name="4x4", slip\_rate=0.1)`
### Basic information on environnment
To get the number of possible actions (in discrete environments): `env.action_space.n`

To get the number of states (in discrete environments): `env.observation_space.n`

### Navigating an episode
Before you start an episode, you must reset the environment using the reset function. This function also returns the inital state of the environment.

`initial_state = env.reset()`

If you would like to take a step in the environment, call the `.step(a)`, where `a` is the action you would like to take. This function will automatically update the state of the
environment with respect to the action taken. It also provides useful information about the transition taken.

`next_state, reward, done, extra = env.step(a)`

Where `next_state` gives you the next state of the environment, `reward` gives the reward for taking `a` in the current state, `done` is a boolean telling you whether the episode has terminated
and `extra` is any extra information the environment migth want to provide (you do no need to worry about this for this example).

## Note: You should not need to call any other methods for this assignment.
