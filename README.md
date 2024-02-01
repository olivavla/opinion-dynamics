# Brief ntroduction to opinion dynamics mathematical model

## Opinion dynamics mathematical model with bounded confidence in noisy environment

In a community, opinions evolve due to affinities and conflicts between mutually interacting individuals. These interactions lead to collective states, where either a majority of individuals adopt a similar opinion (consensus) or a number of opinion groups (clusters) arise. In many situations, the dynamics of this complex collective behaviour goes beyond specific individual attributes and seems to be well characterised by quantities like statistical distributions and averages. In the context of continuous opinion dynamics a model introduced by Hegselmann and Krause is a representation of a model with bounded confidence. In this model individuals trust only their neighbours and over the time change opinions according to an arithmetic mean formula but only from a set of neighbours. Let $n$ be a number of agents in a group under consideration.

$$x_i(t+1)=\frac{1}{|\mathcal{N}_i(t)|}\sum\limits_{j\in\mathcal{N}_i(t)}x_j(t),$$


where $x_i(t)$ is the opinion value of agent $i$ at time $t$,

$\mathcal{N}_i(t)$ is the neighbour set of agent $i$ at time $t$:

$$\mathcal{N}_i(t)=\{j:|x_j(t)-x_i(t)|\leq\epsilon\}, \epsilon\in (0, 1],$$

where $\epsilon$ is the confidence threshold (interaction radius).


After some transient evolution, this leads to final states in which either full consensus is reached or the population splits in a finite number of clusters such that all individuals in one cluster share the same opinion. However, there is a belief that existing method is not efficient enough to describe opinion dynamics close to real life; such dynamics misses the fact that the behavior of an individual in a society does not depend only on the influence of people with similar opinions. There are many additional
factors, both personal and external, which also cause opinion changes. These factors may introduce some degree of discrepancy with reality and should be modelled. Therefore, modifications of the Hegselmann-Krause model were proposed in which agents are allowed to sharply change their opinion with some probability (random jumps) and to alter their opinions because of external influence (additional noise). 

Agents' opinions in a model with bounded confidence with random jumps are changing according to a formula:

$$x_i(t+1) = \begin{cases}
\xi_i(t)\sim U(\frac{1}{2}, 1), &\text{if } \eta_i(t)=1\\
\dfrac{1}{|\mathcal{N}_i(t)|}\sum\limits_{j\in\mathcal{N}_i(t)}x_j(t) , &\text{if } \eta_i(t)=0
\end{cases}$$

where $\eta_i(t)$ are independent random variables with Bernoulli distribution

$$\eta_i(t)= \begin{cases}
    1, \text{with probability } \mu\\
    0, \text{with probability } 1-\mu
\end{cases}$$


One possible interpretation of random jumps modification is that individuals are likely to listen to the opinion of the leader. Thus, agents change their opinions dramatically. The interval of values $(\frac{1}{2}, 1)$ is interpreted as a positive decision, therefore, it is in the interests of the observer to get as many agents with values greater than $\frac{1}{2}$ as possible. It will be studied how quickly all individuals' opinions will reach the absorbing set, what will be the probability distribution for the vector of opinions, with the help of which the assessment of the impact of external influence will be received.

In terms of model with bounded confidence with additive noise, the opinion dynamic is represented as follows:

$$x_i(t+1) = \frac{\alpha}{|\mathcal{N}_i(t)|}\sum\limits_{j\in\mathcal{N}_i(t)} x_j(t)+(1-\alpha)\xi_i(t)$$

where $\alpha\in (0, 1)$ is the noise parameter,

$\xi_i(t)\sim U \left(\frac{1}{2}, 1\right)$ are independent and identically distributed random variables on the interval $\left(\frac{1}{2}, 1\right)$.

Here, external influence added to a Hegselmann-Krause model with a coefficient can be interpreted as advertisement, social networks, social interactions and others. Next, for this model the probability distribution for the opinion profile will be studied.

In both models, with random jumps and with additive noise, the vector of opinions at time $t$ is a stochastic process with a discrete time and a continuous set of states. In finite time these processes will reach an absorbing set.

## Repository

This repository includes simulation models of agent interaction algorithms above. Also it consists of the asymptotic analysis of these models.
