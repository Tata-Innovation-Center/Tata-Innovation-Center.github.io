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
2. $$a : V \rightarrow N$ is an allocation of values to nodes such that for every $$e =
(u, v) \in M$$, $$a(u) + a(v) = v(e)$$, and for every node v not part of an edge
in M, $$a(v) = 0$$.

### Stable Outcomes
Given an exchange network $$(G, v)$$, we call an outcome $$(M, a)$$
unstable if there exists a pair of nodes x, y in G such that $$(x, y) \notin M$$, but
$$a(x) + a(y) < v(x, y)$$  (i.e., the edge has a positive surplus). If $$(M, a)$$ is not
unstable, we call it stable.