---
layout: page
title: Projection
usemathjax: true
tag: Linear Algebra
---

*Define:*
> A projection on a vector space $$V$$ is a linear function $$P:V\to V$$ such that $$P^2 = P$$.

> 也就是說，不管投影幾次，效果都和投影一次相同。

## Projection onto a subspace

> For a given vector $$\boldsymbol{b} \in \mathbb{R}^m$$ and a subspace of $$\mathbb{R}^m$$ spanned by basis $$\{\boldsymbol{a_1}, ..., \boldsymbol{a_n}\}$$, the projection of $$\boldsymbol{b}$$ *onto the subspace* is $$\boldsymbol{p}$$, given by $$P \cdot \boldsymbol{b}=\boldsymbol{p}$$, where $$P$$ is the ***projection matrix***.

> Furthermore, let $$A = \begin{bmatrix}\boldsymbol{a_1}...\boldsymbol{a_n}\end{bmatrix}$$.

<img src= "../img/projection.png"  width="400"/>

---

## Calculation

Since $$\boldsymbol{p}$$ is in $$C(A)$$, we can find $$\boldsymbol{x}$$ s.t. $$A\boldsymbol{x} = \boldsymbol{p}$$. Then let $$\boldsymbol{e} = \boldsymbol{b - p}$$, which is named as *error vector* and is orthogonal to $$\boldsymbol{p}$$. Moreover, $$\boldsymbol{e}$$ is orthogonal to 