---
layout: page
title: Central Limit Theorem
usemathjax: true
tag: Probability
time: 2022/12/04
---

**Table of Content**
- [Theorem (central limit theorem)](#theorem-central-limit-theorem)
  - [Remark](#remark)
  - [De Moivre-Laplace Approximation to the Binomial](#de-moivre-laplace-approximation-to-the-binomial)


---

Let $$X_1, \cdots X_n$$ be **independent, identically distributed** r.v.s with finite mean $$\mu$$ and variance $$\sigma^2$$. 

Let $$S_n = X_1 + \cdots + X_n$$. Then mean of $$S_n$$ is $$\mu$$ and its variance is $$n\sigma^2$$. To standardize it, we let 

$$
Z_n = {S_n - n\mu \over \sqrt{n}\sigma},
$$

where

$$
E[Z_n]=0, var(Z_n) = 1.
$$

## Theorem (central limit theorem)
> Let $$Z\sim N(0, 1)$$. Then for every $$z$$, we have
>
> $$
> \lim_{n\to \infty}P(Z_n\le z) = P(Z\le z).
> $$

### Remark

- 把 $$Z_n$$ 當 $$N(0, 1)$$，把 $$S_n$$ 當 $$N(n\mu, n\sigma^2)$$。

- 對稱且 unimodal（單峰）的 $$X_i$$ 近似效果最好。
  - 像是 uniform 和 binomial。

### De Moivre-Laplace Approximation to the Binomial
> 待補。總之就是左右取 $${1\over 2}$$。