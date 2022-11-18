---
layout: page
title: Transforms
usemathjax: true
tag: Probability
time: 2022/11/18
---

**Table of Content**
- [Definition (tranforms)](#definition-tranforms)
- [Properties](#properties)
  - [Inversion Property (unique)](#inversion-property-unique)
  - [Sum of Independent R.V.s](#sum-of-independent-rvs)
  - [Moments](#moments)
- [Transforms for Some R.V.s](#transforms-for-some-rvs)
  - [Discrete](#discrete)
    - [Bernoulli](#bernoulli)
    - [Binomial](#binomial)
    - [Geometric](#geometric)
    - [Poisson](#poisson)
    - [Uniform](#uniform)
  - [Continuous](#continuous)
    - [Uniform](#uniform-1)
    - [Expoenetial](#expoenetial)
    - [Normal](#normal)
- [Reference](#reference)

---

## Definition (tranforms)
The **transform** associated with a ramdom variable $$X$$ is defined by 

$$
M_X(s) = E[e^{sX}],
$$

where $$s$$ is a scalar parameter.

> **Transform** is also referred to **moment [generating function](../../Concrete-Math/Generating-Functions)**.

When $$X$$ is discrete, the corresponding transform is given by

$$
M(s) = \sum_xe^{sx}p_X(x),
$$

while in the continous case it is given by

$$
M(s) = \int_{-\infty}^{\infty}e^{sz}f_X(x)dx.
$$

> 下標 $$X$$ 在上下文明確時可省略。

---

## Properties

### Inversion Property (unique)
Given a transform $$M_X(s)$$, the distribution of $$X$$ can be **uniquely determined**.

> 也就是說，可以從 transform 來倒推 r.v. 的 CDF！

In fact, more mathematical condition are required, but it suffices to know this simplified fact first.

### Sum of Independent R.V.s

Let $$Z=X+Y$$, and $$X$$ and $$Y$$ are independent r.v.s, and by definition

$$
M_Z(s) = E[e^sZ] = E[e^s(X+Y)] = E[e^{sX}e^{sY}].
$$

Since $$X$$ and $$Y$$ are independent, we have

$$
M_Z(s) = E[e^{sX}]E[e^{sY}] = M_X(s)M_Y(s).
$$

Recall that the [multiplication of two generating functions](../../Concrete-Math/Generating-Functions/#multiplication) is associated with *convolution*, which satisfies the result [here](../6-derived-distro/#the-distribution-of-xy).

### Moments

By definition, $$M_X(s) = E[e^{sX}]$$. If we differentiate it, we get

$$
{d\over ds}M_X(s) = {d\over ds}E[e^{sX}] = E\Big[{d\over ds}e^{sX}\Big] = E[Xe^{sX}],
$$

which means that 

$$
{d\over ds}M_X(s)\Bigg\vert_{s=0} = E[X].
$$

> 將 $$E[\cdot]$$ 依定義展開就可以看出為何 $${d\over ds}$$ 可以任意移動。

We can further derive that 

$$
{d^n\over ds^n}M_X(s)\Bigg\vert_{s=0} = E[X^n].
$$

> 只要有 transform，求 moment 變得輕鬆！

---

## Transforms for Some R.V.s

### Discrete

#### Bernoulli

$$
M(s) = 1-p+pe^s.
$$

#### Binomial

$$ M(s) = (1-p+pe^s)^n. $$

#### Geometric

$$M(s) = {pe^s\over 1-(1-p)e^s}. $$

#### Poisson

$$ M(s) = e^{\lambda(e^s-1)}. $$

#### Uniform

$$M(s) = {e^{sa}(e^{s(b-a+1)})-1 \over (b-a+1)(e^s-1)}.$$

### Continuous

#### Uniform

$$M(s) = {e^{sb}-e^{sa}\over s(b-a)}.$$

#### Expoenetial

$$M(s) = {\lambda\over \lambda-s}.$$

#### Normal

$$M(s) = e^{\sigma^2s^2/2}+\mu s .$$

Particularly, for standard normal, we have

$$
M(s) = e^{s^2/2}
$$

---

## Reference

- Introduction to Probability, 2nd, by Dimitri P. Bertsekas and John N. Tsitsiklis