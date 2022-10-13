---
layout: page
title: Basis
usemathjax: true
tag: Linear Algebra
---

*Define:*
> A ***basis*** for a vector space $$V$$ is a *linearly independent* subset of $$V$$ that *spans* $$V$$.

## Theorem

> Every basis for the same vector space $$V$$ has the *identical number* of vectors, which equals to $$dim(V)$$.

*Proof:*

Let $$V_0 = \{\boldsymbol{v_1}, ..., \boldsymbol{v_n}\}$$ and $$W = \{\boldsymbol{w_1}, ..., \boldsymbol{w_m}\}$$ are both basis of $$V$$.

**(i)**

Assume $$n > m$$. Since $$\{\boldsymbol{v_1}, ..., \boldsymbol{v_n}\}$$ is a basis for $$V$$, every element in $$V$$ can be expressed as a linear combination of $$\{\boldsymbol{v_1}, ..., \boldsymbol{v_n}\}$$. Particularly, let

$$\boldsymbol{w_i} = a_{1i}\boldsymbol{v_1}+ ... + a_{mi}\boldsymbol{v_m}, \forall\ 1 \leq i \leq m$$

, i.e.

$$\begin{bmatrix}\boldsymbol{w_1} &...& \boldsymbol{w_m}\end{bmatrix} = \begin{bmatrix}\boldsymbol{v_1} &...& \boldsymbol{v_n}\end{bmatrix}\begin{bmatrix}\boldsymbol{a_{11}} &...& \boldsymbol{a_{1n}} \\ ... \\ \boldsymbol{a_{m1}} &...& \boldsymbol{a_{mn}} \end{bmatrix}$$

, which means:

$$W = V_0A$$

Here $$A$$ is a $$m \times n$$ matrix, and thus $$N(A) \neq \{\boldsymbol{0}\}$$, for $$n > m$$ (column 數大於 row 數).<br>
$$\Rightarrow$$ There exists non-zero $$\boldsymbol{x} \in \mathbb{R}^n$$ s.t. $$A\boldsymbol{x} = \boldsymbol{0} \Rightarrow V_0A\boldsymbol{x} = \boldsymbol{0} \Rightarrow W\boldsymbol{x} = \boldsymbol{0}$$<br> 
$$\therefore N(W) \neq \{\boldsymbol{0}\}$$, but this contradicts the fact that $$\{\boldsymbol{w_1}, ..., \boldsymbol{w_m}\}$$ is a basis. (Vectors in a basis must be linearly independent.) 

**(ii)**

Similarly, we can prove that $$n < m$$ is impossible either.

$$\therefore n = m$$ ∎

---

## Dimension of Vector Space

> $$dim(V) = $$ **number of vectors** in any *basis* for $$V$$ (basis 的 vector 數量) (詳見 [Linear Transformation])