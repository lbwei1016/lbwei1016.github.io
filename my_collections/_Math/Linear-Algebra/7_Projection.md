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

> For a given vector $$\boldsymbol{b} \in \mathbb{R}^m$$ and a subspace of $$\mathbb{R}^m$$ spanned by basis $$\{\boldsymbol{a_1}, ..., \boldsymbol{a_n}\}(n<m)$$, the projection of $$\boldsymbol{b}$$ *onto the subspace* is $$\boldsymbol{p}$$, given by $$P \cdot \boldsymbol{b}=\boldsymbol{p}$$, where $$P$$ is the ***projection matrix***.

> Furthermore, let $$A = \begin{bmatrix}\boldsymbol{a_1}...\boldsymbol{a_n}\end{bmatrix}$$.

<img src= "../img/projection.png"  width="400"/>

---

## Calculation

Since $$\boldsymbol{p}$$ is in $$C(A)$$, we can find non-zero $$\boldsymbol{x}$$ s.t. $$A\boldsymbol{x} = \boldsymbol{p}$$. Then let $$\boldsymbol{e} = \boldsymbol{b - p}$$, which is named as *error vector* and is orthogonal to $$\boldsymbol{p}$$. We know that $$\boldsymbol{p}$$ arbitrarily lies on $$C(A)$$, so $$<\boldsymbol{e}, \boldsymbol{p}> = 0$$ implies $$<\boldsymbol{e}, \boldsymbol{a_i}> = 0$$; thus $$\boldsymbol{e}^TA = \boldsymbol{0}$$.

From $$\boldsymbol{e}^TA = (\boldsymbol{b}-\boldsymbol{p})^TA = \boldsymbol{0}$$, we can derive that:

$$\boldsymbol{b}^TA = \boldsymbol{p}^TA  = (A\boldsymbol{x})^TA = \boldsymbol{x}^TA^TA$$,

i.e.

$$A^T\boldsymbol{b} = A^TA\boldsymbol{x}$$.

Thus, 

$$\boldsymbol{x} = (A^TA)^{-1}A^T\boldsymbol{b}$$.<br>($$A^TA$$ is invertible here, which we will prove later.)

To sum up, from $$\boldsymbol{p} = A\boldsymbol{x} = A(A^TA)^{-1}A^T\boldsymbol{b} = P\boldsymbol{b}$$, we can find that *projection matrix* $$P=A(A^TA)^{-1}A^T$$, and that $$P^2 = P$$.

---

## Theorem
> $$A^TA$$ is invertible if only if $$A$$ has linearly independent columns.

*Proof:*
First, show that $$A^A$$