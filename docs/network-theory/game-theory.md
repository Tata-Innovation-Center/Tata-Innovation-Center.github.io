---
layout: default
title: Game Theory
mathjax: true
parent: Network Theory
nav_order: 2
date: 2019-11-17 12:00:00
---

# Game Theory
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

### Utility functions 

$$u_{i}(a_{1},a_{2})$$ denotes the utility player i get when player 1 playing $$a_{1}$$ and player 2 playing $$a_{2}$$

### Normal-form games
1. Players act only once;
2. Players act simultaneously
3. The number of players and the set of actions is finite

### Action Space

$$A = A_{1} × A_{2} × . . . × A_{n}$$ is a product of finite sets; we refer to $$A_{i}$$ as
the action space of player i, and refer to the product space, A, as the
outcome space.

### Action profile
We refer to a tuple $$\vec{a}=\left(a_{1}, \ldots, a_{n}\right) \in A$$ of actions as an action profile,
or outcome. As players act only once, each element indicate what each of them play at one step.
We will use $$(a_{i}, a_{−i})$$ to describe the full action profile where player i
plays $$a_{i}$$ and everyone else $$a_{−i}$$.

### Dominant Strategy
A dominant strategy for a player i in a game $$(n, A, u)$$ is
an action $$a_{i}$$ such that, for all $$a_{i}^{\prime} \in A_{i} \backslash a_{i}$$ and all action profiles $$a_{-i} \in A_{-i}$$ we have

$$
u_{i}\left(a_{i}, a_{-i}\right) \geq u_{i}\left(a_{i}^{\prime}, a_{-i}\right)
$$

### Dominated Strategy

we say that $$a_{i} \in A_{i}$$ is strictly dominated by $$a_{i}^{\prime}$$
for a player i, if for any action profile $$a_{-i} \in A_{-i}$$
, we have

$$
u_{i}\left(a_{i}, a_{-i}\right)<u_{i}\left(a_{i}^{\prime}, a_{-i}\right)
$$
