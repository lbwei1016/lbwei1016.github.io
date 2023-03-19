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
  - [Theorem (principal ideal \<=\> all)](#theorem-principal-ideal--all)
  - [Definition (maximal ideal)](#definition-maximal-ideal)
    - [Proposition (prime; maximal)](#proposition-prime-maximal)
  - [Theorem (maximal \<=\> field)](#theorem-maximal--field)
- [Prime Ideals](#prime-ideals)
  - [Definition (prime ideal)](#definition-prime-ideal)
    - [Remark](#remark)
    - [More Examples](#more-examples)
  - [Theorem (prime \<=\> integral domain)](#theorem-prime--integral-domain)
    - [Corollary (maximal =\> prime)](#corollary-maximal--prime)
    - [Examples](#examples)
- [Ideals of Polynomial Rings](#ideals-of-polynomial-rings)
  - [Theorem (field =\> principal)](#theorem-field--principal)
  - [Theorem (maximal \<=\> irreducible)](#theorem-maximal--irreducible)
    - [Corollary (field \<=\> irreducible)](#corollary-field--irreducible)
  - [Theorem (irreducible: prime)](#theorem-irreducible-prime)
- [Remark](#remark-1)

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

### Theorem (principal ideal <=> all)
> Let $$R$$ be a **commutative** ring with unity. A **principal ideal** $$Ra$$ is equal to $$R$$ **iff $$a$$ is a unit**.

> 看看[這](../ideals/#theorem-principal-ideal)！

**Proof**

Use [this theorem](#theorem-ideal--all).

### Definition (maximal ideal)
> A **proper** ideal of a ring $$R$$ is a **maximal ideal** if no proper ideal $$N$$ of $$R$$ *properly contains* $$M$$. That is, if $$N$$ is an ideal such that $$M\subset N\subseteq R$$, then $$N=R$$.

#### Proposition (prime; maximal)
> Let $$p$$ be a prime. Then $$p\Bbb Z$$ is a maximal ideal of $$\Bbb Z$$.

**Proof**

Let $$I$$ be an ideal of $$\Bbb Z$$ properly containing $$p\Bbb Z$$.

We have 

$$
p = [\Bbb Z: p\Bbb Z] = [\Bbb Z:I][I:p\Bbb Z].
$$

Since $$p\Bbb Z\subset I$$, $$[I:p\Bbb Z]>1$$. This implies that $$[I:p\Bbb Z]=p$$ for $$p$$ is prime. Therefore, $$I=\Bbb Z$$. ◼

### Theorem (maximal <=> field)
> Let $$R$$ be a commutative ring with unity. Then $$M$$ is a **maximal ideal iff $$R/M$$ is a field**.

> Check [this](#theorem-prime--integral-domain).

**Proof**

$$(\Rightarrow)$$:

Suppose $$M$$ is a maximal ideal. Since $$R/M$$ is a commutative ring with the unity $$1+M$$. It remains to show that every $$a+M\not=M$$ is a unit.

Since $$a+M\not=M, a\not \in M$$. Consider the canonical homomorphism  $$\gamma: R\to R/M$$ defined by $$\gamma(r) = r+M$$. The preimage of $$\langle a+M \rangle$$ is $$Ra$$, and by [this theorem](../ideals/#theorem-operations-on-ideals), $$Ra+M$$ is also an ideal. Moreover, since $$Ra+M$$ contains $$M$$ and $$M$$ is maximal, $$Ra+M = R$$. Therefore, there exist $$m\in M$$ and $$r\in R$$ such that $$ra+m=1$$. It follows that $$ra=1-m \in 1+M$$. Thus, $$a+M$$ has a multiplicative inverse $$r+M$$ in $$R/M$$. ◼

$$(\Leftarrow)$$:

Suppose $$R/M$$ is a field, and let $$N$$ be an ideal of $$R$$ properly containing $$M$$. We want to show that $$N=R$$. 

By our assumption, there exists an element $$a\in N\backslash M$$. Then $$a+M\not=M$$ in $$R/M$$, and thus $$a+M$$ has a multiplicative inverse $$b+M$$ in $$R/M$$. This means that $$1-ab\in M\subset N$$. Since $$N$$ is an ideal, $$ab \in N$$, and thus $$1=(1-ab)+ab\in N$$. This [implies](#theorem-ideal--all) $$N=R$$. Therefore $$M$$ is maximal. ◼

**Alternative proof for $$(\Leftarrow)$$:**

Since $$N$$ is an ideal of $$R$$ and $$N$$ properly contains $$M$$, with the canonical homomorphism $$\gamma$$ defined above, $$N/M = \gamma(N)$$ is a non-trivial ideal of $$\phi(R) = R/M$$. To see why $$N/M$$ is a non-trivial ideal of $$\phi(R)$$, recall from [this theorem](../ideals/#theorem-kernel-ideal-tongue-twister), and thus we know the trivial ideal of $$\phi(R)$$ is $$M$$ itself. (Note that by [that theorem](../ideals/#theorem-ideal-as-a-kernel), $$M$$ is the kernel of $$\gamma$$.) Since $$R/M$$ is a field, the non-trivial ideal $$N/M$$ must be the whole field $$R/M$$, by [this corollary](#corollary-field-no-proper-nontrivial-ideal). We conclude that $$N=R$$. ◼

---

## Prime Ideals
### Definition (prime ideal)
> A **proper** ideal $$P$$ in a **commutative** ring $$R$$ is a **prime ideal** if $$ab\in P$$ implies $$a\in P$$ or $$b\in P$$.

#### Remark

Why this is called **prime**? See the example below.

Let $$R=\Bbb Z$$. If $$n=p$$ is a **prime** and $$ab\in p\Bbb Z$$, then $$p\mid ab$$, which implies that $$p\mid a$$ or $$p\mid b$$. Thus, $$ab\in p\Bbb Z$$ does imply $$a\in p\Bbb Z$$ or $$b\in p\Bbb Z$$, i.e., $$p\Bbb Z$$ is a **prime ideal** of $$\Bbb Z$$.

> 質因數！

#### More Examples
- If $$R$$ is an [integral domain](../integral-domain), then $$\{0\}$$ is a prime ideal. 
  - No zero divisors in $$R$$!

### Theorem (prime <=> integral domain)
> Let $$R$$ be a **commutative** ring with unity. Then $$P$$ is a **prime ideal of $$R$$ iff $$R/P$$ is an integral domain**.

> Check [this](#theorem-maximal--field).

**Proof**

Since $$R$$ is a commutative ring with unity, its quotient ring $$R/P$$ is also a commutative ring with unity. We can see that

$$
\begin{align*}
  &R/P \text{ is an integral domain} \\
\iff &(a+P)(b+P)=0+P \implies (a+P=0+P) \lor (b+P=0+P) \\
\iff &ab\in P \implies (a\in P) \lor (b\in P) \\
\iff &P\text{ is a prime ideal.} \tag*{$\blacksquare$}
\end{align*}
$$

#### Corollary (maximal => prime)
> Every **maximal** ideal in a **commutative** ring with unity is a **prime ideal**.

> 反之未必！The trivial ideal $$\{0\}$$ of $$\Bbb Z$$ is a prime ideal but **not** a maximal one.

> 由此可知，maximal 是比 prime 更強的性質。

#### Examples

- Let $$R$$ be an integral domain. Then $$\{0\}$$ is a prime ideal. We find that $$R/\{0\}\cong R$$ is indeed an integral domain.
- If $$p$$ is prime, then $$p\Bbb Z$$ is a prime ideal, and $$\Bbb{Z}/p\Bbb{Z} = \Bbb Z_p$$ is a field! 
  - If $$n$$ is not prime, $$\Bbb Z_n$$ is not an integral domain.

---

## Ideals of Polynomial Rings
### Theorem (field => principal)
> Let $$\Bbb F$$ be a **field**. Then **every** ideal $$I$$ in $$\Bbb F[x]$$ is [principal](../ideals/#theorem-principal-ideal).

**Proof**

If $$I=\{0\}$$, $$I=\langle 0\rangle$$ is principal. Otherwise, let $$g(x)$$ be a nonzero element of $$I$$ of minimal degree. We claim that $$I=\langle g(x)\rangle$$.

For any $$f(x)\in I$$, using the division algoritm can yield $$f(x) = q(x)g(x) + r(x)$$, where $$r(x)=0$$ must hold, by the minimality of $$\deg g(x)$$. Thus, $$f(x)=q(x)g(x)\in \langle g(x) \rangle$$, and thus $$I\subseteq \langle g(x)\rangle$$.

Conversely, since $$g(x)\in I$$, we have $$\langle g(x)\rangle \subseteq I$$, and hence $$I=\langle g(x)\rangle$$. Therefore, $$I$$ is a principal ideal. ◼

> Every $$I$$ on $$\Bbb Z$$ is also principal!

### Theorem (maximal <=> irreducible)
> An ideal $$\langle p(x)\rangle$$ in $$\Bbb F[x]$$ is **maximal** iff $$p(x)$$ is **irredcible** over $$\Bbb F$$.

**Proof**

$$(\Rightarrow)$$:

Let $$\langle p(x)\rangle$$ be a maximal ideal. We need to prove that 

- $$p(x)$$ is not a constant polynomial, and
- if $$p(x) = f(x)g(x)$$, then either $$f(x)$$ or $$g(x)$$ is a unit in $$\Bbb F[x]$$.

If $$p(x)$$ is a nonzero constant polynomial, then $$p(x)$$ is a unit in $$\Bbb F[x]$$ and $$\langle p(x) \rangle = \Bbb F[x]$$, contradictiing to the assumption that $$\langle p(x)\rangle$$ is maxiaml. Thus, $$p(x)$$ is not a constant polynomial.

Now suppose $$p(x) = f(x)g(x)$$. Then by [this corollary](../ideals/#corollary-eq-propertiey), $$\langle p(x) \rangle \subset \langle f(x)\rangle$$. Since $$\langle p(x)\rangle$$ is maximal, either $$\langle f(x)\rangle=\Bbb F[x]$$ or $$\langle f(x)\rangle = \langle p(x) \rangle$$. For the former case, $$f(x)$$ is a unit; for the latter case, $$f(x)\in \langle p(x)\rangle$$ and $$f(x) = p(x)h(x)$$ for some $$h(x) \in \Bbb F[x]$$. Then, $$p(x) = f(x)g(x) = p(x)[h(x)g(x)]$$, and thus $$h(x)g(x)=1$$, implying $$g(x)$$ is a unit. 

$$(\Leftarrow)$$:

Use a similar argument as above.

#### Corollary (field <=> irreducible)
> The factor ring $$\Bbb F[x]/\langle p(x)\rangle$$ is a **field** iff $$p(x)$$ is irreducible over $$\Bbb F$$.

> By [this theorem](#theorem-maximal--field)!

### Theorem (irreducible: prime)
> Check [here](../poly-factorization/#theorem-like-prime).

**Proof (use ideals)**

Since $$p(x)$$ is irreducible, by the [previous theorem](#theorem-maximal--irreducible), $$\langle p(x)\rangle$$ is maximal, which is also a **prime** ideal. If $$p(x)\mid r(x)s(x)$$, then $$r(x)s(x)\in \langle p(x)\rangle$$. Thus, $$r(x)\in \langle p(x)\rangle$$ or $$s(x)\in \langle p(x)\rangle$$, which implies the result. ◼

---

## Remark

- $$
\text{Commutative ring with unity } \xrightarrow{\text{no proper non-trivial ideals}} \text{ field}
$$,
- $$
\text{Group} \xrightarrow{\text{no proper non-trivial normal subgroups}} \text{simple group}
$$.