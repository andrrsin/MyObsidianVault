#Theory/AI 
# The Agent, enviroment mechanism
- **Agent:** component of the program, which is learning from environment.
- **Enviroment:** area where agent can perform actions and change the environment. In general, the environment may change over time based on or without Agent impact.

Some examples of this could be a chess game. Where the agent is th eplayer and the enviroment is the board configuration.

Some implementations of this way of AI is [[Q-Learning]] and [[Monte-Carlo tree search]]
## Agent
The agent interacts with the enviroment by doin gactions in a loop. This is made following some specific steps.
![[Pasted image 20230103192551.png]]

The agent always have a unique objective, altough for the algorithm it may vary. There's always only one objective. Usually the models start with no information of how to accomplish such objective.

In Reinforcement Learning this is accomplished with a set of **states**, **actions** and **rewards/punishments**. When moving between the states the objective is represented as the summatory of all the rewards.

![[Pasted image 20230103193041.png]]

This raises two main problems:
1. The Agent doesn't know the reward of next state until reaching it
2. Sometimes the agent doesn't even know the reward after reaching a different state. For example in chess every movement.

```ad-note
For this RL main purpose is to try to identify the next reward in a way it's always the best one.
```

## Environment
The environment space is the number of all combinations of all feature values. In environments with real values there are infinite states and it's called continuous variables. However in practice usually this is **discretize** using discretization to convert it in a finite set of states. There are two main types of environments.


![[Pasted image 20230103194232.png]]

### Deterministic environment
In deterministic environments it is possible to guess the outcome (reward and state) of the next stage and it is seen as a function with two inputs and two outputs. 
- Inputs
	- current state
	- action taken
- outputs
	- next state
	- reward

![[Pasted image 20230103193849.png]]

### Stochastic Environment
In stochastic enviroments it is impossible to guess the outcome exactly. In this case the state probability is calculated  to determine the possibility of getting a reward.
![[Pasted image 20230103193916.png]]


# Exploration and Exploitation
- **Exploration:** when the Agent starts off, it has to explore the environment states by picking actions randomly, so that it can reach a variety of states (or state-action pairs) and discover high-value trajectories.
- Exploitation: when it has enough information, it can pick actions more deliberately to visit known highvalue states or trajectories to maximize its rewards.

Basically use exploration(decide randomly) when it's the beggining to later obtain a solid base and changing to exploitation where we obtain the best case.

## $\epsilon$-greedy  policy
It combines both stochastic policies with a random policy which is used with a random uniform probability. 

It consists on starting with an $\epsilon$ high value from 0 to 1. The agent will choose a random policy based on the probability of $\epsilon$ and a deterministic way with a probability of $1-\epsilon$. $\epsilon$ should decrease during the learning process.
