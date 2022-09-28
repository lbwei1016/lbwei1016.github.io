---
layout: page
title: Random Variable & Cumulants
usemathjax: true
tag: Random Variable, PMF, Cumulants
time: 2022/09/28
---

**Table of Content**
- [Random Variable](#random-variable)
  - [Definition](#definition)
  - [Independence](#independence)
- [Probability Mass Function (PMF)](#probability-mass-function-pmf)
  - [Definition](#definition-1)
- [Expected Value](#expected-value)
  - [Definition](#definition-2)
  - [Properties](#properties)
- [Variance](#variance)
  - [Definition](#definition-3)
  - [Properties](#properties-1)
- [Reference](#reference)

---

## Random Variable
### Definition
> A **random variable** $$X$$ is a *measurable function* $$X: \Omega \to E$$ from a sample space $$\Omega$$ to a measurable space $$E$$. 

> $$E$$ 可以是 $$\mathbb{R}$$、$$\mathbb{Z}$$ 等等；*measurable* 的定義之後再補

**Random variable** 的意義在於，「賦予」樣本空間中的每一事件一個可供計算的數值（粗淺來說）；例如，對於 $$\Omega = \{head, tail\}$$，可以定義

$$X(head) = 1, X(tail) = 0。$$

$$X(\omega)$$ 這個 function 可以不必是 *one-to-one*、*onto*。

### Independence
$$X$$ and $$Y$$ are **independent** random variables if 

$$P(X=x \land Y=y) = P(X=x)\dot{}P(Y=y).$$

---

## Probability Mass Function (PMF)
### Definition
> A **probability mass function (pmf)** is a function over the sample space of a discrete random variable $$X$$ which gives the probability that $$X$$ is equal to a certain value. 

Let $$X$$ be a random variable on a sample space $$\Omega$$. Then the **pmf** $$p: E \to [0,1]$$ is defined as

$$p_X(\omega) = P(X=\omega), \omega \in \Omega,$$

which must satisfies two conditions:

$$\sum_\omega p_X(\omega) = 1 \tag{1}$$
$$p_X(\omega) \ge 0 \tag{2}$$

---

## Expected Value
### Definition

The *mean* of a random variable $$X$$ on a probability sapce $$\Omega$$ is defined to be

$$\sum_{x \in X(\Omega)}x \dot{}P(X=x).$$

> If the sum is *infinite*, it has to be *well-defined* (convergent).

We can give the mean a special name and some alternative notations: Call it the **expected value** and write

$$EX = E(X) = \sum_{\omega \in \Omega}X(\omega)P(\omega) = \mu$$

### Properties

If $$X$$ and $$Y$$ are any two random variable defined on the same probability space $$\Omega$$, then

$$E(X+Y) = \sum_{\omega \in \Omega}(X(\omega) + Y(\omega))P(\omega) = EX + EY. \tag{1}$$

Moreover, if $$X$$ and $$Y$$ are [independent](#independence), 

$$E(XY) = E(X)E(Y). \tag{2}$$

> 左式展開即可證明。

另外，

$$E(\alpha X) = \alpha EX。 \tag{3}$$

---

## Variance
### Definition

**Variance** is defined as the mean square deviation from the mean:

$$VX = V(X) = E((X-EX)^2).$$

**Variance** 用來量測數據的分散性（偏離平均的量），但計算過程的平方使得 variance 呈現的尺度被放大；為了回到常軌，我們取 square root

$$\sigma = \sqrt{VX}，$$

稱其作 **standard deviation**。

### Properties

$$\begin{align*}
  VX &= E((X - EX)^2) \\
  &= E(X^2 - 2XE(X) + E(X)^2) \\
  &= E(X^2) - 2E(X)E(X) + E(X)^2 \\
  &= E(X^2) - E(X)^2 \tag{1}
\end{align*}
$$

> *"The variance is the mean of the square minus the square of the mean."*  

If $$X$$ and $$Y$$ are [independent](#independence),

$$V(X+Y) = VX + VY.$$

> 用到 [independent expected value](#properties) 的性質。

> *"The variance of a sum of independent random variables is the sum of their
variances."* 

---

## Reference
- [Wiki: Random variable](https://en.wikipedia.org/wiki/Random_variable)
- [ncl.ac.uk](https://www.ncl.ac.uk/webtemplate/ask-assets/external/maths-resources/statistics/distribution-functions/probability-mass-function.html)
- [Wiki: Probability mass function](https://en.wikipedia.org/wiki/Probability_mass_function)
- [CMath] (Chapter 8), Concrete Mathematics: A Foundation for Computer Science, by Ronald Graham, Donald Knuth, and Oren Patashni