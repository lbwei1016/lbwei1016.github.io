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

---

## Definition

If an process is called a Poisson process, it has **small interval probabilities**, stated as: The probabilities $$P(k, \tau)$$ satisfy

$$
\begin{align*}
P(0, \tau) &\approx 1 - \lambda\tau,  \\
P(1, \tau) &\approx \lambda\tau, \\
P(k, \tau) &\approx 0, &\text{for } k=2, 3,\cdots,
\end{align*}
$$

where $$P(k, \tau)$$ is the prob. of $$k$$ arrivals in interval of duration $$\tau$$.

Let us approximate a Poisson process with a Bernoulli process. For a time interval $$\tau$$, divide it into $$n$$ *slots* such that each slot is of length $$\delta$$. Thus $$n = \tau / \delta$$. According to our definition, the prob. of an arrival within time $$\delta$$ is $$P(1, \delta) \approx \lambda\delta = p$$, where $$p$$ is the parameter of a Bernoulli r.v. We know that the expected number of arrivals in $$n$$ slots is $$np$$, which in our case is $$\lambda\tau$$. When $$n\to \infty$$ and $$\delta\to 0$$, $$np = \lambda\tau$$ remains constant. From [the discussion here](../2-discrete-rv/#poisson), we see that a **binomial PMF** ($$n$$ slots Bernoulli) **converges to a Poisson PMF**, here, with parameter $$\lambda\tau$$. To conclude, we have

$$
\begin{align*}
P(k, \tau) = e^{-\lambda\tau}{(\lambda\tau)^k\over k!},\ k\in \Bbb N.
\end{align*}
$$

Note that a Taylor series expansion of $$P(k, \tau)$$ exactly yields the **small interval probabilities**, with a negligible $$O(\tau^2)$$ term.

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