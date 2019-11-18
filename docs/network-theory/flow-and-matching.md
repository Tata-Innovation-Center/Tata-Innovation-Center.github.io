---
layout: default
title: Flow and matching
nav_order: 8
mathjax: true
parent: Network Theory
date: 2019-11-18 12:00:00
---

# Flow and matching

{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

--- 

### The Max-Flow Problem

A (s, t)-flow in a weighted graph G = (V, E, c), c is the weight, and where s is
a source and t is a sink, is a function $$f : E \rightarrow R $$ such that the following
conditions hold:

1. Conservation of flow: For every node $$v \neq s, t$$

$$
\sum_{u |(u, v) \in E} f(u, v)=\sum_{w |(v, w) \in E} f(v, w)
$$

That is, the sum of the flows over incoming edges is the same as the flow
over outgoing edges

2. Respecting Capacity contraints: For every edge $$e \in E, f(e) \leq c(e)$$

### Augmenting Path Algorithm
We can find the maximum flow in a weighted graph G using the Augmenting Path Algorithm:
1. Find a path P from s to t in the directed graph (assume all edges of
capacity 0 are removed).
2. “Push” as much flow as possible along this path.
3. Create a new “residual graph” $$G_{0}$$, constructed as follows:
    - For each edge $$e \in P$$ where flow was added, decrease its capacity by the same amount as the flow that was added.
    - In addition, for each edge $$e = (u, v) \in P$$ where flow was added, add the same amount of capacity that was removed from $$(u, v)$$ to a reverse edge $$(v, u)$$.
4. Reiterate this process on the new graph $$G^{\prime}$$, and continue until no further augmenting path $$P$$ can be found
5. The final maximum flow is obtained by summing up the flows picked in each iteration.

### Min-Cut 

An $$(s, t)$$-cut of a weighted graph $$G = (V, E, c)$$ is a partition
of V into two sets $$(S, T)$$ such that $$s \in S$$ and $$t \in T$$. The capacity of an
$$(s, t)$$-cut $$(S, T)$$ is the sum of the capacities of all the edges $$e = (u, v) \in E$$
such that $$u \in S$$ and $$v \in T$$ (i.e. all edges leaving S). An (s, t)-cut (S, T)
is said to be a min-$$(s, t)$$-cut in G if its capacity is smaller, or equal to, the
capacity of any other $$(s, t)$$-cut in G


### Theorem 1

Given a weighted graph $$G = (V, E, c)$$ and a source-sink pair
s, t, the Augmenting Path Algorithm outputs some max-$$(s, t)$$-flow in G. Furthermore,
1. The output flow is always integral;
2. The algorithm’s running time is polynomial in the size of G and the value of the max-$$(s, t)$$-flow.
3. The value of the max-$$(s, t)$$-flow in G is equal to the capacity of any min-$$(s, t)$$-cut in G

### Edge-Disjoint Paths

We say that two paths from s to t are edge-disjoint if they do not have any edges in
common. 

In any graph G, the number of edge-disjoint paths between a
source s and a sink t equals the max-$$(s, t)$$-flow in $$(G, c)$$ where $$c(e) = 1$$ for all
edges e. Additionally, there exists a algorithm that finds them whose running
time is polynomial in the number of such paths.


### Bipartite Graphs and Maximum Matchings

A bipartite graph is simply a graph where the nodes are divided into two types—“left nodes” X and “right nodes” Y and edges can only exist between a node of one type and a node of the other type. Formal definition:

A bipartite graph is a graph $$G = (V, E)$$ where $$V=X \cup Y$$
and $$(x, y) \in E$$ only if $$x \in X$$ and $$y \in Y$$ .