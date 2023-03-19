---
layout: page
title: More on Ideals
usemathjax: true
tag: Abstract Algebra, Ring
time: 2023/03/19
---

**Table of Content**
- [Maximal Ideals](#maximal-ideals)
  - [Definitions (trivial; proper)](#definitions-trivial-proper)
  - [Theorem (ideal =\> all)](#theorem-ideal--all)
    - [Corollary (field: no proper, nontrivial ideal)](#corollary-field-no-proper-nontrivial-ideal)
  - [Theorem (principal ideal =\> all)](#theorem-principal-ideal--all)
  - [Definition (maximal ideal)](#definition-maximal-ideal)
  - [Theorem (maximal =\> field)](#theorem-maximal--field)

---

## Maximal Ideals

### Definitions (trivial; proper)
> For a nonzero ring $$R$$, we define:
>
> - $$\{0\}$$ to be the **trivial** ideal.
> - $$R$$ to be the **improper** ideal.
> - Any other ideal is a **proper non-trivial** ideal.


### Theorem (ideal => all)
> Let $$R$$ be a ring with unity. If an ideal $$I$$ contains an **unit**, then $$I=R$$.

**Proof**

Let $$u$$ be a unit contained in $$I$$. Then $$1=u^{-1}u\in I$$. It follows that $$r=r1\in I$$ for all $$r\in R$$. ◼

#### Corollary (field: no proper, nontrivial ideal)
> A **field** contains no proper nontrival ideals.

**Proof**

Sine any nontrivial ideal of a field contains a unit, it must be the whole field.

### Theorem (principal ideal => all)
> Let $$R$$ be a **commutative** ring with unity. A **principal ideal** $$Ra$$ is equal to $$R$$ **iff $$a$$ is a unit**.

> 看看[這](../ideals/#theorem-principal-ideal)！

**Proof**

Use [this theorem](#theorem-ideal--all).

### Definition (maximal ideal)
> A **proper** ideal of a ring $$R$$ is a **maximal ideal** if no proper ideal $$N$$ of $$R$$ *properly contains* $$M$$. That is, if $$N$$ is an ideal such that $$M\subset N\subseteq R$$, then $$N=R$$.

> Let $$p$$ be a prime. Then $$p\Bbb Z$$ is a maximal ideal of $$\Bbb Z$$.

### Theorem (maximal => field)
> Let $$R$$ be a commutative ring with unity. Then $$M$$ is a **maximal ideal iff $$R/M$$ is a field**.

**Proof**

$$(\Rightarrow)$$:

Suppose $$M$$ is a maximal ideal. Since $$R/M$$ is a commutative ring with the unity $$1+M$$. It remains to show that every $$a+M\not=M$$ is a unit.

Since $$a+M\not=M, a\not \in M$$. Consider the canonical homomorphism  $$\gamma: R\to R/M$$ defined by $$\gamma(r) = r+M$$. The preimage of $$\langle a+M \rangle$$ is $$Ra$$, and by [this theorem](../ideals/#theorem-operations-on-ideals), $$Ra+M$$ is also an ideal. Moreover, since $$Ra+M$$ contains $$M$$ and $$M$$ is maximal, $$Ra+M = R$$. Therefore, there exist $$m\in M$$ and $$r\in R$$ such that $$ra+m=1$$. It follows that $$ra=1-m \in 1+M$$. Thus, $$a+M$$ has a multiplicative inverse $$r+M$$ in $$R/M$$. ◼

$$(\Leftarrow)$$:

Suppose $$R/M$$ is a field, and let $$N$$ be an ideal of $$R$$ properly containing $$M$$. We want to show that $$N=R$$. 

By our assumption, there exists an element $$a\in N\backslash M$$. Then $$a+M\not=M$$ in $$R/M$$, and thus $$a+M$$ has a multiplicative inverse $$b+M$$ in $$R/M$$. This means that $$1-ab\in M\subset N$$. Since $$N$$ is an ideal, $$ab \in N$$, and thus $$1=(1-ab)+ab\in N$$. This [implies](#theorem-ideal--all) $$N=R$$. Therefore $$M$$ is maximal. ◼

**Alternative proof for $$(\Leftarrow)$$:**

Since $$N$$ is an ideal of $$R$$ and $$N$$ properly contains $$M$$, with the canonical homomorphism $$\gamma$$ defined above, $$N/M = \gamma(N)$$ is a non-trivial ideal of $$\phi(R) = R/M$$. To see why $$N/M$$ is a non-trivial ideal of $$\phi(R)$$, recall from [this theorem](../ideals/#theorem-kernel-ideal-tongue-twister), and thus we know the trivial ideal of $$\phi(R)$$ is $$M$$ itself. (Note that by [that theorem](../ideals/#theorem-ideal-as-a-kernel), $$M$$ is the kernel of $$\gamma$$.) Since $$R/M$$ is a field, the non-trivial ideal $$N/M$$ must be the whole field $$R/M$$, by [this corollary](#corollary-field-no-proper-nontrivial-ideal). We conclude that $$N=R$$. ◼