---
layout: page
title: Zeros of Polynomials
usemathjax: true
tag: Abstract Algebra, Polynomial, Field
time: 2022/11/20
---

**Table of Content**
- [Theorem (zero and factor)](#theorem-zero-and-factor)
  - [Corollary (distinct zeros)](#corollary-distinct-zeros)
  - [Corollary (the multiplicative group of a field)](#corollary-the-multiplicative-group-of-a-field)
- [Irreducible Polynomials](#irreducible-polynomials)
  - [Definition (irreducible polynomials)](#definition-irreducible-polynomials)
    - [Remarks](#remarks)
  - [Theorem (degree $$2$$ or $$3$$)](#theorem-degree-2-or-3)


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

---

## Irreducible Polynomials
### Definition (irreducible polynomials)
> A *nonconstant* polynomial $$f(x) \in \mathbb{F}[x]$$ is **irreducible over $$\mathbb{F}$$** or is an **irreducible polynomial in $$\mathbb{F}[x]$$** if $$f(x)$$ cannot be expressed as a product $$g(x)h(x)$$ of two polynoials in $$\mathbb{F}[x]$$ with $$0< \deg{g(x)},\deg{h(x)} < \deg{f(x)}$$ simultaneously.
>
> If a polynomial $$f(x)\in\mathbb{F}[x]$$ is *nonconstant* and is not irreducible over $$\mathbb{F}$$, then it is reducible over $$\mathbb{F}$$.

**Examples**

- $$x^2+1$$ is irreducible over $$\mathbb{R}$$.
- $$x^2+1$$ is **reducible** over $$\mathbb{C}$$.

> 是否 reducible 端視 over 哪個 field！

#### Remarks

The definition of irreducible polynomials can also be given as 

> $$f(x)$$ is irreducible over $$\mathbb{F}$$ if for any factorization $$f(x)=g(x)h(x)$$ in $$\mathbb{F}[x]$$, one of $$g(x)$$ and $$h(x)$$ is a **unit**.

> 因為 $$g$$ 或 $$h$$ 其中必有一 constant polynomial，而  $$\mathbb{F}[x]$$ 中只有 constants 是 unit。

### Theorem (degree $$2$$ or $$3$$)
> Suppose that $$f(x)\in\mathbb{F}[x]$$ is of degree $$2$$ or $$3$$. Then $$f(x)$$ is rducible over $$\mathbb{F}$$ iff $$f(x)$$ has a zero in $$\mathbb{F}$$.