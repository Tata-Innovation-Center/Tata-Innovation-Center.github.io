---
layout: default
title: Contagion in Social Networks
nav_order: 7
mathjax: true
parent: Network Theory
date: 2019-11-18 12:00:00
---

# Contagion in Social Networks

{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

### Cascade

Given a plain networked coordination game G induced by a graph $$G = (V, E)$$ and coordination utility Q, we say that a set $$S \subseteq V$$ is cascading with respect to G if the following process always ends with all
nodes in V choosing X.
1. Start off with an outcome $$\vec{a} = (X_{S}, Y_{−S})$$, where every node in S chooses X, and all other nodes chooses Y
2. Run BRD from $$\vec{a}$$ but where the process is restricted to only nodes in $$V \backslash S$$ best responding (i.e., nodes in S never change from X, but the others may change strategies by best responding).

### Density

Given an undirected graph $$G = (V, E)$$ and a set of nodes
$$S \subseteq V$$ , we say that S has density t if for every node $$v \in S$$, the fraction of
v’s neighbors that are inside S is at least t; that is, for all $$v \in S$$,

$$
\frac{|N(v) \cap S|}{|N(v)|} \geq t
$$

### Theorem 1
Given a plain networked coordination game G induced by $$G =(V, E)$$, with adoption threshold t, a set S is cascading w.r.t. G if and only if there does not exist a set of nodes $$T \subseteq V \backlash S$$ having density 1 − t 


### The Computational Complexity of Finding the Small Cascading Sets

NP-hard

### Strong cascade

The notion of a cascading set assumes that the original set S of “early adopters”
never changes actions—i.e. they do not participate in the BRD. We can consider an even stronger notion of cascading where the early adopters only need to start off playing X

