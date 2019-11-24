---
layout: default
title: Matching Network
nav_order: 9
mathjax: true
parent: Network Theory
date: 2019-11-24 12:00:00
---

# Matching Network

{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

--- 

### Definition of a Matching Market
Given a set of players (buyers) $$X=[n]=\{1, \ldots, n\}$$ and a set of n items Y :
1. we associate with each player (buyer) $$i \in X$$, a valuation function $$v_{i}:Y \rightarrow N$$. For each $$y \in Y$$ , $$v_{i}(y)$$ determines i’s value for item y
2. we associate with each item $$y \in Y$$ , a price $$p(y) \in N$$
3. a buyer i who receives an item y gets utility
$$
v_{i}(y)-p(y)
$$
We would assume sellers get no utility.

### Another definition
We refer to the tuple $$T = (n, Y, v)$$ (as defined above) as a
matching market, and the tuple $$(T, p) = (n, Y, v, p)$$ as a priced matching
market.

### Induced acceptability graph 
Writting

### Induced preferred choice graph
Writting

### Market-clearing
Writting

### Social Optimality of Market Clearing
We can define the social value of an assignment in a matching market
$$T$$ as
$$
S V^{\Gamma}(\alpha)=\sum_{i \in[n], \alpha(i) \neq \perp} v_{i}(\alpha(i))
$$

Note the social value is different from sum of buyer’s utilities, as it considers
only the value the buyers get from the items,  but without considering the
prices they need to pay for them. 

And the social welfare can be written as:
$$
\begin{aligned} SW^{T}(\alpha, p)=\text { buyers' utilities }+\text { sellers' utilities } \\=\sum_{i \in[n], \alpha(i) \neq \perp} u_{i}(\alpha(i))+\sum_{i \in[n], \alpha(i) \neq \perp} p(\alpha(i)) \\=\sum_{i \in[n], \alpha(i) \neq \perp}\left(v_{i}(\alpha(i))-p(\alpha(i))\right)+\sum_{i \in[n], \alpha(i) \neq \perp} p(\alpha(i))  \\= \sum_{i \in[n], \alpha(i) \neq \perp} v_{i}(\alpha(i))=S V^{\Gamma}(\alpha)
\end{aligned}
$$