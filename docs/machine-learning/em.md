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

There are two reasons why we might want to use latent variable models.

The simplest reason is that some data might be naturally unobserved. For example, if we are modeling a clinical trial, then some patients may drop out, and we won’t have their measurements. The methods in this chapter can be used to learn with this kind of missing data.

However, the most important reason for studying LVMs is that they enable us to leverage our prior knowledge when defining a model. Our topic modeling example from the introduction illustrates this. We know that our set of news articles is actually a mixture of $$K$$
distinct distributions (one for each topic); LVMs allow us to design a model that captures this.

LVMs can also be viewed as increasing the expressive power of our model. In the case of GMMs (In the following section), the distribution that we can model using a mixture of Gaussian components is much more expressive than what we could have modeled using a single component.


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

This model postulates that our observed data is comprised of $$K$$ clusters with proportions specified by
$$ \pi_{1},..., \pi_{K}$$; the distribution within each cluster is a Gaussian. We can see that $$p(x)$$
is a mixture by explicitly writing out this probability

$$
p(x)=\sum_{k=1}^{K} p(x | z=k) p(z=k)=\sum_{k=1}^{K} \pi_{k} \mathcal{N}\left(x ; \mu_{k}, \Sigma_{k}\right)
$$

To generate a new data point, we sample a cluster $$k$$ and then sample its Gaussian $$\mathcal{N}\left(x ; \mu_{k}, \Sigma_{k}\right)$$. 

<div class="imgcap">
<img src="https://user-images.githubusercontent.com/22668421/68343354-94e25780-00ba-11ea-9850-7e4532df42c2.png" style="border:none;width:100%">
</div>

## The Expectation-Maximization algorithm

So how do we train a LVM? we should be maximizing the marginal log-likelihood of the data which can be written as:

