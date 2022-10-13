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

In a special case when $$\boldsymbol{b}$$ is projected onto *a single vector* $$\boldsymbol{a}$$ (not a subspace; 1-D projection), $$\boldsymbol{p} = (\boldsymbol{aa^T} / \boldsymbol{a^Ta})\boldsymbol{b} = (\boldsymbol{a^Tb} / \boldsymbol{a^Ta}) \boldsymbol{a}$$. (This formula is analogous to the multi-dimensional version.) (See [The Gram-Schmidt Process](../9_Orthogonality-More/))

---

## Theorem
> $$A^TA$$ is invertible if only if $$A$$ has linearly independent columns.

*Proof:*

First, show that $$A^TA$$ has the same *null space* as $$A$$, i.e. $$N(A) \subseteq N(A^TA)$$ and $$N(A^TA) \subseteq N(A)$$

**(i)**

For all $$\boldsymbol{x} \in N(A), A\boldsymbol{x} = \boldsymbol{0} \Rightarrow A^TA\boldsymbol{x} = A^T\boldsymbol{0} = \boldsymbol{0}$$, which implies $$\boldsymbol{x} \in N(A^TA)$$. Therefore, $$N(A) \subseteq N(A^TA)$$.

**(ii)**

For all $$\boldsymbol{x} \in N(A^TA), (A^TA)\boldsymbol{x} = \boldsymbol{0} \Rightarrow \boldsymbol{x}^T A^TA\boldsymbol{x} = \boldsymbol{x}^T\boldsymbol{0} = 0\ (scalar)$$, and we know $$\boldsymbol{x}^T A^TA\boldsymbol{x} = (A\boldsymbol{x})^T \cdot (A\boldsymbol{x}) = \|A\boldsymbol{x}\|^2 = 0$$. We can conclude that $$A\boldsymbol{x}$$ is a vector with *norm* equal to *zero*, which implies $$A\boldsymbol{x}=\boldsymbol{0}$$, i.e. $$\boldsymbol{x} \in N(A)$$. Therefore, $$N(A^TA) \subseteq N(A)$$.

From **(i)** and **(ii)**, $$N(A) = N(A^TA)$$ is shown.

**(iii)**

Note that $$A$$ is $$m \times n$$ and $$A^TA$$ is $$n \times n$$.

Given $$rank(A)=r, dim(N(A)) = n-r, dim(N(A^TA))=n-rank(A^TA)$$. Since $$N(A) = N(A^TA)$$, hence $$dim(N(A)) = dim(N(A^TA)) \Rightarrow rank(A^TA) = r$$.

As $$A$$ has linealy independent columns, i.e. $$rank(A) = n$$, $$rank(A^TA)$$ also equals to $$n$$. Therefore, $$A^TA$$ is invertible, and $$A^TA$$ is invertible only if its rank is $$n$$. ◼

> Application of this theorem: [image encryption](https://github.com/SiriusKoan/NYCU-LA-final-project/blob/main/technique_specifics.pdf)