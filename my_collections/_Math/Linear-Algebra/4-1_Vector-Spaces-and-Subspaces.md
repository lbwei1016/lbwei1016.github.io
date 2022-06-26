---
layout: page
title: Vector Spaces and Subspaces
usemathjax: true
tag: Linear Algebra
--- 

> The space $$\mathbb{R}^n$$ consists of all vectors $$\boldsymbol{v}$$ with $$n$$ components.

## Vector Spaces

*Define:* 

> A vector space $$V$$ is a collection of vectors with two operations
>
> 1. vector addition (element-wise)
> 2. scalar multiplication
>
> so that $$\forall \boldsymbol{v}, \boldsymbol{w} \in V, \boldsymbol{v} + \boldsymbol{w} \in V, and \ \forall c \in \mathbb{R}, c\boldsymbol{v} \in V$$ 

> Any linear combination of vectors in $$\mathbb{R}^n$$ results in a vector in $$\mathbb{R}^n$$.

## Subspaces

*Define:* 

> A subset $$W$$ of a vector space $$V$$ is called a subspace if $$W$$ itself form a vector space with the two operations defined on $$V$$ and contains $$\boldsymbol{0}$$.
>
> In short, **all linear combinations stay in the subspace $$W$$.** (closedness of $$W$$) (封閉性)

### Column space & Null space
* 以上兩者都是 ***Four Fundamental Subspaces*** 之一，非常重要，細節見[另一文章]。

### Span

*Define:* 

> Let $$U$$ be a subset of vectors in a vector space $$V$$, while $$U$$ itself may not be a subspace.
>
> The span of $$U$$ consists of **all linear combinations of the vectors in $$U$$**(including $$\boldsymbol{0}$$), denoted by $$span(U)$$.

> 由向量擴展出的空間 (集合)。  

* $$span(U)$$ is always a subspace of $$V$$ (refer to the *Theorem* of *subspaces*)
* $$C(A) = span(U)$$, where $$U = \{ column\ vectors\ of\ A\}$$ 

## Rank & Nullity

> Given $$A_{m\times n}$$
>
> $$rank(A) =$$ 
> * number of non-zero rows in the **RREF** of A
> * number of **pivots(pivot variable)** in $$A$$ 
> * number of **linearly independent** *column vectors*
> * **$$span(A)$$ 的維度 (dimension)**
>
> $$nullity(A) = n - rank(A)$$ 
> * number of **free variables** 
> * 相對於 $$rank$$ 的概念

* Given $$A_{m\times n}$$, $$rank(A) = r$$, $$R$$ is the RREF of A
  *  $$R = I$$
      * $$r = m$$ and $$r = n$$ 
      * $$A$$ is square and invertible
      *  ***full column rank (r = n)*** and ***full row rank (r = m)*** 
      * a single solution
  *  $$R = \begin{bmatrix}I \\ \boldsymbol{0} \end{bmatrix}$$ 
     *  $$r < m$$ and $$r = n$$ 
     *  $$A$$ is *tall* and ***full column rank (r = n)*** 
     *  one or no solution
  *  $$R = \begin{bmatrix}I\  F \end{bmatrix}$$ ($$F$$ is a non-zero matrix)
     *  $$r = m$$ and $$r < n$$ 
     *  $$A$$ is *wide* and ***full row rank (r = m)*** 
     *  $$\infty$$ solutions (has free variable(s))
  *  $$R = \begin{bmatrix}I\ F\\\boldsymbol{0}\ \boldsymbol{0}  \end{bmatrix}$$ 
     *  $$r < m$$ and $$r < n$$ 
     *  $$A$$ is ***not full column rank*** 
     *  zero or $$\infty$$ solution