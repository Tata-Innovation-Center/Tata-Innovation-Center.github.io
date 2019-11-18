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

