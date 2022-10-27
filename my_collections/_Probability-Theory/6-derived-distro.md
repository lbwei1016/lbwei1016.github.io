---
layout: page
title: Derived Distribution
usemathjax: true
tag: Conditional Probability
time: 2022/10/26
---

**Table of Content**

---

## Discrete R.V. (monotonic)

Let $$X$$ be a discrete r.v. and $$Y = g(X)$$. If $$g$$ is **strictly monotonic**, we have $$h(y) = g^{-1}(y) = x$$. Thus

$$
p_Y(y) = P(y = g(x)) = P(x = h(y)) = p_X(h(y)).
$$

---

## Continuous R.V.
### The Linear Funcition of a Normal R.V.

Let $$X\sim N(\mu, \sigma^2)$$ and $$Y = aX+b$$. We have

$$
Y \sim N(aX+b, a^2\sigma^2).
$$

### General Version (monotonic)

Let $$X$$ be a continuos r.v. and $$Y = g(X)$$. If $$g$$ is **strictly monotonic**, we have $$h(y) = g^{-1}(y) = x$$. Moreover,

$$
f_Y(y) = f_X(h(y))\Bigg\vert {dh(y) \over y} \Bigg\vert.
$$

> 這個等式由 CDF 微分而來。（分成 mono. increasing 和 mono. decreasing 討論，因此有絕對值）

---

## The PDF of a function of Multiple R.V.s

Let $$X, Y$$ be independent continous r.v.s, and $$Z = g(X,Y)$$. We have

$$
F_Z(z) = P(g(X,Y) \le z).
$$

列出這個式子後，在平面上畫出 $$X$$ 和 $$Y$$ 有定義的區域，藉由算面積的方式來求 $$F_Z(z)$$！

> 詳見 [MIT OCW](https://ocw.mit.edu/courses/res-6-012-introduction-to-probability-spring-2018/resources/the-pdf-of-a-function-of-multiple-random-variables/)。

---

## Simulation

Generate sample $$X$$ with given CDF $$F_X(\cdot)$$.

> 已經知道 CDF 了，利用 uniform distribution $$u$$ 求出 $$g(u)$$ such that $$x = g(u)$$. 

> 為甚麼要這樣做？為了用 uniform distribution 表示其他 distribution？

---

## Reference
- [MIT OCW](https://ocw.mit.edu/courses/res-6-012-introduction-to-probability-spring-2018/pages/part-i-the-fundamentals/)