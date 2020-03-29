#MDP element

one can identify four main subelements of a reinforcement learning system: a policy, a reward signal , a value function, and, optionally,a model of the environment.

A policy defines the learning agent’s way of behaving at a given time. Roughly speaking,a policy is a mapping from perceived states of the environment to actions to be taken when in those states.

A reward signal defines the goal of a reinforcement learning problem. On each time step, the environment sends to the reinforcement learning agent a single number called the reward.

A value function specifies what is good in the long run. Roughly speaking, the value of a state is the total amount of reward an agent can expect to accumulate over the future, starting from that state. Whereas rewards determine the immediate, intrinsic desirability of environmental states, values indicate the long-term desirability of states after taking into account the states that are likely to follow and the rewards available in those states.

Action choices are made based on value judgments. We seek actions that bring about states of highest value, not highest reward, because these actions obtain the greatest amount of reward for us over the long run. Unfortunately, it is much harder to determine values than it is to determine rewards.

A model of the environment. This is something that mimics the behavior of the environment, or more generally, that allows inferences to be made about how the environment will behave.

The artificial neural network provides the program with the ability to generalize from its experience, so that in new states it selects moves based on information saved from similar states faced in the past, as determined by its network. How well a reinforcement learning system can work in problems with such large state sets is intimately tied to how appropriately it can generalize from past experience.

A RL agent will have a:
1) Policy: is map from state to action. It's a function of the agent's action. For a Deterministic policy: a = π(s)
Stochastic policy: π(a|s) = P[At = a|St = s]

2) Value function: Value function is a prediction of future reward and is used to evaluate the goodness/badness of states
And therefore to select between actions, e.g. vπ(s) = Eπ [Rt+1 + γRt+2 + γ2Rt+3 + ... | St = s]

3) model: A model predicts what the environment will do next
P predicts the next state
R predicts the next (immediate) reward, e.g.
Pass0 = P[St+1 = s0| St = s, At = a]
Ras = E [Rt+1 | St = s, At = a

Bellman Equation:
Value of the current state = immeidiate reward + the value of the next state

v(s) = E [Gt| St = s]

     = E [Rt+1 + γRt+2 + γ2Rt+3 + ... | St = s]
     = E [Rt+1 + γ (Rt+2 + γRt+3 + ...) | St = s]
     = E [Rt+1 + γGt+1 | St = s]
     = E [Rt+1 + γv(St+1) | St = s]
