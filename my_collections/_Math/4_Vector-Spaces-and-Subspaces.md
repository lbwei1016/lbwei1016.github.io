---
layout: page
title: Vector Spaces and Subspaces
usemathjax: true
tag: Linear Algebra
--- 

> The space $$\mathbb{R}^n$$ consists of all vectors $$\boldsymbol{v}$$ with $$n$$ components.

## Vector Spaces

* Define:

> A vector space $$V$$ is a collection of vectors with two operations
>
> 1. vector addition (element-wise)
> 2. scalar multiplication
>
> so that $$\forall \boldsymbol{v}, \boldsymbol{w} \in V, \boldsymbol{v} + \boldsymbol{w} \in V, and \ \forall c \in \mathbb{R}, c\boldsymbol{v} \in V$$ 

> Any linear combination of vectors in $$\mathbb{R}^n$$ results in a vector in $$\mathbb{R}^n$$.

## Subspaces

* Define:

> A subset $$W$$ of a vector space $$V$$ is called a subspace if $$W$$ itself form a vector space with the two operations defined on $$V$$ and contains $$\boldsymbol{0}$$.
>
> In short, **all linear combinations stay in the subspace $$W$$.** (closedness of $$W$$) (封閉性)

* Theorem (see below)

### Column space of Matrix

> The *column space of $$A$$* is defined as "**all linear combinations of the columns of $$A$$**".

* column space of $$A$$ is denoted by $$C(A)$$ 
* see below

### Span

* Define:

> Let $$U$$ be a subset of vectors in a vector space $$V$$, while $$U$$ itself may not be a subspace.
>
> The span of $$U$$ consists of **all linear combinations of the vectors in $$U$$**(including $$\boldsymbol{0}$$), denoted by $$span(U)$$. 

* $$span(U)$$ is always a subspace of $$V$$ (refer to the *Theorem* of *subspaces*)
* $$C(A) = span(U)$$ where $$U = \{ column\ vectors\ of\ A\}$$ 

### Four Fundamental Subspaces

1. Column space of $$A$$ 
2. Row space of $$A$$ (column space of $$A^T$$)
3. Null space of $$A$$ 
   * The null space of $$A$$ consists of all **solutions** of $$A\boldsymbol{x} = \boldsymbol{0}$$, denoted by $$N(A)$$  
4. Left null space of $$A$$ (null space of $$A^T$$)

### Theorem

> Suppose $$A \in \mathbb{R}^{m\times n}$$ 
>
> Proof is attached in the end.

* $$C(A)$$ is a subspace of $$\mathbb{R}^m$$  
* $$N(A)$$ is a subspace of $$\mathbb{R}^n$$  

### Finding Null space

> variable corresponding to *pivot column*: **pivot variable**
>
> variable corresponding to *free column (non-pivot column)*: **free variable** 

1. Use Gaussian-Jordan elimination: $$A \rightarrow R$$ (RREF)
2. Identify *pivot variables* and *free variables*.
3. Identify *special solutions*. (see hand-written note)
4. $$N(A)$$ = $$span(\{special\ solutions\})$$ 

> Note: If no free variables in step 2, $$N(A)=\{\boldsymbol{0}\}$$ 

### Dimension of  Vector Space

> $$dim(V) = $$ **number of vectors** in any *basis* for $$V$$ (basis 的 vector 數量)
>
> **Basis**: A set $$B$$ is called a *basis* if the vectors in $$B$$ are **linearly independent**, and every vector in $$V$$ is a linear combination of vectors in $$B$$. ($$B$$ is in vector space $$V$$.)

#### The dimension of null space

> Define:
>
> The dimension of a *null space* is the number of **free variables**, i.e. 
>
> $$dim(N(A))$$ = number of special solutions

### Rank(& Nullity)

> Given $$A_{m\times n}$$
>
> $$rank(A) =$$ 
> * number of non-zero rows in the **RREF** of A
> * number of **pivots(pivot variable)** in $$A$$ 
>
> $$nullity(A) = n - rank(A)$$ 
> * number of **free variables** 

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

