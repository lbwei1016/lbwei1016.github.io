---
layout: page
title: Zeros of Polynomials
usemathjax: true
tag: Abstract Algebra, Ring, Field
time: 2022/11/20
---

**Table of Content**

---

## Theorem (zero and factor)
> An element $$a\in \mathbb{F}$$ is a **zero** of $$f(x) \in \mathbb{F}[x]$$ iff $$x-a$$ is a factor of $$f(x)$$ in $$\mathbb{F}[x]$$.

**Proof**

Use the [division algorithm](../M-rings-of-polynomials/#division-algorithm-of-polynomials).

### Corollary (distinct zeros)
> A non-zero polynomial $$f(x)\in \mathbb{F}[x]$$ of degree $$n$$ can have **at most $$n$$ distinct zeros in $$\mathbb{F}$$**.

**Proof**

- By induction on the degree of $$f(x)$$. 
- For polynomials $$f(x)$$ of degree $$k+1$$, if $$f(x)$$ has a zero, then $$f(x) = (x-a)q(x)$$ for some $$q(x)\in\mathbb{F}[x]$$ of degree $$k$$.
- If $$f(b)=0$$ and $$b\not=a$$, then $$(b-a)q(b)=0$$.
  - Since $$\mathbb{F}$$ has no zero divisors and $$a\not=b$$, $$q(b)=0$$.

### Corollary (the multiplicative group of a field)
> Let $$\mathbb{F}$$ be a field. If $$G$$ is a **finite subgroup** of the multiplicative group $$\mathbb{F}^\times$$, then $$G$$ is **cyclic**. In particular, if $$\mathbb{F}$$ is a **finite field**, then $$\mathbb{F}^{\times}$$ is **cyclic**.

> $$G$$ 當然是 abelian。

**Proof**

By the [fundamental theorem of finitely generated abelian groups](../G-Finitely-Generated-Abelian-Groups/#finitely-generated-abelian-groups), the finite abelian group $$G$$ is isomorphic to $$\mathbb{Z}_{p_1^{e_1}}\times\cdots\times\mathbb{Z}_{p_k^{e_k}} $$ for some primes $$p_i$$ and integers $$e_i\ge 1$$.

Note that $$G$$ contains a subgroup $$H$$ isomorphic to $$\mathbb{Z}_{p_1}\times\cdots\times\mathbb{Z}_{p_k}$$. Suppose $$p_i=p_j=p$$, then $$x^p = 1$$ has **at least** $$p^2$$ solutions in $$H\subset \mathbb{F}$$, which, by [the above corollary](#corollary-distinct-zeros), is a contradiction.

Therefore, all $$p_i$$ are distinct and by [this theorem](../G-Finitely-Generated-Abelian-Groups/#theorem-cyclic-abelian-groups), $$G$$ is cyclic.

> $$p^2$$ 個解哪裡來？例如 $$x=(a,b,1,\cdots,1)$$，而 $$a$$ 和 $$b$$ 各有 $$p$$ 種選擇使 $$x^p = 1$$。