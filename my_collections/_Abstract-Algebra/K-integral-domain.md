---
layout: page
title: Integral Domain
usemathjax: true
tag: Abstract Algebra, Ring, Field
time: 2022/11/15
---

**Table of Content**


---

## Preface
> Do $$ab=0$$ always imply $$a=0$$ or $$b=0$$? 

## Definition (zero divisor)
> A **non-zero** element $$a$$ of a ring $$R$$ is a **zero divisor** if there exists a **non-zero** element $$b$$ such that $$ab = 0$$.

> 把 $$0$$ 因數分解成 $$a$$ 和 $$b$$ 的感覺。

### Example

- $$\bar 2, \bar 3$$ and $$\bar 4$$ are zero divisors in $$\mathbb{Z}_6$$.

> $$M_n(\mathbb{R})$$ 中有很多 zero divisor！

### Theorem (zero divisors of $$\mathbb{Z}_n$$)
> The zero divisors of $$\mathbb{Z}_n$$ are *precisely* the nonzero elements whose representatives are **not relatively prime** to $$n$$.

#### Corollary (when $$n$$ is prime)
> If $$p$$ is a prime, then $$\mathbb{Z}_p$$ has no zero divisors.

### Theorem (cancellation law)
> **The cancellation law** holds for a ring $$R$$ iff $$R$$ has **no** zero divisors.

**Proof**

$$(\Rightarrow)$$ Assume that the cancellation law holds, but $$ab=0$$ for some $$a, b \not = 0$$. Then we have $$ab = 0 = a0$$, but $$b \not = 0$$, which is a contradiction.

$$(\Leftarrow)$$ Assume that $$R$$ has no zero divisors. If $$ab=ac$$ and $$a\not = 0$$, then $$ab-ac=0=a(b-c)$$, by distributive law. Since $$R$$ has no zero divisors and $$a$$ is assumed to be nonzero, we have $$b-c=0$$ and thus $$b=c$$. ◼

#### Remark

- 就算 $$R$$ 有 zero divisors，只要 $$a^{-1}$$ 存在，$$ab=ac$$ 依舊 implies $$b=c$$。

- 如果 $$R$$ 沒有 zero divisor，則當 $$a\not = 0$$， $$ax=b$$ 在 $$R$$ 中至多有一解（$$a(x_1-x_2) = 0 \Rightarrow x_1=x_2$$；可能無解）。

- If $$R$$ is a **commutative** ring with unity and $$R$$ has no zero divisors, for convenience, $$a^{-1}b$$ can be denoted as **$$b/a$$**. In this case, $$a^{-1}$$ is denoted by **$$1/a$$**.

---

## Definition (integral domain)
> A *commutative* ring $$R$$ with unity $$1\not=0$$ and has *no zero divisors* is an **integral domain**.
>
>The ring of integers $$\mathbb{Z}$$ is an integral domain. 

> 如果 $$R$$ 是 integral domain，則 $$R$$ 的結構和 $$\mathbb{Z}$$ 便有些類似！

### Reamrk

- $$\mathbb{Z}_n$$ is an integral domain iff $$n$$ is prime.
- The direct product $$R\times S$$ of two nonzero rings $$R$$ and $$S$$ is never an integral domain since $$(r,0)(0,s)=(0,0) $$ for all $$r\in R$$ and $$ s\in S$$.

> 第二項 remark 說明了，我們難以用 direct product 的方式建構出性質良好的 ring，不像 [groups](../G-Finitely-Generated-Abelian-Groups)。