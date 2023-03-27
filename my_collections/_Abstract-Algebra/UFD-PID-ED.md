---
layout: page
title: UFD, PID, ED
usemathjax: true
tag: Abstract Algebra, UFD, PID, ED
time: 2023/03/22
---

**Table of Content**
- [Unique Factorization Domain (UFD)](#unique-factorization-domain-ufd)
  - [Definitions (divide, factor, accociate, ...)](#definitions-divide-factor-accociate-)
  - [Theorem (integral domain properties)](#theorem-integral-domain-properties)
  - [Definition (UFD)](#definition-ufd)
    - [Examples](#examples)
  - [Lemma (prime \<=\> irreducible)](#lemma-prime--irreducible)
    - [Corollary (not UFD)](#corollary-not-ufd)
  - [Question](#question)
- [Principal Ideal Domain (PID)](#principal-ideal-domain-pid)
  - [Definition (PID)](#definition-pid)
    - [Examples](#examples-1)
  - [Lemma (maximal \<=\> irreducible)](#lemma-maximal--irreducible)
  - [Lemma (irreducible)](#lemma-irreducible)
    - [Proof](#proof)
    - [Corollary (divide someone)](#corollary-divide-someone)
  - [Lemma (ascending chain of ideals)](#lemma-ascending-chain-of-ideals)
  - [Theorem (ascending chain condition; ACC)](#theorem-ascending-chain-condition-acc)
  - [**Theorem (PID =\> UFD)**](#theorem-pid--ufd)
    - [Lemma (product of irreducibles; unique factorizaion)](#lemma-product-of-irreducibles-unique-factorizaion)
  - [Theorem (poly ring UFD)](#theorem-poly-ring-ufd)
    - [Corollary (Hilbert; multivariate)](#corollary-hilbert-multivariate)
- [Euclidean Domain (ED)](#euclidean-domain-ed)
  - [Definition (ED)](#definition-ed)
  - [Theorem (ED =\> PID)](#theorem-ed--pid)
    - [Corollary (ED =\> UFD)](#corollary-ed--ufd)
  - [Theorem (use EF2)](#theorem-use-ef2)
- [Remark (comparison)](#remark-comparison)


---

## Unique Factorization Domain (UFD)
### Definitions (divide, factor, accociate, ...)
> Let $$R$$ be a commutative ring with unity. Let $$a, b\in R$$.
>
> 1. If there exists $$c\in R$$ such that $$b=ac$$, then $$a$$ **divides** $$b$$, i.e., $$a$$ is a **factor** of $$b$$, denoted by $$a\mid b$$.
>
> 2. An element $$u$$ is an **unit** if $$u$$ **divides** $$1$$.
>
> 3. $$a$$ and $$b$$ are **associates** if $$a=ub$$ for some unit $$u\in R$$.
>
> 4. A nonzero non-unit element $$p$$ is an **irreducible** if whenever $$p=ab$$, **either $$a$$ or $$b$$ is a unit**.
>
> 5. A nonzero non-unit element $$p$$ of an **integral domain** is a **prime** if $$p\vert ab$$ implies $$p\vert a$$ or $$p\vert b$$.

> In $$\Bbb Z$$, $$-n$$ and $$n$$ are associates.

### Theorem (integral domain properties)
> Let $$D$$ be an integral domain. Let $$a, b\in D$$. 
>
> 1. $$a\vert b$$ iff $$\langle b\rangle\subset \langle a\rangle$$.
> 2. $$a$$ and $$b$$ are **associates** iff $$\langle a\rangle = \langle b\rangle$$.
>   - $$a$$ and $$1$$ **associates** iff $$a$$ is an **unit**.
> 3. $$a$$ is **irreducible** iff $$\langle a\rangle$$ is **maximal** among all proper *principal* ideals.
> 4. A **prime element $$a$$ is always irreducible**, while the converse is not necessarily true.
> 5. An arbitrary integral domain need not be **[atomic](https://math.stackexchange.com/questions/96790/integral-domain-that-is-not-a-factorization-domain)** (factorization domain).

> A **subring with unity of a field** is an **integral domain**!

**Proof of 4.**

Let $$p=ab$$. Since $$p$$ is a prime and $$p\vert ab$$, we have $$a=cp$$ or $$b=dp$$ for some $$c, d\in D$$. WLOG, suppose $$a=cp$$, and then 

$$
p=ab=cpb=pcb \implies p(1-cb) = 0,
$$

which means that $$cb=1$$. Thus $$b$$ is a unit.

On the other hand, $$2$$ is irreducible in $$\Bbb Z[\sqrt{-5}]$$, but $$2\vert (1+\sqrt{-5})(1-\sqrt{-5})$$ doesn't imply $$2$$ divides either of them. ◼

### Definition (UFD)
> An integral domain $$D$$ is an **unique factorization domain (UFD)** if
>
> 1. Every nonzero non-unit element of $$D$$ can be **factored** into a product of finite number of **irreducibles**.
>
> 2. If $$a\in D$$ has two factorizations $$p_1\cdots p_r$$ and $$q_1\cdots q_s$$ into products of irreducibles, then $$r=s$$ and $$q_j$$ can be renumbered so that $$p_i$$ and $$q_i$$ are **associates**.

#### Examples

- Let $$\Bbb F$$ be a field. Then $$\Bbb F$$ and $$\Bbb F[x]$$ are UFDs.
- $$\Bbb Z$$ is a UFD.

### Lemma (prime <=> irreducible)
> In a **UFD**, an element is irreducible **iff** it is prime.

**Proof (irreduciblity implies prime)**

Let $$p$$ be an irreducible in a UFD $$D$$. We shall prove that for some $$q, x, y\in D$$, whenever $$pq = xy$$, $$p\vert x$$ or $$p\vert y$$. 

**Case 1**: $$xy=0$$.

Since $$D$$ is an integral domain, either $$x$$ or $$y$$ is zero, and we have $$p\vert 0$$.

**Case 2**: $$x$$ or $$y$$ is a unit.

Without loss of generality, suppose $$x$$ is a unit. Then, $$(x^{-1}q)p = y$$, which implies that $$p\vert y$$.

**Case 3**: $$x$$ and $$y$$ are non-zero, non-unit.

First, suppose $$q$$ is a unit. Then $$p = q^{-1}xy = (q^{-1}x)y$$. Since $$p$$ is a prime, it is also irreducible, which implies that either $$(q^{-1}x)$$ or $$y$$ is a unit. By assumption, $$y$$ is not a unit. Suppose $$(q^{-1}x)$$ is a unit, let $$r$$ be its inverse. Then

$$
rq^{-1}x = 1 \implies x = r^{-1}q,
$$

which means that $$x$$ is as well a unit. A contradiction. Thus $$q$$ is not a unit.

Since $$pq=xy$$ and all of them are **non-zero and non-unit**, there must be a one-to-one correspondence between the irreducibles on both sides (unique factorization). This means that $$p$$ must correspond to an irreducible factor of $$x$$ or that of $$y$$, i.e., $$p$$ divides either $$x$$ or $$y$$. ◼

> 要先確認大家都 **non-zero、non-unit**，才可以分解！

#### Corollary (not UFD)
>  To show an integral domain is **not** a UFD, one may show that there exists some irreducible element which is **not** a prime.

### Question
> Show that $$\Bbb Z[\sqrt{-6}]$$ is not a UFD.

First note that $$D = \Bbb Z[\sqrt{-6}]$$ is an integral domain since it is a subring with unity of $$\Bbb C$$.

Let $$N(z) = z\bar z$$. Then, for all $$z_1, z_2\in D$$, $$N(z_1)N(z_2) = N(z_1)N(z_2)$$. Let $$z=3+2\sqrt{-6}$$, then $$N(z) = 3^2 + 6\cdot 2^2 = 33$$. Suppose $$z=z_1z_2$$, then

$$
33 = N(z) = N(z_1)N(z_2).
$$

Since $$N(z_i) = 3$$ or $$11$$ has no solutions, we must have one of $$N(z_i) = 1$$. Therefore, $$z_1$$ or $$z_2$$ is a unit and $$z$$ is irreducible.

The same argument implies that $$(3-2\sqrt{-6}), 3$$, and $$11$$ are all irreducible. Therefore, 

$$
33 = 3 \cdot 11 = (3+2\sqrt{-6})(3-2\sqrt{-6}).
$$

Since $$(3-2\sqrt{-6})$$ is not associated to $$3$$ and $$11$$, we obtain two non-equivalent factorization of $$6$$. That is to say, $$D$$ is not a UFD. ◼

---

## Principal Ideal Domain (PID)
### Definition (PID)
> An integral domain $$D$$ is a **principal ideal domain** if every ideal in $$D$$ is **principal**.

#### Examples

- $$\Bbb Z$$ is a PID. ($$n\Bbb Z$$)
- Let $$\Bbb F$$ be a field, then $$\Bbb F[x]$$ is a PID.

### Lemma (maximal <=> irreducible)
> An ideal $$\langle p\rangle$$ in a PID is **maximal** iff $$p$$ is **irreducible**.

**Proof idea**

If $$p$$ is not irreducible, there exist $$a\mid p$$ for some non-unit $$a$$, which means that $$\langle p\rangle \subset \langle a\rangle$$. 

### Lemma (irreducible)
> In a PID $$D$$, if an **irreducible** $$p$$ divides $$ab$$, then either $$p\mid a$$ or $$p\mid b$$.

#### Proof

Suppose $$p\mid ab$$, then $$ab=pr$$ for some $$r\in D$$. This implies that $$ab\equiv 0$$ in $$D/\langle p\rangle$$. Since $$\langle p\rangle$$ is maximal (by the previous lemma), $$D/\langle p\rangle$$ is a [field](../more-on-ideals/#theorem-maximal--field); we conclude that $$a\equiv 0$$ or $$b\equiv 0$$ (no zero divisor), i.e., $$a\in \langle p\rangle$$ or $$b\in \langle p\rangle$$. ◼

**Alternative proof idea:**

$$x\vert n \iff n\in \langle x\rangle.$$

> 小就是大！

#### Corollary (divide someone)
> In a PID, if an **irreducible** $$p$$ divides $$a_1\cdots a_n$$, then $$p$$ divides $$a_i$$ for some $$i$$.

> 想想 $$\Bbb F[x]$$！

### Lemma (ascending chain of ideals)
> Let $$R$$ be a *commutative* ring. Suppose that $$I_1\subseteq I_2\subseteq\cdots $$ is an **ascending chain of ideals** in $$R$$. Then $$I=\bigcup_i I_i$$ is an ideal of $$R$$.

### Theorem (ascending chain condition; ACC)
> Let $$D$$ be a **PID**. Let $$I_1\subseteq I_2\subseteq\cdots$$ be an ascending chain of ideals. Then there is a positive number $$N$$ such that **$$I_n = I_N$$ for all $$n\ge N$$**.

> 當 $$D$$ 是 infinite 才有討論價值！

> [Noetherian ring](https://en.wikipedia.org/wiki/Noetherian_ring).

**Proof**

Since $$D$$ is a PID, $$I=\langle a\rangle$$ for some $$a\in I$$ (Because we have unity in $$D$$, $$a$$ is guaranteed to stay in $$I$$.). Then there exist some $$N$$ such that $$a\in I_N$$, which implies that $$I=\langle a\rangle = Ra\subseteq I_N$$. We conclude that $$I=I_N$$. ◼

### **Theorem (PID => UFD)**
> If $$D$$ is a PID, then it is also a UFD.

#### Lemma (product of irreducibles; unique factorizaion)
> Let $$D$$ be a PID. Then every non-zero, non-unit element of $$D$$ is a **product of irreducibles**. Such product is **unique** upto order and associates.

**Proof**

Let's first show that every nonzero non-unit element $$a$$ has an irreducible factor, with an algorithmic way.

$$
\begin{align*}
  &\textbf{procedure}: \text{FindIrrFactor}(a \in D) \\
  &\textbf{1.  }\textbf{if } a \text{ is irreducible}: 
  \textbf{return } a. \\
  &\textbf{2.  }\text{Factorize } a \text{ into } a=a_1b_1, \text{ where neither is a unit}. \text{Thus } \langle a\rangle \subset \langle a_1\rangle. \\
  &\textbf{3.  }\textbf{return }\text{FindIrrFactor}(a_1).
\end{align*}
$$

With this algorithm, we obtain a strictly ascending chain of ideals $$\langle a\rangle \subset\langle a_1\rangle \subset \cdots$$. By [ACC](#theorem-ascending-chain-condition), this process must terminate at some point, and thus there exists an irreducible factor $$a_n$$ of $$a$$.

Now, we shall show that $$a$$ is a product of irreducibles. 

$$
\begin{align*}
  &\textbf{procedure}: \text{Factorization}(a \in D) \\
  &\textbf{1.  }\textbf{if } a \text{ is irreducible}: 
  \textbf{return } a. \\
  &\textbf{2.  }\text{Factorize } a \text{ into } a=p_1a_1, \text{ where } p_1 \text{ is irreducible and } a_1\text{ is not a unit}. \text{Thus } \langle a\rangle \subset \langle a_1\rangle. \\
  &\textbf{3.  }\textbf{return }\text{Factorization}(a_1).
\end{align*}
$$

With the same argument, we have $$a=p_1p_2\cdots p_r$$ when the process terminates, where $$p_i$$ are all irreducibles. 

Finally, the proof of uniqueness of factorization resembles the proof [here](../poly-factorization/#theorem-like-prime). Hence it is omitted here. ◼


### Theorem (poly ring UFD)
> The polynomial ring over a UFD is still a UFD.

#### Corollary (Hilbert; multivariate)
> Let $$\Bbb F$$ be a field. Then $$\Bbb F[x_1, \cdots, x_n]$$ is a UFD, but not a PID when $$n\ge2$$.

**Proof (not a PID)**

Let $$I=\langle x_1, x_2\rangle = \{fx_1 + gx_2\mid f, g\in \Bbb F[x_1, x_2] \}$$.

Suppose $$I$$ is principal: $$I=\langle f(x_1, x_2)\rangle$$. There exist $$g_1, g_2\in \Bbb F[x_1, x_2]$$ such that 

$$
\begin{align*}
x_1 = f\cdot g_1 &\implies \deg_{x_2}f = 0, \\
x_2 = f\cdot g_2 &\implies \deg_{x_1}f = 0. 
\end{align*}
$$

This means that $$f$$ is a unit. However, $$\langle x_1, x_2\rangle$$ doesn't contain any unit, which is a contradiction. Therefore, $$I$$ is not principal. ◼

---

## Euclidean Domain (ED)
### Definition (ED)
> A **Euclidean function** on an integral domain $$D$$ is a function $$\nu: D\backslash \{0\} \to \Bbb N\cup \{0\}$$ such that:
>
> **(EF1)** For all $$a, b\in D$$ with $$b\not =0$$, there exist $$q$$ and $$r$$ in $$D$$ such that 
>
> $$
> a=bq+r, \text{ with either } r=0 \text{ or } \nu(r)<\nu(b).
> $$
>
> **(EF2)** For all $$a, b\in D$$ with $$ab\not = 0$$, $$\nu(a)\le \nu(ab)$$.
>
> An integral domain $$D$$ is a **Euclidean domain** if there exists a Euclidean function **on $$D$$**.

**Examples of $$\nu$$**

- $$\nu(n) = \vert n\vert$$: $$\Bbb Z$$ is a Euclidean domain.
- $$\nu(f(x)) = \deg f(x)$$: $$\Bbb F[x]$$ is a Euclidean domain.

### Theorem (ED => PID)
> Every Euclidean domain $$D$$ is a PID.

#### Corollary (ED => UFD)
> Every Euclidean domain is a UFD.

**Proof hint**

Claim that $$I=\langle b\rangle$$, where $$b$$ has the minimum $$\nu$$ value in $$I$$.

### Theorem (use EF2)
> Let $$D$$ be a Euclidean domain with Euclidean function $$\nu$$. Then
>
> 1. $$\nu(1)$$ is minimal among all $$\nu(a)$$ for $$a\in D\backslash\{0\}$$.
> 2. $$u\in D$$ is a unit **iff** $$\nu(u)=\nu(1)$$.

**Proof**

By **[EF2](#definition-ed)**.

---

## Remark (comparison)

設 $$D$$ 為一 integral domain。

證明 $$D$$ 不是 UFD / PID 簡單（找反例：prime, irreducible）、證明 $$D$$ 是 ED 也簡單（找 function $$\nu$$）；但是反之卻很困難！這就是定義這麼多 domain 的原因。

具體來說，如果找不到 Euclidean function，就可以試著證明 $$D$$ 不是 UFD。

> 延伸：[Dedekind's Domain](https://en.wikipedia.org/wiki/Dedekind_domain)。