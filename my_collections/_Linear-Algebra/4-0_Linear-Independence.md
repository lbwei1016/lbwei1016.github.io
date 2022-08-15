---
layout: page
title: Linear Independence
usemathjax: true
tag: Linear Algebra
---

*Define:*
> A set of vectors $$\boldsymbol{u_1, u_2,..., u_n}$$ are *linearly independent* when
> 
> $$a_1\boldsymbol{u_1} + a_2\boldsymbol{u_2} + ... + a_n\boldsymbol{u_1} = \boldsymbol{0} \Longleftrightarrow a_1 = a_2 = ... = a_n = 0$$

## Linear Dependence

*Define:*
> A set of vectors $$\boldsymbol{u_1, u_2,..., u_n}$$ are *linearly dependent* if they are not linearly independent.

*Remark:*
> Linear dependence implies that $$\boldsymbol{u_i}$$ can be expressed as a linear combination of other vectors, e.g.

$$\boldsymbol{u_1} = -(a_2\boldsymbol{u_2} + ... a_n\boldsymbol{u_n})/a_1$$

---

## Determine Dependence
$$a_1\boldsymbol{u_1} + a_2\boldsymbol{u_2} + ... + a_n\boldsymbol{u_1} = \boldsymbol{0}$$ 
can be expressed as:

$$\begin{bmatrix}\boldsymbol{u_1} & ... & \boldsymbol{u_n}\end{bmatrix} \begin{bmatrix}a_1\\ ...\\ a_n\end{bmatrix} = \boldsymbol{0}$$

Let $$U = \begin{bmatrix}\boldsymbol{u_1} & ... & \boldsymbol{u_n}\end{bmatrix}$$.<br>
The vectors in $$U$$ are *linearly independent* if only if $$N(U)=\{\boldsymbol{0}\}$$.