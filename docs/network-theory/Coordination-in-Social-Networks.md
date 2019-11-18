---
layout: default
title: Coordination in Social Networks
nav_order: 6
mathjax: true
parent: Network Theory
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
2. Choose Y if $$pdx < (1 − p)dy$$.
3. choose either X or Y if $$pdx = (1 − p)dy$$ 

### Social welfare or potential function of a Plain Networked Coordination Games

$$
\Phi^{\mathcal{G}}(\vec{a})=\mathrm{SW}^{\mathcal{G}}(\vec{a})=\sum_{i \in n} u_{i}(\vec{a}) =\sum_{(i, j) \in E} Q\left(a_{i}, a_{j}\right)

$$
