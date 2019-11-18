---
layout: default
title: Traffic Network Games
nav_order: 8
mathjax: true
parent: Network Theory
date: 2019-11-18 12:00:00
---

# Traffic Network Games

{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

--- 

###  Definition of a Traffic Network Game
A traffic network game G on a directed graph $$G = (V, E)$$ is specified as
follows:
1. We associate with each edge $$e \in E$$, a travel time function $$T_{e}(·)$$, which
determines the travel time $$T_{e}(x)$$ on the “road” e if x players are traveling on it
2. We assume the travel time is linear: $$T_{e}(x) = \alpha_{e}x+\beta_{e}$$, where $$\alpha_{e}$$, $$\beta_{e}$$ ≥ 0.
(So, the more people are traveling on an edge, the longer it should take.)

3. We specify a source $$s \in V$$ and a target $$t \in V$$ ; the goal of all players is
to travel from s to t. The action set for each player is the set of paths p from s to t.


