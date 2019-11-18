---
layout: default
title: Analyzing Best-Response
Dynamics
nav_order: 3
mathjax: true
has_children: true
permalink: /docs/network-theory
date: 2019-11-17 12:00:00
---

# Analyzing Best-Response Dynamics

{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

### BRD and PNE in graph
1. The BRD process can be interpreted as simply starting at any node $$\vec{u}$$
in G and then picking any outgoing edge, traversing it to reach a new
node $$\vec{u}^{\prime}$$, picking any outgoing edge from it and so on. That is, we take
a walk from any node in the graph. Each node on this graph will be an action profile.

2. BRD converges in G if and only if there are no cycles in G—that is, G is
a DAG. This means that we eventually reach a node that does not have
any outgoing edges and thus the path ends.

3. a is a PNE if and only if $$\vec{a}$$ is a, so-called, sink in the
graph G—that is, a node without any outgoing edges. If a node is a
sink in G, nobody can improve their utility by best responding.

### Potential function
we define a potential (or “energy”) function $$\Phi: A \rightarrow \mathbb{Z}$$, which maps outcome profiles to integers(denoting the “energy level”). A particularly natural potential function (which
we will use later) is the utilitarian social welfare, or simply social welfare
(SW), defined as the sum of all players’ utilities:

$$
\Phi(a)=\mathrm{SW}(a)=\sum_{i \in n} u_{i}(a)
$$


### Ordinal potential function
Roughly speaking, a potential function is said to be ordinal if any profitable single-player
deviation increases the potential. 
$$\Phi: A \rightarrow \mathbb{Z}$$ for a game $$G = (n, A, u)$$ if, for every action profile
$$a \in A$$, every player i, and every action $$a_{i}^{\prime} \in A_{i}$$, if

$$
u_{i}\left(a_{i}^{\prime}, a_{-i}\right)>u_{i}\left(a_{i}, a_{-i}\right)
$$

then

$$
\Phi\left(a_{i}^{\prime}, a_{-i}\right)>\Phi\left(a_{i}, a_{-i}\right)
$$

### Weakly ordinal potential function
The above condition change to :

$$a_{i} \notin B R_{i}(\vec{a})$$  but $$ a_{i}^{\prime} \in B R_{i}(\vec{a})$$

