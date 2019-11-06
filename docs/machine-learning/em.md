---
layout: default
title: EM Algorithm and latent variable models
parent: Machine Learning
mathjax: true
nav_order: 5
date: 2019-11-04 12:00:00
---

# EM Algorithm and latent variable models
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Latent variable models

In our world, there are variables that can be observed and there are also variables that are unobservable.
for example consider a probabilistic language model of news articles, Each article 
$$x$$ typically focuses on a specific topic $$t$$. e.g. finance, sports, politics. Using this prior knowledge, we may build a more accurate model. and topic $$t$$ here is an unobserved variable because at this point we have no idea what topic it is.

Since $$t$$ is unobserved, we cannot directly use the learning methods that we have so far. In fact, the unobserved variables make learning much more difficult.



More formally, a latent variable model (LVM) $$p$$ is a probability distribution over two sets of variables 
$$x,z$$:

$$
p(x, z ; \theta)
$$

where the $$x$$ variables are observed at learning time in a dataset $$D$$ and the $$z$$ are never observed.


## Gaussian mixture models

Gaussian mixture models (GMMs) are a good example of latent variable model.

In a GMM, each data point is a tuple $$(x_{i},z_{i})$$ with $$x_{i} \in \mathbb{R}^{d}$$ and $$
z_{i} \in\{1,2, \ldots, K\}$$, The joint probability is:

$$
p(x, z)=p(x | z) p(z)
$$

where $$p(z=k) = \pi_{k}$$ for some vector of class probabilities$$\pi \in \Delta_{K-1}$$ and 

$$
p(x | z=k)=\mathcal{N}\left(x ; \mu_{k}, \Sigma_{k}\right)
$$

is a multivariate Gaussian with mean and variance $$\mu_{k}$$, $\Sigma_{k}$