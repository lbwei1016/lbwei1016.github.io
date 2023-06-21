---
layout: page
title: Rings and Fields
usemathjax: true
tag: Abstract Algebra, Ring, Field
time: 2022/11/03
---

**Table of Content**
- [Ring](#ring)
  - [Definition (ring)](#definition-ring)
  - [Examples](#examples)
  - [Some Little Definitions](#some-little-definitions)
- [Definition (about multiplication)](#definition-about-multiplication)
- [Field](#field)
  - [Remark](#remark)
- [Subrings and Subfields](#subrings-and-subfields)
- [Homomorphism](#homomorphism)
  - [Definition (homomorphism)](#definition-homomorphism)
  - [Proposition (one-to-one)](#proposition-one-to-one)
  - [Theorem (subring)](#theorem-subring)
  - [Definition (endomorphism)](#definition-endomorphism)
    - [Theorem (endomorphism ring)](#theorem-endomorphism-ring)
    - [Example $$I$$](#example-i)
    - [Example $$II$$](#example-ii)
- [Isomorphism](#isomorphism)
  - [Example $$I$$](#example-i-1)
  - [Example $$II$$](#example-ii-1)
  - [Example $$III$$](#example-iii)
- [Application](#application)
  - [Chinese Remainder Theorem](#chinese-remainder-theorem)
    - [Theorem (CRT)](#theorem-crt)

---

## Ring
### Definition (ring)
> A **ring** $$\langle R,+,\cdot \rangle$$ is a set $$R$$ together with two binary operations $$+$$ and $$\cdot$$, called **addition** and **multiplication**, such that the following axioms are satisfied:
> - $$\langle R,+\rangle$$ is an *abelian* group.
> - Multiplication is associative.
> - For all $$a,b,c\in R$$, the **left distributive law** $$a\cdot(b+c) = (a\cdot b)+(a\cdot c)$$ and the **right distributive law** $$(a+b)\cdot c = (a\cdot c) + (b\cdot c)$$ hold. 

> Ring 可以**沒有**乘法單位元素（unity）！如果有，叫 *a ring with unity*。

### Examples

- $$\mathbb{Z}_n$$ is a ring with $$\bar a + \bar b = \overline{a+b}$$ and $$\bar a \cdot \bar b = \overline{a\cdot b} $$.
- $$M_n(\mathbb{R})$$ of all $$n\times n$$ matrices is a ring.
- Let $$R_1$$ and $$R_2$$ be rings. The *direct product* of $$R_1$$ and $$R_2$$, $$R_1 \times R_2$$, is a ring, where $$+$$ and $$\cdot$$ are defined elementwise.
- Let $$\text{End}(V)$$ be the set of *all linear transformations from $$V$$ to $$V$$*. Let addition and multiplication be defined by 

$$
f+g: v\to f(v) + f(g),\ f\circ g: v\to f(g(v)).
$$

  Then $$\langle \text{End}(V), +, \circ \rangle$$ is a ring called the **endomorphism ring of $$V$$**.

### Some Little Definitions

- By convention we set $$0 \cdot a = 0_R$$, where the $$0$$ on the left-hand side is the integer $$0$$, while $$0_R$$ on the right is the **additive identity** element of $$R$$.

- A ring with a multiplicative identity $$1_R$$ is a **ring with unity**.

---

## Definition (about multiplication)

Let $$R$$ be a ring with unity $$1\not = 0$$.

1. An element $$u$$ of $$R$$ is a **unit** if it has a multiplicative inverse.
2. If every nonzero element of $$R$$ is a unit, then $$R$$ is a **division ring** (or **skew field**).

## Field

A *commutative division ring* is a **field**.

> **Field** 在這裡終於出現了！

### Remark

1. multiplicative **identity** element and **inverse(s)** are both **unique**.
2. For a ring $$R$$ with unity, the set of units forms a multiplicative group, denoted by $$R^{\times}$$, called **the group of units**.

What if $$1_R = 0_R$$? If that is the case, let $$1_R=0_R=e$$. For any $$a\in R$$, we have 

$$
a + e = a\cdot e = a, \\
a = a\cdot e = a(e-e) = e.
$$

Thus $$R = \{e\}$$, which is trivial.

---

## Subrings and Subfields

Let $$R$$ be a ring. A subset $$S$$ of $$R$$ is a subring of $$R$$ if

1. $$S$$ is closed under $$+_R$$ and $$\times_R$$,
2. for $$a$$ in $$S$$, $$-a$$ is also in $$S$$,
3. $$0_R\in S$$, (or equivalently, $$S$$ is non-empty)

which is denoted by $$S<R$$.

> 可以先說明 the additive identity of $$R$$ is ...（例如零矩陣 $$O$$），再說明 $$O$$ 在 $$S$$ 中。

> Subfield 多說明 $$a^{-1}$$ 也在其中。

---

## Homomorphism
### Definition (homomorphism)

> For rings $$R$$ and $$R'$$, $$\phi: R\to R'$$ is a (ring) homomorphism if 
> 1. $$\phi(a+b) = \phi(a) + \phi(b)$$,
> 2. $$\phi(ab) = \phi(a)\phi(b)$$.
> 
> for all $$a,b \in R$$.

The **kernel** of $$\phi$$ is

$$\text{ker}(\phi) = \{a\in R\vert \phi(a) = 0\}.$$

> 映到加法單位元素才是 kernel！

### Proposition (one-to-one)
> A ring homomorphism is **one-to-one** if and only if its kernel is $$\{0\}$$.

### Theorem (subring)
> Let $$\phi: R\to R'$$ be a ring homomorphism. Then $$\phi(R)$$ is a **subring** of $$R'$$.

### Definition (endomorphism)
> Let $$G$$ be a group. A homomorphism **from $$G$$ to itself** is an **endomorphism**.

#### Theorem (endomorphism ring)
> Let $$(G,+)$$ be an **abelian** group. The set $$\text{End}(G)$$ of **all endomorphisms of $$G$$ forms a ring** under function addition and function composition.

#### Example $$I$$

The function $$\phi: \mathbb{Z}\to \mathbb{Z}_n$$ defined by $$\phi(a) = \bar a$$ is a ring homomorphism.

> 加法和乘法都要檢查！

#### Example $$II$$

Let $$R = \mathbb{Q}[x]$$ be *the set of all polynimails* over $$\mathbb{Q}$$. Given $$a\in \mathbb{R}$$, define $$\phi_a:\mathbb{Q}[x]\to \mathbb{R} $$ by

$$
\phi_a(f(x)) = f(a).
$$

Then $$\phi_a$$ is an [evalutation homomorphism](../rings-of-polynomials/#evaluation-homomorphism).

For $$a=\sqrt{2}$$, we have

$$
\mathbb{Q}[\sqrt{2}] := \phi_{\sqrt{2}}(\mathbb{Q}[x]) = \{f(\sqrt{2})\vert f[x]\in\mathbb{Q}[x] \},
$$

which is a **subring** of $$R$$.

> $$\mathbb{Q}[\sqrt{2}]$$ 不再是多項式的集合，而是數值的集合。

---

## Isomorphism

一如往常：
1. ring homomorphism
2. one-to-one
3. onto

### Example $$I$$

$$
\rho: \mathbb{Z}_{mn} \to \mathbb{Z}_n\times \mathbb{Z}_m
$$

given by $$\rho(\bar a) = (\bar a, \bar a)$$ is a **group isomorphism** and is also a **ring isomorphism**.

### Example $$II$$

Let $$\alpha$$ be a basis of $$n$$-dimensional vector space $$V$$ over $$F$$. Then the matrix representation $$\text{Rep}_\alpha:\text{End}(V) \to M_n(F) $$ is a ring isomorphism.

> $$\text{End}(V)$$: see [this](#definition-endomorphism).

> 任意 linear trans. 都可以用矩陣表示！

### Example $$III$$

Regard $$\mathbb{C}$$ as a vector space over $$\mathbb{R}$$ with the basis $$\alpha = \{1, i\}$$. Consider the map 

$$
\rho: \mathbb{C} \to \text{End}(\mathbb{C})
$$

given by $$\rho(x) = \rho_x$$, and $$\rho_x(y) = \rho_xy$$.

> $$\rho_x$$ is a *linear tranformation*. 
 
It can be shown that $$\rho$$ is an injective ring homomorphism. Moreover, let

$$
\phi: \mathbb{C} \to \Bigg\{\begin{pmatrix}
  a & -b \\ b & a
\end{pmatrix} \Bigg\vert a, b \in \mathbb{R}\Bigg\} 
$$

given by 

$$
\phi(a+bi) = \begin{pmatrix}
  a & -b \\ b & a
\end{pmatrix},
$$

which is a ring isomorphism. We will show that $$\phi$$ is equal to $$\text{Rep}_{\alpha} \circ \rho$$. Note that for $$a,b \in \mathbb{R}$$,

$$
\rho_{a+bi}(1) = a\cdot 1 + b\cdot i, \\
\rho_{a+bi}(i) = -b\cdot 1 + a\cdot i.
$$

> 記得 $$\rho_{a+bi}$$ 是線性變換！而 $$1$$ 和 $$i$$ 是 basis 中的 vector。

Therefore, 

$$
\text{Rep}_\alpha(\rho_{a+bi}) = \begin{pmatrix}
  a & -b \\ b & a
\end{pmatrix} = \phi(a + bi).
$$

> $$\rho_{a+bi} = \rho(a+bi)$$.

> 將 basis 從 $$\{1, i\}$$ 變換到 $$\{\rho_{a+bi}(1), \rho_{a+bi}(i) \}$$。

---

## Application
### Chinese Remainder Theorem
For two positive coprime integers $$m$$ and $$n$$, we have a ring isomorphism

$$
\begin{align*}
\rho: \Bbb Z_{mn} &\to \Bbb Z_m \times \Bbb Z_n \\
x \bmod{mn} &\mapsto (x\bmod m, x\bmod n).
\end{align*}
$$

This means that the system of congruent equation

$$
\begin{cases}
  x \equiv a \bmod m \\
  x \equiv b \bmod n
\end{cases}
$$

has a **unique solution upto a multiple of $$mn$$**. To solve this, it is sufficient to find

$$
x_1 = \rho^{-1}(1, 0), x_2 = \rho^{-1}(0, 1),
$$

which are called the **fundamental solutions**. Then we have

$$
\rho^{-1}(a, b) = ax_1 + bx_2.
$$

Since $$x_1\equiv 0 \bmod n$$, we can write $$x_1=kn$$ for some integer $$k$$. Thus, 

$$
x_1 = kn \equiv 1 \bmod m.
$$

This implies that $$k$$ is the multiplicative inverse of $$n$$ modulo $$m$$, which can be [solved easily](../../Concrete-Math/extgcd). Generalize it, we have the following theorem:

#### Theorem (CRT)

Consider the system of equations

$$
\begin{cases}
  x &\equiv a_1 \bmod b_1 \\
  x &\equiv a_2 \bmod b_2 \\
  &\vdots\\
  x &\equiv a_k \bmod b_k
\end{cases}
$$

> If any pair of $$b_1, \cdots b_k$$ are **coprime**, then the above equation has a **unique solution** upto a multiple of $$b_1\cdots b_k$$. Moreover, if $$x_1,\cdots,x_k$$ are fundamental solutions, the **general solution** is 
>
> $$
> a_1x_1 + \cdots a_kx_k \pmod {b_1\cdots b_k}.
> $$