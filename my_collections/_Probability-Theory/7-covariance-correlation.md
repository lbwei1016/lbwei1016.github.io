---
layout: page
title: Covariance & Correlation Coefficient
usemathjax: true
tag: Probability
time: 2022/11/02
---

**Table of Content**

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

從 [Properties](#properties) 的第二點可以發現 covariance 和 variance 的關係，於是此處等號 $$(3)$$ 成立；共 $$n^2$$ 項。

---

## Correlation Coefficient
### Definition
> $$\rho(X,Y) = {cov(X,Y) \over \sigma_X\sigma_Y}.$$