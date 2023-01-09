---
layout: page
title: The Poisson Process
usemathjax: true
tag: Probability, Statistics
time: 2022/01/04
---

**Table of Content**
- [Definition](#definition)
- [Time of the $$k$$-th arrival](#time-of-the-k-th-arrival)
- [Fresh Start Property](#fresh-start-property)
- [Properties](#properties)
  - [Sum of independent Poisson r.v.s](#sum-of-independent-poisson-rvs)
  - [Merging and Splitting](#merging-and-splitting)

---

## Definition

If an process is called a Poisson process, it has **small interval probabilities**, stated as: For small $$\delta$$, the probabilities $$P(k, \delta)$$ satisfy

$$
\begin{align*}
P(0, \delta) &\approx 1 - \lambda\delta,  \\
P(1, \delta) &\approx \lambda\delta, \\
P(k, \delta) &\approx 0, &\text{for } k=2, 3,\cdots,
\end{align*}
$$

where $$P(k, \delta)$$ is the prob. of $$k$$ arrivals in interval of duration $$\delta$$.

Let us approximate a Poisson process with a Bernoulli process. For a time interval $$\tau$$, divide it into $$n$$ *slots* such that each slot is of length $$\delta$$. Thus $$n = \tau / \delta$$. According to our definition, the prob. of an arrival within time $$\delta$$ is $$P(1, \delta) \approx \lambda\delta = p$$, where $$p$$ is the parameter of a Bernoulli r.v. We know that the expected number of arrivals in $$n$$ slots is $$np$$, which in our case is $$\lambda\tau$$. When $$n\to \infty$$ and $$\delta\to 0$$, $$np = \lambda\tau$$ remains constant. From [the discussion here](../2-discrete-rv/#poisson), we see that a **binomial PMF** ($$n$$ slots Bernoulli) **converges to a Poisson PMF**, here, with parameter $$\lambda\tau$$. To conclude, we have

$$
\begin{align*}
P(k, \tau) = e^{-\lambda\tau}{(\lambda\tau)^k\over k!},\ k\in \Bbb N.
\end{align*}
$$

Note that a Taylor series expansion of $$P(k, \tau)$$ exactly yields the **small interval probabilities**, with a negligible $$O(\tau^2)$$ term when $$\tau$$ is small.

> $$\lambda$$ 被稱為 arrival rate。

---

## Time of the $$k$$-th arrival

Let $$Y_k$$ be the r.v. of the $$k$$-th arrival. We have 

$$
\begin{align*}
f_{Y_k}(y)\delta &\approx P(y\le Y_k \le y+\delta) \\
&\approx P(k-1, y) \cdot \lambda\delta.
\end{align*}
$$

After cancelling $$\delta$$ from both sides, we have

$$
f_{Y_k}(y) = P(k-1, y)\lambda = {\lambda^ky^{k-1}e^{-\lambda y}\over (k-1)!}, 
$$

and this is called the **Erlang distribution** of order $$k$$.

---

## Fresh Start Property

Let $$T_k = Y_k - Y_{k-1}$$, which is the $$k$$-th inter-arrival time. Then $$T_1, T_2, \cdots$$ are **independent, identically distributed exponential r.v.s**, and $$Y_k = T_1+\cdots T_k$$. 

We can also define a Poisson process as a sum of i.i.d exponential r.v.s, which is equivalent to our former definition.

> 新定義？具體一點？

---

## Properties
### Sum of independent Poisson r.v.s

The sum of two independent Poisson r.v.s, with parameter $$\lambda$$ and $$\mu$$ respectively, is a Poisson r.v. with parameter $$\lambda + \mu$$.

> 從 convolution 或是 Poisson process（同一 process 切出兩獨立區間，並令 $$\lambda=1$$）來看都可以。

Since $$P(k, \tau) \sim \text{Poisson}(\lambda\tau)$$, the *concatenation* of two independent Poisson processes, with arrival rate $$\lambda_1, \lambda_2$$ and duration $$\tau_1, \tau_2$$, is 

$$
\text{Poisson}(\lambda_1\tau_1 + \lambda_2\tau_2).
$$

### Merging and Splitting

**Merge**: merged process: $$\text{Poisson}(\lambda_1+\lambda_2)$$

**Split**: resulting streams are $$\text{Poisson}(\lambda q)$$ and $$\text{Poisson}\lambda(1-q)$$.

> The two resulting streams are **independent**! Unlike those in the case of Bernoulli process.