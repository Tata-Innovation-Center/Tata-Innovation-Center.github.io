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

Let $$Z$$ be a uniform random vector in $$[0, 1]^n$$ and $$X = AZ$$ for a square invertible matrix $$A$$, with inverse $$W = A^{-1}$$.

Geometrically, the matrix A maps the unit hypercube $$[0, 1]^n$$ to a parallelotope

<div class="imgcap">
<img src="https://user-images.githubusercontent.com/22668421/74756128-19a84a00-5242-11ea-92c2-74907e050f7c.png" style="border:none;width:100%">
</div>

The volume of the parallelotope is equal to the determinant of the
transformation $$A$$


$$
\operatorname{det}(A)=\operatorname{det}\left(\begin{array}{cc}{a} & {c} \\ {b} & {d}\end{array}\right)=a d-b c
$$

$$X$$ is uniformly distributed over the parallelotope. Hence, we have


$$
\begin{aligned} p_{X}(\mathbf{x}) &=p_{Z}\left(W_{\mathbf{X}}\right)|\operatorname{det}(W)| \\ &=p_{Z}(W \mathbf{x}) /|\operatorname{det}(A)| \end{aligned}
$$



