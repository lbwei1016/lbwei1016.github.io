---
layout: page
title: Four Fundamental Subspaces
usemathjax: true
tag: Linear Algebra
---

1. Column space of $$A$$ 
2. Row space of $$A$$ (column space of $$A^T$$)
3. Null space of $$A$$ 
   * The null space of $$A$$ consists of all **solutions** of $$A\boldsymbol{x} = \boldsymbol{0}$$, denoted by $$N(A)$$  
4. Left null space of $$A$$ (null space of $$A^T$$)

---

## Column Space
*Define:*
> All linear combinations of the columns of $$A$$. <br>
> All solution(s) to $$A\boldsymbol{x} = \boldsymbol{b}$$.

* Denoted by $$C(A)$$ 

## Null Space
*Define:*
> All solution(s) to $$A\boldsymbol{x} = \boldsymbol{0}$$. 

* Denoted by $$N(A)$$ 

## Theorem

> Suppose $$A \in \mathbb{R}^{m\times n}$$ 
>

* $$C(A)$$ is a subspace of $$\mathbb{R}^m$$  
* $$N(A)$$ is a subspace of $$\mathbb{R}^n$$  

---

## Calulation
### Finding Column Space

### Finding Null space
*Define:* 
> variable corresponding to *pivot column*: **pivot variable**
>
> variable corresponding to *free column (non-pivot column)*: **free variable** 

1. Use Gaussian-Jordan elimination: $$A \rightarrow R$$ (RREF)
2. Identify *pivot variables* and *free variables*.
3. Identify *special solutions*. 
4. $$N(A)$$ = $$span(\{special\ solutions\})$$ 

> If there are no free variables in step 2, $$N(A)=\{\boldsymbol{0}\}$$. In this case, $$dim(N(A))=0$$. (因為 basis 是 $$\{\emptyset\}$$)

### The dimension of null space
*Define:* 
> The dimension of a *null space* is the number of **free variables**, i.e. 
>
> $$dim(N(A))$$ = number of special solutions
