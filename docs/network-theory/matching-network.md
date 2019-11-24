---
layout: default
title: Matching Market
nav_order: 9
mathjax: true
parent: Network Theory
date: 2019-11-24 12:00:00
---

# Matching Market

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
SW^{T}(\alpha, p)=\text { buyers' utilities }+\text { sellers' utilities }
$$

### claim 1
For all $$\alpha$$, p, $$SW^{T}(\alpha, p) = SV^{T}(\alpha)$$.

We say that an assignment α maximizes social value if $$SV^{T}(\alpha) = \max _{\alpha^{\prime}} SV^{T}(\alpha^{\prime})$$ Similarly, an assignment α and and price function p maximize social welfare if $$SW^{T}(\alpha) = \max _{\alpha^{\prime},p^{\prime}} SV^{T}(\alpha^{\prime}, p^{\prime})$$

### Corollary 2
For any matching market $$T = (n, Y, v)$$, an assignment $$\alpha$$
maximizes social value if and only if $$(\alpha, p)$$ maximize social welfare for any
(or every) p.

Thus, if we have an outcome that maximizes social value, then social
welfare will be maximized regardless of how we set prices.


### Theorem 1
(Social optimality of market equilibria.). Given a matching
market $$T$$ and a market equilibrium $$(p, M)$$ for $$T$$, we have that $$\alpha m$$ (i.e., the
assignment corresponding to the matching M) maximizes social value.

### Theorem 2
A market equilibrium $$(p, M)$$ exists in every matching market
$$T$$. Additionally, there exists an efficient procedure which finds this equilibrium
in time polynomial in the maximum valuation $$V$$ that any buyer has for some
item

### Bundles of Identical Goods
In writing