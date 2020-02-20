---
layout: default
title: Variational Autoencoder
mathjax: true
parent: Advanced topics in machine learning
nav_order: 4
date: 2020-02-20 12:00:00
---

# Variational Autoencoder
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Latent variable models

There are a lot of latent variables for a image x of a person, for example, the gender, eye color, hair color, pose, etc. And the idea of latent variable models(LVM) is to explicitly model these factors using latent variables z. 

A latent variable model defines a probability distribution

$$
p(x, z)=p(x | z) p(z)
$$

Challenge: Very difficult to specify the conditional distribution or the distribution of latent variables by hand.

Key idea:

1. Assume latent variable is from a gaussian distribution, $$\mathbf{z} \sim \mathcal{N}(0, l)$$
2. And the conditional distribution is also some form of gaussian, $$p(\mathbf{x} | \mathbf{z})=\mathcal{N}\left(\mu_{\theta}(\mathbf{z}), \Sigma_{\theta}(\mathbf{z})\right)
$$ where $$\mu_{\theta},\Sigma_{\theta}$$ are neural networks

## Shallow mixture models

Mixture of Gaussians. 
1. $$
\mathbf{z} \sim \text { Categorical }(1, \cdots, K)
$$
2. $$
p(\mathbf{x} | \mathbf{z}=k)=\mathcal{N}\left(\mu_{k}, \Sigma_{k}\right)
$$

## Deep latent-variable models

### Representation: Variational autoencoder

### Learning: Variational inference