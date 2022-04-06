---
aliases: Markov decision process, MDP
---
Markov decision process (Puterman, 1994)
#### Markov decision process
Markov decision process described by a five-tuple $M = \langle \mathcal{S}, \mathcal{A}, P, R, γ\rangle:$ 
	- $\mathcal{S}$ is a possibly infinite set of states the environment can be in;
	- $\mathcal{A}$ is a possibly infinite set of actions the agent can take in a state;
	- $P(s'|s, a)$ gives the transition probability of the environment landing in a new state $s'$ after action $a$ is taken in state $s$;
	- $R(s, a)$ is the average reward immediately received by the agent after taking action $a$; and
	- $\gamma \in (0,1]$ is a discount factor.
The intersection can be recorded as a trajectory $(s_1, a_1, r_1,...)$, generated as follows: at step $t = 1, 2, . . .,$
	- The agent observes the environment’s current state $s_t ∈ S$, and takes an action $a_t ∈ A$;
	- The environment transitions to a next-state $s_{t+1}$, distributed according to the transition probabilities $P(·|s_t, a_t)$;
	- Associated with the transition is an immediate reward $r_t ∈ R,$ whose average is $R(s_t , a t ).$
Omitting the subscript, each step results in a tuple $(s, a, r, s' )$ that is called a transition. The goal of an RL agent is to maximize the long-term reward by taking optimal actions (to be defined soon). Its action-selection policy, denoted by $π$, can be deterministic or stochastic. In either case, we use $a ∼ π(s)$ to denote selection of action by following π in state s. Given a policy $π$, the value of a state $s$ is the average discounted long-term reward from that state:$$V^\pi(S) := \mathbb{E}[r_1 + \gamma r_2+ \gamma ^2r_3 + ...|s1 = s, a_i \sim \pi(s_i), \forall i \geqslant 1]$$
We are interested in optimizing the policy so that $V^π$ is maximized for all states. Denote by $π^∗$ an optimal policy, and $V^∗$ its corresponding value function (also known as the optimal value function). In many cases, it is more convenient to use another form of value function called the ![[Q-function#Q formular]]which measures the average discounted long-term reward by first selecting a in state s and then following policy $π$ thereafter. The optimal [[Q-function]], corresponding to an optimal policy, is denoted by $Q^∗$ .



