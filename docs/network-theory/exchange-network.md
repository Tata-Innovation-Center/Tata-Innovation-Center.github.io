---
layout: default
title: Exchange Network
nav_order: 10
mathjax: true
parent: Network Theory
date: 2019-11-24 12:00:00
---

# Exchange Network

{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

--- 
 
### Definition of an Exchange Networks
An exchange network is a pair $$(G, v)$$, where $$G = (V, E)$$
is a graph and $$v : E \rightarrow N$$ is a function. An outcome of an exchange network
$$(G, v)$$ is a pair $$(M, a)$$ where:
1. M is a matching in G (i.e. a subset of E where no two edges share a
common endpoint.)
2. $$a : V \rightarrow N$$ is an allocation of values to nodes such that for every $$e =
(u, v) \in M$$, $$a(u) + a(v) = v(e)$$, and for every node v not part of an edge
in M, $$a(v) = 0$$.

### Stable Outcomes
Given an exchange network $$(G, v)$$, we call an outcome $$(M, a)$$
unstable if there exists a pair of nodes x, y in G such that $$(x, y) \notin M$$, but
$$a(x) + a(y) < v(x, y)$$  (i.e., the edge has a positive surplus). If $$(M, a)$$ is not
unstable, we call it stable.

### Claim 1
Let $$T = (n, Y, v)$$ be a matching market and let $$(G, v)$$ be the
exchange network corresponding to $$T$$. Or, conversely, let $$(G, v)$$ be an exchange
network where $$G = ([n ∪ Y ], E)$$ is bipartite, and let $$T$$ be the matching market
corresponding to it. Then $$(p, M)$$ is a market equilibrium in $$T$$ if and only if
$$(M, a)$$ is a stable outcome in $$(G, v)$$ where:

1. $$a(y) = p(y)$$ if $$y \in Y$$
2. $$a(i) = v_{i}(M(i)) − p(M(i))$$ if $$i \in [n]$$ and $$M(i) \neq \perp$$
3. $$a(i) = 0$$ otherwise


### Theorem 1
Any exchange network $$(G, v)$$ where $$G$$ is bipartite has a stable
outcome. Furthermore, such a stable outcome can be found in time polynomial
in the size of $$G$$ and the maximum value of any edge in the graph.

### Claim 2
There exists an exchange network with three nodes for which no
stable outcome can exist.

