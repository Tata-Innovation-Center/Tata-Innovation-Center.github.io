---
layout: default
title: Mechanism Design and Auctions
nav_order: 11
mathjax: true
parent: Network Crowd and Market
date: 2019-11-24 12:00:00
---

# Mechanism Design and Auctions

{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

--- 
 
### The Mechanism Design Model

writing


### Single-item auction context

Consider the following setting:
1. We have a set of n buyers, and a single item for sale
2. The states $$\Omega=[n] \cup \perp$$ determine which of the n players will receive the
object (where $$\perp$$ represents no player winning).
3. Player i’s type $$t_{i} \in T_{i}=\mathbb{N}$$ describes i’s valuation of the object, and
$$v_{i}\left(t_{i}, \omega\right)=t_{i}$$ if $$\omega = i$$ (i.e., i gets the object) and 0 otherwise

We refer to a context $$\Gamma = (n, \Omega, T, V )$$ as above as a single-item auction
context.

### First-price auction mechanism 
The mechanism M run by the auctioneer,
upon receiving reports (i.e., bids) $$r_{i}$$ from each player i returns $$\mathcal{M}(\vec{r}) =\left(i^{*}, \vec{p}\right)$$ where
1. $$i^{*}=\arg \max _{i} r_{i}$$, (i.e. the winner is the player who reports (or “bids”)
the highest value
2. $$p_{i}=0$$ if $$i \neq i^{*}$$ (only the winner should pay for the item)
3. $$p_{i^{*}} =r_{i^{*}}$$ (the winner should pay the amount that they bid).


We can similarly define a second-price auction, where the winner is still the
highest bidder, but they instead need only pay the second-highest bid

$$
p_{i^{*}}=\max _{j \in[n] \backslash i^{*}} r_{j}
$$

### Goals of Mechanism Design

Writing

### DST and NT

Writting

### Claim 1
A mechanism M is DST if and only if it is NT.

### The VCG Mechanism
