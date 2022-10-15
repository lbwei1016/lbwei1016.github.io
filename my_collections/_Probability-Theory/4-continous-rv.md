---
layout: page
title: Continous Random Variables
usemathjax: true
tag: Continous, Random Variable
time: 2022/10/05
---

**Table of Content**
- [PDF](#pdf)
  - [Definition](#definition)
- [Expectation](#expectation)
  - [Definition](#definition-1)
- [Special Random Variables](#special-random-variables)
  - [Exponential Random Variable](#exponential-random-variable)
- [CDF](#cdf)
  - [Problem](#problem)
  - [The Geometric and Exponential CDFs](#the-geometric-and-exponential-cdfs)
- [Reference](#reference)
  
---

## PDF
### Definition

> A random variable $$X$$ is called **continuous** if there is a nonnegative function $$f_X$$, called the **probability density function** of $$X$$, such that 

$$P(X \in B) = \int_B f_X(x)dx, \tag{1}$$

for every subset $$B$$ of the real line. In particular, we have

$$P(a \le X \le b) = \int^b_af_X(x)dx, \tag{2}$$

and 

$$
\int_{-\infty}^{\infty}f_X(x)dx = 1.
$$

For very small length $$\delta$$, we have

$$
\int_x^{x+\delta}f_X(t)dt \approx f_X(x)\delta.
$$

> 為什麼叫做 *density*？因為上式的 $$f_X(x)\delta$$ 就像密度乘長度。 
 
值得注意：$$f_X > 1$$ 是合法的，因為他不是機率本身（見 $$(1)$$），[PMF](../2-discrete-rv/#probability-mass-function-pmf) 則直接代表機率；這點從 notation 就可以看出端倪：pmf 是 $$p_X$$，而 pdf 是 $$f_X$$（pmf 有 **$$p$$**，pdf 則非）。

---

## Expectation
### Definition

$$
E(X) = \int^{\infty}_{-\infty}xf_X(x)dx.
$$

> *center of gravity*

---

## Special Random Variables
### Exponential Random Variable

An **exponential** random variable has a pdf of the form

$$
f_X(x) = \begin{cases}
    \lambda e^{-\lambda x},\ &\text{if } x \ge 0, \\
    0, &\text{otherwise},
\end{cases}
$$

where $$\lambda$$ is a positive parameter *characterizing* the pdf.

> 令 $$y=\lambda x$$，可以輕鬆積分，驗證 integral evaluates to 1。

In particular, we have

$$
P(X \ge a) = \int^{\infty}_a \lambda e^{-\lambda x}dx = e^{-\lambda a}
$$

Moreover, 

$$
E(X) = {1 \over \lambda}, \\
var(X) = {1 \over \lambda^2}.
$$

> 對比 [geometric r.v.](../2-discrete-rv/#geometric)，可以發現他們的相似性！

> **memorylessness**!

---

## CDF

CDF stands for **cumulative distribution function**. For every $$x$$ we have

$$
F_X(x) = P(X \le x) = \begin{cases}
    \sum_{k \le x}p_X(k), &\text{discrete,} \\
    \int_{-\infty}^x f_X(t)dt,\ &\text{continous}.
\end{cases}
$$

A cdf have the following properties

- If $$X$$ is discrete, then $$F_X(x)$$ is a piecewise constant function of $$x$$, and by summing and [differencing](../../Concrete-Math/Finite-Calculus/#difference-operator-delta) we have

$$
F_X(k) = \sum_{i=-\infty}^kp_X(i), \\
p_X(k) = F_X(k) - F_X(k-1) = \Delta F_X(k-1).
$$

- If $$X$$ is continous, then $$F_X(x)$$ is a continous function of $$x$$, and by **differentiation** we have

$$
F_X(x) = \int^x_{-\infty}f_X(t)dt, \\
f_X(x) = {d\over dx}F_X(x).
$$

> **CDF** 很好用！因為不管 $$X$$ 是否連續，$$\{X \le x\}$$ 都必定是一合法 event，而且 CDF 可以輕易轉換成 PMF 或PDF。

### Problem

> Let $$X = \text{max}(X_1, X_2, X_3),$$ where $$X_i$$ is the $$i$$-th test score and $$X$$ is the final score. Assume that the score in each test takes one of the values from $$1$$ to $$10$$ with equal probability, independently of the scores in other tests. Find $$p_X$$ and $$E(X)$$ of the final score.

**Solution**

We have 

$$
\begin{align*}
1-F_X(k) = P(X>k) &= P(X_1>K, X_2>k, X_3>k) \\
&= P(X_1>k)P(X_2>k)P(X_3>k) \\
&= ({10-k \over 10})^3.
\end{align*}
$$

Hence 

$$
F_X(k) = 1 - ({10-k \over 10})^3, \\ 
p_X(k) = ({11-k \over 10})^3 - ({10-k \over 10})^3,
$$

and the mean is 

$$
\begin{align*}
E(X) &= (({10 \over 10})^3 - ({9 \over 10})^3) + 2(({9 \over 10})^3 - ({8 \over 10})^3) + \cdots + 10(({1 \over 10})^3 - ({0 \over 10})^3) \\
&= {1 \over 1000} \sum_{k=1}^{10}k^3 \\
&= 3.025 \tag*{$\blacksquare$}
\end{align*}
$$

### The Geometric and Exponential CDFs

The cdf of a geometric r.v. with parameter $$p$$ is given by

$$
F_{geo}(n) = \sum_{k=1}^n p(1-p)^{k-1} = 1-(1-p)^n,\ n=1,2,\cdots, 
$$

and that of an exponential r.v. with parameter $$\lambda > 0$$ is given by

$$
F_{exp}(x) = 0,\ x \le 0, \\
F_{exp}(0) = \int^x_0 \lambda e^{-\lambda t}dt = 1 - e^{-\lambda x},\ x > 0.
$$

Let us define $$\delta = -\ln(1-p)/\lambda$$, so that

$$
e^{-\lambda \delta} = 1-p,
$$

and hence we have

$$F_{exp}(n\delta) = F_{geo}(n),\ n = 1,2,\cdots.$$

這裡可以把 $$\delta$$ 想成：每 $$\delta$$ 秒丟一次硬幣。當 $$\delta$$ 很小的時候（$$\delta \ll 1$$），a geometric r.v. with parameter $$p$$ is **a close approximation** to an exponential r.v. with parameter $$\lambda$$！

> 當 $$\delta \to 0$$，離散就變成了連續。

---

## Reference
- Introduction to Probability, 2/e, by Dimitri P. Bertsekas, John N. Tsitsiklis