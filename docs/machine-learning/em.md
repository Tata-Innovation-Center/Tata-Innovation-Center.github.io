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
consider for example a probabilistic language model of news articles, Each article 
$$x$$ typically focuses on a specific topic $$t$$. e.g. finance, sports, politics. Using this prior knowledge, we may build a more accurate model. and topic $$t$$ here is an unobserved variable.

Since $$t$$ is unobserved, we cannot directly use the learning methods that we have so far. In fact, the unobserved variables make learning much more difficult.

## Gaussian mixture models

More formally, a latent variable model (LVM) $$p$$ is a probability distribution over two sets of variables 
$$x,z$$:

\begin{equation}
p(x, z ; \theta)
\end{equation}



