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
2. And the conditional distribution is also in some form of gaussian, $$p(\mathbf{x} | \mathbf{z})=\mathcal{N}\left(\mu_{\theta}(\mathbf{z}), \Sigma_{\theta}(\mathbf{z})\right)
$$ where $$\mu_{\theta},\Sigma_{\theta}$$ are neural networks

## Shallow mixture models

Mixture of Gaussians. 
1. $$
\mathbf{z} \sim \text { Categorical }(1, \cdots, K)
$$
2. $$
p(\mathbf{x} | \mathbf{z}=k)=\mathcal{N}\left(\mu_{k}, \Sigma_{k}\right)
$$

Generative process: 
1. Pick a mixture component k by sampling z
2. Generate a data point by sampling from that Gaussian

The likelihood is non-convex: this increases representational power, but
makes inference more challenging

$$
p(\mathbf{x})=\sum_{\mathbf{z}} p(\mathbf{x}, \mathbf{z})=\sum_{\mathbf{z}} p(\mathbf{z}) p(\mathbf{x} | \mathbf{z})=\sum_{k=1}^{k} p(\mathbf{z}=k) \underbrace{\mathcal{N}\left(\mathbf{x} ; \mu_{k}, \Sigma_{k}\right)}_{\text {component }}
$$

## Deep latent-variable models
Key idea: A mixture of an infinite number of Gaussians 
1. $$\mathbf{z} \sim \mathcal{N}(0, l)$$ (From discrete to continuous)
2. $$p(\mathbf{x} | \mathbf{z})=\mathcal{N}\left(\mu_{\theta}(\mathbf{z}), \Sigma_{\theta}(\mathbf{z})\right)
$$ where $$\mu_{\theta}, \Sigma_{\theta}$$ are neural networks. 

$$
\mu_{\theta}(\mathbf{z})=\sigma(A \mathbf{z}+c)=\left(\sigma\left(a_{1} \mathbf{z}+c_{1}\right), \sigma\left(a_{2} \mathbf{z}+c_{2}\right)\right)=\left(\mu_{1}(\mathbf{z}), \mu_{2}(\mathbf{z})\right)
$$

$$
\left.\Sigma_{\theta}(\mathbf{z})=\operatorname{diag}(\exp (\sigma(B \mathbf{z}+d)))\right)=\left(\begin{array}{cc}{\exp \left(\sigma\left(b_{1} z+d_{1}\right)\right)} & {0} \\ {0} & {\exp \left(\sigma_{\left.2 z+d_{2}\right)}\right)}\end{array}\right)
$$

$$
\theta=(A, B, c, d)
$$

3. Even though $$p(\mathbf{x} | \mathbf{z})$$ is simple, the marginal $$p(x)$$ is very complex/flexible

### Representation: Variational autoencoder

### Learning: Variational inference

## Learning deep latent variable generative models