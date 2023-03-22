---
layout: page
title: Unique Factorization Domain
usemathjax: true
tag: Abstract Algebra, UFD
time: 2023/03/22
---

**Table of Content**
- [Definitions (divide, factor, accociate, ...)](#definitions-divide-factor-accociate-)
- [Theorem (integral domain)](#theorem-integral-domain)
- [Definition (UFD)](#definition-ufd)
  - [Examples](#examples)
- [Question](#question)


---

## Definitions (divide, factor, accociate, ...)
> Let $$R$$ be a commutative ring with unity. Let $$a, b\in R$$.
>
> 1. If there exists $$c\in R$$ such that $$b=ac$$, then $$a$$ **divides** $$b$$, i.e., $$a$$ is a **factor** of $$b$$, denoted by $$a\mid b$$.
>
> 2. An element $$u$$ is an **unit** if $$u$$ **divides** $$1$$.
>
> 3. $$a$$ and $$b$$ are **associates** if $$a=ub$$ for some unit $$u\in R$$.
>
> 4. A nonzero non-unit element $$p$$ is an **irreducible** if whenever $$p=ab$$, **either $$a$$ or $$b$$ is an unit**.

> In $$\Bbb Z$$, $$-n$$ and $$n$$ are associates.

## Theorem (integral domain)
> Let $$D$$ be an integral domain. Let $$a, b\in D$$. 
>
> 1. $$a\mid b$$ iff $$\langle b\rangle\subset \langle a\rangle$$.
> 2. $$a$$ and $$b$$ are **associates** iff $$\langle a\rangle = \langle b\rangle$$.
>   - $$a$$ and $$1$$ **associates** iff $$a$$ is an **unit**.
> 3. $$a$$ is **irreducible** iff $$\langle a\rangle$$ is **maximal** among all proper *principal* ideals.

> A **subring with unity of a field** is an **integral domain**!

## Definition (UFD)
> An integral domain $$D$$ is an **unique factorization domain (UFD)** if
>
> 1. Every nonzero non-unit element of $$D$$ can be **factored** into a product of finite number of **irreducibles**.
>
> 2. If $$a\in D$$ has two factorizations $$p_1\cdots p_r$$ and $$q_1\cdots q_s$$ into products of irreducibles, then $$r=s$$ and $$q_j$$ can be renumbered so that $$p_i$$ and $$q_i$$ are **associates**.

### Examples

- Let $$\Bbb F$$ be a field. Then $$\Bbb F$$ and $$\Bbb F[x]$$ are UFDs.
- $$\Bbb Z$$ is a UFD.

## Question
> Show that $$\Bbb Z[\sqrt{-6}]$$ is not a UFD.

First note that $$D = \Bbb Z[\sqrt{-6}]$$ is an integral domain since it is a subring with unity of $$\Bbb C$$.

Let $$N(z) = z\bar z$$. Then, for all $$z_1, z_2\in D$$, $$N(z_1)N(z_2) = N(z_1)N(z_2)$$. Let $$z=3+2\sqrt{-6}$$, then $$N(z) = 3^2 + 6\cdot 2^2 = 33$$. Suppose $$z=z_1z_2$$, then

$$
33 = N(z) = N(z_1)N(z_2).
$$

Since $$N(z_i) = 3$$ or $$11$$ has no solutions, we must have one of $$N(z_i) = 1$$. Therefore, $$z_1$$ or $$z_2$$ is an unit and $$z$$ is irreducible.

The same argument implies that $$(3-2\sqrt{-6}), 3$$, and $$11$$ are all irreducible. Therefore, 

$$
33 = 3 \cdot 11 = (3+2\sqrt{-6})(3-2\sqrt{-6}).
$$

Since $$(3-2\sqrt{-6})$$ is not associated to $$3$$ and $$11$$, we obtain two non-equivalent factorization of $$6$$. That is to say, $$D$$ is not a UFD. ◼


