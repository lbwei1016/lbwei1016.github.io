---
layout: page
title: Rings of Polynomials
usemathjax: true
tag: Abstract Algebra, Polynomial, Field
time: 2022/11/20
---

**Table of Content**
- [Definition (polynomial)](#definition-polynomial)
- [Theorem (operation)](#theorem-operation)
  - [Corollary (integral domain)](#corollary-integral-domain)
    - [Proof A](#proof-a)
    - [Proof B](#proof-b)
  - [Remark A](#remark-a)
  - [Remark B](#remark-b)
  - [Remark C](#remark-c)
  - [Remark D](#remark-d)
    - [Theorem (degree)](#theorem-degree)
- [Theorem (First Ring Isomorphism Theorem)](#theorem-first-ring-isomorphism-theorem)
  - [Evaluation Homomorphism](#evaluation-homomorphism)
  - [Ring Extension (finitely generated commutative ring)](#ring-extension-finitely-generated-commutative-ring)
  - [Zeros of a Polynomial](#zeros-of-a-polynomial)
    - [Definition (zeros)](#definition-zeros)
- [Division Algorithm of Polynomials](#division-algorithm-of-polynomials)
  - [Theorem (division algorithm)](#theorem-division-algorithm)

---

## Definition (polynomial)
> Let $$R$$ be a ring. A **polynomial $$f(x)$$ over $$R$$** is a **formal sum** 

$$
\sum_{i=0}^\infty a_ix^i = a_0 + a_1x + \cdots + a_nx^n + \cdots,
$$

where $$a_i \in R$$, and $$a_i = 0$$ for all but a finite number of values of $$i$$.

> **Formal sum** 代表「$$+$$」只是形式上的，不能實際代值到 indeterminate $$x$$ 中，也就是不能 *evaluate*。

> "$$a_i = 0$$ for all **but** a finite number of values of $$i$$" ：除了有限個 $$i$$ **之外**，其他 $$a_i$$ 都等於 $$0$$；意思就是**幾乎** *for all*。

> [Generating function](../../Concrete-Math/Generating-Functions/)！

---

## Theorem (operation)
> Let $$R$$ be a ring. Let $$f(x) = \sum_{i=0}^\infty a_ix^i$$ and $$g(x) = \sum_{i=0}^\infty b_ix^i$$ be two polynomials over $$R$$. Define addition and multiplication by

$$
f(x) + g(x) = \sum_{i\ge 0} (a_i+b_i)x^i, \\
f(x)g(x) = \sum_{n\ge 0}\Big(\sum_{i=0}^na_ib_{n-i} \Big)x^n.
$$

> Then the set $$R[x]$$ of **all polynomials** over $$R$$ is a **ring** under these two operations. Furthermore, if $$R$$ is *commutative*, then **so is** $$R[x]$$ (and vice versa); if $$R$$ is a ring with unity, then $$R[x]$$ **also** has the multiplicative identity $$1_{R[x]}$$, which is identical to $$1_R$$.

### Corollary (integral domain)
> If $$D$$ is an integral domain, then so is $$D[x]$$.

#### Proof A

For two polynomials $$f(x),g(x)\in D$$, if $$f(x)g(x) = 0$$, then

$$
S_n = \sum_{i=0}^na_ib_{n-i}=0,\ \forall n \ge 0,
$$

where $$a_i$$ and $$b_i$$ are the coefficients of $$f$$ and $$g$$, respectively.

Let's start off with $$n=0$$: $$a_0b_0=0$$. Since $$D$$ has no zero divisors, this implies that either $$a_0$$ or $$b_0$$ is zero. If we continue evaluating $$S_n$$ from smaller $$n$$ to larger ones, we can reduce $$S_n$$ to the following form:

$$
S_n = a_kb_{n-k}, \text{ for some } k, 0\le k \le n,
$$

since there must be $$n$$ zeros among $$\{a_0,\cdots,a_{n-1}\}$$ and $$\{b_0, \cdots,b_{n-1} \}$$. 

Now suppose neither $$f(x)$$ nor $$g(x)$$ is a zero polynomial. For $$i,j \in \mathbb{N}$$, there exist $$a_i$$ and $$b_j$$ such that $$a_i \not=0 $$ and $$b_j\not =0$$. Then from the above observation, we must have

$$
S_{i+j} = a_ib_j = 0.
$$

However, this violates the fact that $$D$$ is an integral domain since both $$a_i$$ and $$b_j$$ are in $$D$$. This contradiction means that either $$f$$ or $$g$$ is zero, i.e. $$D[x]$$ is an integral domain. ◼

#### Proof B

First define that the degree of the zero polynomial is $$-\infty$$. 

Suppose $$\deg f(x)=n$$ and $$\deg g(x)=m$$. Then by [this theorem](#theorem-degree), we have

$$
\deg f(x)g(x) = \deg f(x) + \deg g(x),
$$

which holds even for the zero polynomial.

Now we can see that $$f(x)g(x)$$ is the zero polynomial only if at least one of them is the zero polynomial. Thus the statement holds. ◼

### Remark A

The ring $$R[x_1,\cdots,x_n]$$ of polynomials in $$n$$ indetreminates over $$R$$ can be defined as:

For all $$f(x_1,\cdots,x_n) \in R[x_1,\cdots,x_n]$$,

$$
f(x_1,\cdots x_n) = \sum_{i \ge 0}a_i\Big(\sum_{d_1+\cdots+d_n=i}x_1^{d_1}\cdots x_n^{d_n} \Big).
$$

### Remark B

Let $$F$$ be a field. The set $$F[x]$$ is not a field since the inverse of $$x$$, $$1/x$$, is not in $$F[x]$$. On the other hand, we can construct a field containing $$F[x]$$ as a subdomain: The [field of quotients](../L-fields-of-quotients) of $$F[x]$$ is $$F(x) = \{f(x)/g(x): f(x),g(x)\in F[x], g(x)\not=0 \}$$, called the **field of rational functions** in $$x$$ over $$F$$.

> 注意 notation！$$F(x)$$ 是 field，而 $$F[x]$$ 只是 integral domain（因為 $$F$$ 是 integral domain；by [theorem](../K-integral-domain/#theorem-fields-are-integral-domain) and [corollary](#corollary-integral-domain)）。

### Remark C

The addition and multiplication defined above still work well for polynomials of **infinite degree**, which are called **formal power series**.

### Remark D

For $$f(x), g(x)\in\mathbb{R}[x]$$, we have

$$
\deg f(x)g(x) = \deg f(x) + \deg g(x);
$$

however when $$R = \mathbb{Z}_4$$, the above equation is not necessarily valid. 

#### Theorem (degree)
> If $$R$$ is an integral domain, then 

$$
\deg f(x)g(x) = \deg f(x) + \deg g(x)
$$

> for all $$f(x), g(x)\in R[x]$$.

**Proof**

Suppose $$\deg f(x) = n$$ and $$\deg g(x) = m$$. This means that $$a_n\not=0$$ and $$b_m\not=0$$, where $$a_n$$ and $$b_n$$ are the coefficients of $$f(x)$$ and $$g(x)$$, respectively. Since $$R$$ is an integral domain, $$a_nb_m \not=0$$, and thus the equation holds. ◼

---

## Theorem (First Ring Isomorphism Theorem)
> Let $$\phi: R\to R'$$ be a ring homomorphism. Then $$R/\text{ker}\phi$$ has a canonical ring structure such that $$R/\text{ker}\phi \cong \phi(R)$$.

> The kernel of a ring homomorphism is called the **ideal**.

### Evaluation Homomorphism

Suppose $$R$$ is a subring of $$R'$$, and $$R'$$ is commutative. Then for $$\alpha \in R'$$, the ring homomorphism $$\phi_\alpha: R[x]\to R'$$ given by

$$
\phi_\alpha(a_0+a_1x+\cdots+a_nx^n) = a_0+a_1\alpha +\cdots+a_n\alpha^n
$$

is called **the evaluation homomorphism**. By the First Ring Isomorphism Theorem, we have

$$
R[x]/\text{ker}\phi_{\alpha} \cong \phi(R[x]) = R[\alpha].
$$

> 為什麼 $$R$$ 要是 $$R'$$ 的 subring？因為這樣 $$a_0+a_1\alpha +\cdots+a_n\alpha^n$$ 才保證在 $$R'$$ 中。

**Example**

Let $$R'$$ be a commutative ring with unity and characteristic $$n$$, and let $$R = \mathbb{Z}_n \cong \langle 1_{R'} \rangle$$. Then

$$
\mathbb{Z}_n/\text{ker}\phi_\alpha \cong \langle 1_{R'}, \alpha \rangle.
$$

> 見[此](../K-integral-domain/#theorem-subring-generated-by-the-unity)。

### Ring Extension (finitely generated commutative ring)

One can regard $$R[\alpha]$$ as an *extension* of $$R$$ by plugging in an element $$\alpha$$ from a larger ring $$R'$$. Then the above result just shows that *every ring extension of $$R$$ by a single element* is isomorphic to $$R[x]/I$$ for some ideal $$I$$ of $$R[x]$$. In general, a **finitely generated commutative ring** with unity and characteristic $$n$$ is isomorphic to

$$
\mathbb{Z}_n[x_1,\cdots,x_m]/I,
$$

where $$I$$ is an ideal of $$\mathbb{Z}_n[x_1,\cdots,x_m]$$.

### Zeros of a Polynomial

#### Definition (zeros)
> Let $$F$$ be a subfield of a field $$E$$. Let $$f(x)\in F[x]$$. Suppose that $$\alpha\in E$$ is an element such that $$f(\alpha)=0$$. Then $$\alpha$$ is a **zero** of $$f(x)$$ in $$E$$.

**Example**

Let $$F=\mathbb{Q}, E=\mathbb{R}$$ and $$f(x)=x^2-2$$. Then $$\pm\sqrt{2}$$ are zeros of $$f(x)$$ in $$\mathbb{R}$$.

--- 

## Division Algorithm of Polynomials
### Theorem (division algorithm)
> Let $$F$$ be a field, and $$f(x)$$ and $$g(x)$$ be polynomials in $$F[x]$$. Suppose that $$g(x)$$ is not the zero polynomial. Then there exist unique polynomials $$q(x)$$ and $$r(x)$$ such that 
> 
>1. $$f(x) = g(x)q(x) + r(x)$$,
>2. $$r(x)=0$$, or $$\deg  r(x) < \deg  g(x)$$.