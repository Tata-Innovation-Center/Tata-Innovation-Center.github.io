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
for example, your blood pressure, your blood sugar and glucose and are variable that can be meassured, however, your overall health condition, is unobservable in some sense.

More formally, a latent variable model (LVM) $$p$$ is a probability distribution over two sets of variables 
$$x,z$$:

$$
p(x, z ; \theta)
$$

where the $$x$$ variables are observed at learning time in a dataset $$D$$ and the $$z$$ are never observed.

There are two reasons why we might want to use latent variable models.

The simplest reason is that some data might be naturally unobserved. For example, if we are modeling a clinical trial, then some patients may drop out, and we won’t have their measurements.

However, the most important reason for studying LVMs is that they enable us to leverage our prior knowledge when defining a model. 

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

is a multivariate Gaussian with mean and variance $$\mu_{k}$$, $$\Sigma_{k}$$

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

## The Expectation-Maximization algorithm in the context of GMM

So how do we train a LVM? we should be maximizing the marginal log-likelihood of the data which can be written as:

$$
\log p(D)=\sum_{x \in D} \log p(x)=\sum_{x \in D} \log \left(\sum_{z} p(x | z) p(z)\right)
$$

Here, $$p(x)$$ is very easy to optimize if the distribution of $$x$$ can be written in some exponetial form, however, when we introduced latent variable $$z$$ here, the optimization of the right half of this equation became very hard and it non-convex.

So how do we do the optimization, we will resort to EM algorithm.


We can formally define the EM algorithm as follows. Let $$D$$ be our dataset.

- Starting at an initial $$\theta_{0}$$, repeat until convergence for $$t = 1,2,...$$

- E-step: For each $$x\in D$$,compute the posterior $$p\left(z|x;\theta_{t}\right)$$

- M-step: Compute new weights via

$$
\theta_{t+1}=\arg \max _{\theta} \sum_{x \in D} \mathbb{E}_{z \sim p\left(z | ; ; \theta_{t}\right)} \log p(x, z ; \theta)
$$

 In the context of GMMs, Suppose we have a dataset $$D$$
. In the E-step, we may compute the posterior for each data point $$x$$
 as follows:

 $$
p\left(z | x ; \theta_{t}\right)=\frac{p\left(z, x ; \theta_{t}\right)}{p\left(x ; \theta_{t}\right)}=\frac{p\left(x | z ; \theta_{t}\right) p\left(z ; \theta_{t}\right)}{\sum_{k=1}^{K} p\left(x | z_{k} ; \theta_{t}\right) p\left(z_{k} ; \theta_{t}\right)}
$$

Note that each $$
p\left(x | z_{k} ; \theta_{t}\right) p\left(z_{k} ; \theta_{t}\right)
$$ is simply the probability that $$x$$ originates from component $$k$$ given the current set of parameters 
$$\theta$$. After normalization, these form the $$K$$-dimensional vector of probabilities $$
p\left(z | x ; \theta_{t}\right)
$$.

At the M-step, we optimize the expected log-likelihood of our model.


$$
\begin{aligned} \theta_{t+1} &=\arg \max _{\theta} \sum_{x \in D} \mathbb{E}_{z \sim p\left(z | x ; \theta_{t}\right)} \log p(x, z ; \theta) \\ &=\arg \max _{\theta} \sum_{k=1}^{K} \sum_{x \in D} p\left(z_{k} | x ; \theta_{t}\right) \log p\left(x | z_{k} ; \theta\right)+\sum_{k=1}^{K} \sum_{x \in D} p\left(z_{k} | x ; \theta_{t}\right) \log p\left(z_{k} ; \theta\right) \end{aligned}
$$

We can optimize each of these terms separately. We will start with $$p\left(x|z_{k};\theta\right)=\mathcal{N}\left(x;\mu_{k},\Sigma_{k}\right)
$$ We have to find 

$$
\sum_{x \in D} p\left(z_{k} | x ; \theta_{t}\right) \log p\left(x | z_{k} ; \theta\right)=c_{k} \cdot \mathbb{E}_{x \sim Q_{k}(x)} \log p\left(x | z_{k} ; \theta\right)
$$
where $$c_{k}=\sum_{x\in D} p\left(z_{k}|x;\theta_{t}\right)$$ is a constant that does not depend on $$\theta$$ and $$Q_{k}(x)$$ is a probability distribution defined over $$D$$ as

$$
Q_{k}(x)=\frac{p\left(z_{k} | x ; \theta_{t}\right)}{\sum_{x \in D} p\left(z_{k} | x ; \theta_{t}\right)}
$$

Now we know that $$
\mathbb{E}_{x \sim Q_{k}(x)} \log p\left(x | z_{k} ; \theta\right)
$$ is optimized when $$
p\left(x | z_{k} ; \theta\right)
$$ equals $$Q_{k}(x)$$
this objective equals the KL divergence between $$Q_{k}$$ and $$P$$, plus a constant. Thus, we may set the mean and variance $$
\mu_{k}, \Sigma_{k}
$$ to those of $$Q_{k}$$, which are

$$
\mu_{k}=\mu_{Q_{k}}=\sum_{x \in D} \frac{p\left(z_{k} | x ; \theta_{t}\right)}{\sum_{x \in D} p\left(z_{k} | x ; \theta_{t}\right)} x
$$

and  

$$
\Sigma_{k}=\Sigma_{Q_{k}}=\sum_{x \in D} \frac{p\left(z_{k} | x ; \theta_{t}\right)}{\sum_{x \in D} p\left(z_{k} | x ; \theta_{t}\right)}\left(x-\mu_{Q_{k}}\right)\left(x-\mu_{Q_{k}}\right)^{T}
$$

Note how these are the just the mean and variance of the data, weighted by their cluster affinities! Similarly, we may find out that the class priors are

$$
\pi_{k}=\frac{1}{|D|} \sum_{x \in D} p\left(z_{k} | x ; \theta_{t}\right)
$$




## EM in a general context.


## Proof of convergence





