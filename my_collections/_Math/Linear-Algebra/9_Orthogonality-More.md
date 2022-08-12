---
layout: page
title: More on Orthogonality 
usemathjax: true
tag: Linear Algebra
---
## Orthogonal Bases

*Define:*

> All vectors in a *orthogonal basis* are othogonal to each other.

---

## Orthonormal Matrix

*Define:*

> Orthonormal: *orthogonal + normalized*

> An *orthonormal matrix* contains normalized vectors which are orthogonal to each other; here we denote a orthonormal matrix $$Q$$.

### Theorem

**(i)**

> $$Q^TQ = I$$. Moreover, if $$Q$$ is square, $$Q^{-1} = Q^T$$

**(ii)**

> An Orthonormal matrix preserves properties such as *norm* and *dot product* of vectors it multiplies with.

> $$\|Q\boldsymbol{x}\| = \|\boldsymbol{x}\|$$ and $$(Q\boldsymbol{x})^T(Q\boldsymbol{y}) = \boldsymbol{x^Ty}$$

---

## The Gram-Schmidt Process

> A systematic way to create orthogonal basis from any basis. (actually *orthonormal*)

> Note: Orthonormal basis is often(?) called only *orthogonal* basis.

**Algorithm GS** (Produce an orthonormal basis). Given a ordinary basis $$\{\boldsymbol{v_1},...,\boldsymbol{v_n}\}$$, convert it to an orthonormal basis.

**I.** [Initailize] Let $$\boldsymbol{e_1} = \boldsymbol{v_1}, \boldsymbol{q_1} = \boldsymbol{e_1}/\|\boldsymbol{e}\|$$

**II.** [Convertion] Set $$\boldsymbol{e_k} = \sum_{1\leq i\leq k-1}(\boldsymbol{q_i^T\boldsymbol{v_k}})\boldsymbol{q_i}$$
cont.