---
layout: default
title: Coordination in Social Networks
nav_order: 6
mathjax: true
parent: Network Crowd and Market
date: 2019-11-18 12:00:00
---

# Coordination in Social Networks

{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

### Plain Networked Coordination Games
1. If player's action “match”, i.e. they play the same strategy,they get the same positive utility $$Q(X, X) = x$$ or $$Q(Y, Y ) = y$$
2. If they “mismatch”, they get utility $$Q(X, Y ) = Q(Y, Y ) = 0$$

### The Adoption Threshold 

Consider a node v that has d neighbors (friends), a fraction p of whom choose X and the
remaining fraction $$(1 − p)$$ of whom choose Y . Then v’s utility for choosing X
is $$pdx$$ and its utility for choosing Y is $$(1−p)dy$$. What action should v take to
maximize its utility (i.e., to best respond to the actions of the other players)?

1. Choose X if $$pdx > (1 − p)dy$$.
2. choose either X or Y if $$pdx = (1 − p)dy$$ 
3. Choose Y otherwise.

### Social welfare or potential function of a Plain Networked Coordination Games

$$
\Phi^{\mathcal{G}}(\vec{a})=\mathrm{SW}^{\mathcal{G}}(\vec{a})=\sum_{i \in n} u_{i}(\vec{a}) =\sum_{(i, j) \in E} Q\left(a_{i}, a_{j}\right)
$$

### Theorem 1

$$\Phi^{\mathcal{G}}$$ is an ordinal potential function for any plain networked coordination game G.


### Theorem 2

BRD converges in every plain networked coordination game.

### Incorporating Intrinsic Values

Now we can consider case where each player's action has its own intrinsic value and the utility now is:

$$
u_{i}(\vec{a})=R_{i}\left(a_{i}\right)+\sum_{j \in N(i)} Q\left(a_{i}, a_{j}\right)
$$

where  $$R_{i}(a_{i})$$ denotes the intrinsic value of $$a_{i}$$ to player i

### Theorem 3

BRD converges in every Networked Coordination Game

### Price of Stability

How bad can the “gap” between the social welfare in the best equilibrium and in the sociallyoptimal outcome be? We denote the maximum social welfare (MSW) by 

$$
M S W^{\mathcal{G}}=\max _{\vec{a} \in A} S W^{\mathcal{G}}(\vec{a})
$$

The Price of Stability in a game G with non-negative
utilities is defined as

$$
\frac{M S W^{\mathcal{G}}}{\max _{\vec{a} \in P N E^{\mathcal{G}}} S W^{\mathcal{G}(\vec{a})}}
$$

where $$PNE_{G}$$ denotes the set of PNE in G.


### Theorem 4
In every Networked Coordination Game G, there exists a PNE $$\vec{a}^{\prime}$$
such that

$$
S W^{\mathcal{G}}\left(\vec{a}^{\prime}\right) \geq \frac{1}{2} M S W^{\mathcal{G}}
$$

In other words, the Price of Stability in G is at most 2.

### Theorem 5
For every $$n \in N$$, $$\epsilon > 0$$, there exists some n-player Networked
Coordination Game G such that for every PNE $$\vec{a}^{\prime}$$ in G we have that

$$
S W^{\mathcal{G}}\left(\vec{a}^{\prime}\right) \leq\left(\frac{1}{2}+\epsilon\right) M S W^{\mathcal{G}}
$$

In other words, the Price of Stability can be arbitrarily close to 2.