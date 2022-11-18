---
layout: page
title: Covariance & Correlation Coefficient
usemathjax: true
tag: Probability
time: 2022/11/02
---

**Table of Content**
- [Covariance](#covariance)
  - [Definition](#definition)
  - [Properties](#properties)
    - [The variance of a sum of r.v.s](#the-variance-of-a-sum-of-rvs)
- [Correlation Coefficient](#correlation-coefficient)
  - [Definition](#definition-1)
  - [Theorem: $$\vert \rho \vert \le 1$$](#theorem-vert-rho-vert-le-1)
  - [Interpretation](#interpretation)
- [Reference](#reference)

---

## Covariance
### Definition
> $$cov(X,Y) = E\Big[(X-E[X]) \cdot (Y-E[Y]) \Big]$$.

兩 r.v. 偏移各自平均的乘積期望值。若 covariance 為正，則 $$X$$ 和 $$Y$$ 呈正相關，反之則為負。

值得注意，covariance 的單位是 $$X$$ 的單位乘以 $$Y$$ 的單位。 

### Properties

$$
\begin{align*}
  cov(X,Y) &= E[XY] - E[X]E[Y], \tag{1} \\
  cov(X,X) &= var(X), \tag{2} \\
  cov(aX+b, Y) &= a\cdot cov(X,Y), \tag{3} \\
  cov(X, Y+Z) &= cov(X,Y) + cov(X,Z). \tag{4} \\
\end{align*}
$$

If $$X$$ and $$Y$$ are independent, $$cov(X, Y) = 0$$ (this is shown in $$(1)$$).

> covariance 為 $$0$$ **不**表示 $$X$$ 和 $$Y$$ independent！


#### The variance of a sum of r.v.s

$$
\begin{align*}
var(X_1+X_2) &= E\Big[(X_1+X_2 - E[X_1+X_2])^2 \Big] \\
&= var(X_1) + var(X_2) + 2cov(X_1, X_2). \tag{1}
\end{align*}
$$

$$
\begin{align*}
var\Big(\sum_{i=1}^n X_i\Big) &= \sum_{i=1}^nvar(X_i) + \sum_{i\not = j}cov(X_i, X_j) \tag{2} \\ 
&= \sum_{i=1}^ncov(X_i, X_i) + \sum_{i\not = j}cov(X_i, X_j) \\
&= \sum_{i,j} cov(X_i, X_j). \tag{3}
\end{align*}
$$

從 [Properties](#properties) 的第二點可以發現 covariance 和 variance 的關係，於是此處等式 $$(3)$$ 成立；共 $$n^2$$ 項。

等式 $$(3)$$ 並沒有實質上計算的好處，只是符號統一而已。

---

## Correlation Coefficient
### Definition
> $$\rho(X,Y) = {cov(X,Y) \over \sigma_X\sigma_Y}.$$

**Correlation coefficient** 是 *dimensionless version of* covariance，也可以說是標準化的 covariance，代表 r.v. 之間的關聯程度。因為 correlation coefficient 有固定的值域 （$$-1\le \rho \le 1$$，稍後證明），因此比起 covariance 是更能顯示 r.v. 之間的關聯性究竟有多高。

> correlation coefficient: 相關係數。

### Theorem: $$\vert \rho \vert \le 1$$

**Proof**

$$
\rho(X,Y) = E\bigg[{X-E[X]\over \sigma_X}\cdot {Y-E[Y]\over \sigma_Y}\bigg] 
$$

Suppose $$X$$ and $$Y$$ are of zero means and unit variances, so that $$\rho(X,Y) = E[XY]$$.

> 這是為了簡化計算。

And we have

$$
\begin{align*}
E\Big[(X-\rho Y)^2 \Big] &= E[X^2] - 2\rho E[XY] + \rho^2E[Y^2] \\
&= 1 - 2\rho^2 + \rho^2 = 1 - \rho^2.
\end{align*}
$$

Since $$(X-\rho Y)^2$$ is always nonnegative, $$E\Big[(X-\rho Y)^2 \Big]$$ and $$1-\rho^2$$ must also be nonnegative. Hence,

$$
1-\rho^2 \ge 0,\ \vert \rho\vert \le 1. \tag*{$\blacksquare$}
$$

If $$\vert\rho\vert = 1$$, then $$X=Y$$ or $$X=-Y$$.

### Interpretation

假如 $$\rho(X,Y) \not = 0$$，並不代表 $$X$$ 如何發生會改變 $$Y$$ 的分布，而是存在一潛在因子 $$Z$$ 同時影響著 $$X$$ 和 $$Y$$，也就是說，

> Correlation often reflects **underlying, common, hidden factor**.

---

## Reference

- [MIT OCW](https://ocw.mit.edu/courses/res-6-012-introduction-to-probability-spring-2018/pages/part-i-the-fundamentals/)