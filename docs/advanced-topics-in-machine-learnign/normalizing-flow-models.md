---
layout: default
title: Normalizing Flow Models
mathjax: true
parent: Advanced topics in machine learning
nav_order: 4
date: 2020-02-18 12:00:00
---

# Normalizing Flow
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Intuitions

## Change of Variables fomula

### 1D example
If $$X= 4Z$$ and $$z \sim \mathcal{U}[0,2]$$, what is $$p_{x}(4)$$? 

X is uniform in [0, 8], so $$p_{X}(4) = 1/8$$.

We have the following formula when we apply a transform function over random variables,

If $$X = f (Z)$$, $$f(\cdot)$$ is monotone with inverse, $$Z=f^{-1}(X)=h(X)$$,  then:

$$
p_{X}(x)=p_{Z}(h(x))\left|h^{\prime}(x)\right|
$$

For the 1d example, we have 
$$
p_{X}(4)=p_{Z}(1) h^{\prime}(4)=1 / 2 \times 1 / 4=1 / 8
$$

### Geometry: Determinants and volumes(2D case)

