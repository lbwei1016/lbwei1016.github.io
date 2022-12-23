---
layout: page
title: Finite Field
usemathjax: true
tag: Abstract Algebra, Field
time: 2022/12/12
---

**Table of Content**
- [Propositions](#propositions)
- [Theorem (number of elements)](#theorem-number-of-elements)
  - [Corollary (power size)](#corollary-power-size)
  - [Corollary (vector space)](#corollary-vector-space)
  - [Remark](#remark)
- [Structure of Finite Fields](#structure-of-finite-fields)
  - [Theorem (finite makes simple)](#theorem-finite-makes-simple)
  - [Theorem (finite is never closed)](#theorem-finite-is-never-closed)
  - [Theorem (zero; closure)](#theorem-zero-closure)
  - [Theorem (exsistence)](#theorem-exsistence)
    - [Definition (derivation)](#definition-derivation)
      - [Lemma (operations)](#lemma-operations)
    - [**Proof**](#proof)
    - [Theorem (also a zero; power)](#theorem-also-a-zero-power)
  - [Remark](#remark-1)
  - [Theorem (Galois fields)](#theorem-galois-fields)
- [Cyclotomic Polynomials over Finite Fields](#cyclotomic-polynomials-over-finite-fields)
  - [Question](#question)


---

## Propositions
> 1. The characteristic $$\text{char}(F)$$ is either a **prime** or $$0$$.
> 2. If $$p = \text{char}(F)$$ is a **prime**, then $$F$$ can be regarded as a **field extension of $$\Bbb{Z}_p$$**. 
> 3. If $$\text{char}(F)=0$$, then $$F$$ can be regraded as a **field extension of $$\Bbb Q$$**.

**Proof** (prop. 1)

Suppose $$\text{char}(F) = n < \infty$$. If $$n$$ is composite, $$n=ab$$ for some $$a,b\in \Bbb{Z}^+$$. 

Then

$$
0 = n \cdot 1 = (a\cdot 1)(b \cdot 1).
$$

This implies that $$a = 0$$ or $$b = 0$$, which is a contradiction. Therefore, $$n$$ is either prime or $$0$$. ◼

**Proof** (prop. 2)

We know that $$\Bbb{Z}_p$$ is of characteristic $$p$$. Since $$\Bbb{Z}_p$$ is cyclic, it means that $$\Bbb{Z}_p$$ is the smallest field of characteristic $$p$$. Thus, $$\Bbb{Z}_p \le E$$. ◼


---

## Theorem (number of elements)
> Let $$E$$ be a finite extension of **degree $$n$$** over a finite field $$F$$. If $$F$$ has $$q$$ elements, then $$E$$ has **$$q^n$$ elements**.

**Proof**

[basis](../Q-algebraic-extension/#theorem-basis) + [unique expression](../P-field-extension/#theorem-unique-expression).

### Corollary (power size)
> If $$E$$ is a finite field of **characteristic $$p$$**, then the number of elements in $$E$$ is $$p^n$$ for some positive integer $$n$$.

> Check [proposition 2.](#propositions).

### Corollary (vector space)
> If $$E$$ is a vector sapce over $$F$$ whose dimension is $$n$$, then $$E \cong F^n$$.

### Remark

若要建構一有 $$p^n$$ 個元素的 field，就找一 irreducible polynomial $$f(x)$$ over $$\Bbb{Z}_p$$ of degree $$n$$。令 $$f(\alpha) = 0, \alpha \not \in \Bbb{Z}_p$$，所求的 field 就是 $$\Bbb{Z}_p(\alpha)$$！

---

## Structure of Finite Fields

### Theorem (finite makes simple)
> A **finite extension** $$E$$ of a **finite field** $$F$$ is a **simple extension** of $$F$$.

**Proof**

Let $$\alpha$$ be a generator of the multiplicative group $$E^\times$$. Then $$E=F(\alpha)$$. ◼

### Theorem (finite is never closed)
> **No** finite field is be algebraically closed.

**Proof**

Suppose $$F$$ and $$E$$ are two finite fields, and $$F\le E$$. We have

$$
[E:\Bbb Z_p] = [E:F][F:\Bbb Z_p].
$$

Since $$F, E$$ are both finite, $$[E:\Bbb Z_p]$$ and $$[F:\Bbb Z_p]$$ are finite, which implies that $$[E:F]$$ is finite as well. By this [lemma](../S-algebraic-closure/#lemma-finite-degree-implies-algebraic), there exists $$\alpha \in E$$ such that $$\alpha$$ is algebraic over $$F$$. Hence, $$F$$ is not algebraically closed. ◼

### Theorem (zero; closure)
> Let $$E$$ be a field of $$p^n$$ elements contained in $$\overline{\Bbb{Z}}_p$$. Then the elements of $$E$$ are **precisely** the **zeros of $$x^{p^n}-x$$** in $$\overline{\Bbb{Z}}_p$$.

**Proof**

There are $$p^n-1$$ elements in $$E^\times$$. By [Lagrange's theorem](../F-Lagrange-thm), every nonzero element of $$E$$ is a zero of $$x^{p^n-1}-1$$. Thus, every elements if $$E$$ is a zero of $$x^{p^n}-x = x(x^{p^n-1}-1)$$.

On the other hand, since $$\overline{\Bbb Z}_p$$ is a field, a polynomial of degree $$p^n$$ has at most $$p^n$$ zeros. 

Therefore the theorem is proved. ◼

### Theorem (exsistence)
> A finite field of $$p^n$$ elements exists for **every** prime power $$p^n$$.

Here, we shall show that the converse of [this theorem](#theorem-zero-closure) is true, i.e., the set $$S$$ containing zeros of $$x^{p^n}-x$$ in $$\overline{\Bbb Z}_p$$ forms a field of $$p^n$$ elements. Note that since $$\overline{\Bbb Z}_p$$ is algebraically closed, $$x^{p^n}-x$$ **factors completely into linear factors** over $$\overline{\Bbb Z}_p$$. We will show 

- The zeros of $$x^{p^n}-x$$ are all distinct so that $$S$$ has $$p^n$$ elements.
- $$S$$ is a subdoamin in $$\overline{\Bbb Z}_p$$. Since $$S$$ is finite, this implies that $$S$$ is a field.

Before our proof begins, let's define an useful property.

#### Definition (derivation)
> Let $$F$$ be a field. The map $$D: F[x]\to F[x]$$ defined by $$D(a_0+a_1x\cdots+a_nx^n) = a_1+2a_2x + \cdots+na_nx^{n-1}$$ is called the **derivation**, and $$D(f(x))$$ is called the **derivative** of $$f(x)$$.

> 形式上的微分！

##### Lemma (operations)
> Let $$F$$ be a field. The derivation $$D$$ on $$F[x]$$ satisfies
>
> - $$D(f+g) = D(f) + D(g)$$.
> - $$D(fg) = gD(f) + fD(g)$$.

Here we go.

#### **Proof**

**1. zeros are distinct**

Suppose that $$\alpha$$ is a repeated zero of $$x^{p^n}-x$$, say, $$x^{p^n}-x = (x-\alpha)^2g(x)$$ for some $$g(x)\in \overline{\Bbb Z}_p[x]$$. We have

$$
D((x-\alpha)^2g(x)) = 2(x-\alpha)g(x) + (x-\alpha)^2D(g(x)),
$$

and thus $$\alpha$$ is also a zero of 

$$
D((x-\alpha)^2g(x)) = D(x^{p^n}-x) = p^nx^{p^n-1}-1.
$$

However, since $$\alpha$$ is a zero of $$x^{p^n}-x = x(x^{p^n-1}-1)$$, $$\alpha^{p^n-1} = 1$$. And since $$\text{char}(\overline{\Bbb Z}_p) = p$$, i.e. $$p\cdot 1 = 0$$, we have $$p^n\alpha^{p^n-1} = 0$$. That is, 

$$
D((x-\alpha)^2g(x)) = -1,
$$

which is a contradiction. Therefore, $$x^{p^n}-x$$ has no repeated root. 

**2. $$S$$ is a sundomain**

Recall that any subring of a field is a subdomain. Thus it suffices to show that $$S$$ is a subring; we know that $$a\in S$$ if $$a^{p^n} = a$$. 

<ins>additive identity</ins>

$$0^{p^n} = 0$$. Thus $$0 \in S$$.

<ins>closed</ins>

Let $$\alpha$$ and $$\beta$$ be two elements in $$S$$.

Recall that $$p \mid {p \choose k}$$ for all $$1\le k \le p-1$$. Since $$p\cdot 1 = p = 0$$, for $$k$$ in that range we have

$$
{p\choose k}u^kv^{p-k} = 0,
$$

for all $$u, v \in \overline{\Bbb Z}_p$$. This means that $$(u+v)^p = u^p + v^p$$ for all $$u, v \in \overline{\Bbb Z}_p$$, and thus

$$
(\alpha+\beta)^{p^n} = ((\alpha+\beta)^p)^{p^{n-1}} = (\alpha^p + \beta^p)^{p^{n-1}} = \cdots = \alpha^{p^n} + \beta^{p^n} = \alpha + \beta.
$$

Therefore, $$\alpha+\beta \in S$$.

On the other hand, closedness of multiplication is easily proved, which is omitted here.

<ins>additive inverse</ins>

Suppose $$\alpha \in S$$. If $$p=2$$, then $$-\alpha=\alpha \in S$$. Otherwise, $$p$$ is odd and 

$$
(-\alpha)^{p^n} = -\alpha^{p^n} = -\alpha,
$$

which means $$-\alpha\in S$$. ◼

#### Theorem (also a zero; power)
> Let $$\alpha \in \Bbb{Z}_p$$ be a zero of $$f(x)$$ in $$\overline{\Bbb Z}_p$$. Then $$\alpha^p$$ is also a zero of $$f(x)$$.

**Proof**

Let $$f(x) = \sum_{i=0}^n a_ix^i$$, where $$a_i\in \Bbb{Z}_p$$. This means that $$a_i^p = a_i$$ for all $$i \in \{0, 1, \cdots, (n-1)\}$$. Then

$$
0 = \big(f(\alpha) \big)^p = \Big(\sum_{i=0}^n a_i\alpha^i\Big)^p.
$$

By the same argument of the <ins>closed</ins> part in the previous proof, we have

$$
\Big(\sum_{i=0}^n a_i\alpha^i\Big)^p = \sum_{i=0}^n a_i^p\alpha^{pi} = \sum_{i=0}^n a_i\alpha^{pi} = f(\alpha^p) = 0. \tag*{$\blacksquare$}
$$

### Remark

綜合以上兩 theorem，對於任意 prime power $$p^n$$，存在**唯一**的 finite field，其包含 $$p^n$$ 個 $$\overline{\Bbb Z}_p$$ 中的元素，稱為 the **Galois field**，以 $$\Bbb{F}_{p^n}$$ 或 $$GF(p^n)$$ 表示。

### Theorem (Galois fields)
> Let $$F$$ be a field of $$p^n$$ elements. Then $$F \cong \Bbb{F}_{p^n}$$.

**Proof**

Let $$\alpha$$ be a generator of $$F^\times$$ and $$\alpha'$$ be a zero of $$f(x) = \text{Irr}(\alpha, \Bbb{Z}_p)$$ in $$\overline{\Bbb Z}_p$$. Then

$$
F = \Bbb{Z}_p(\alpha) \cong \Bbb{Z}_p[x]\Big/f(x)\Bbb{Z} _p[x] \cong \Bbb{Z}_p(\alpha') = GF(p^n). ◼
$$

> 參考 [Field extension](../P-field-extension/#remark-3)。

---

## Cyclotomic Polynomials over Finite Fields

> See [More on cyclotomic polynomials](../O-poly-factorization/#more-on-cyclotomic-polynomials).

Recall that $$n$$-th cyclotomic polynomial is defined to be

$$
\Phi_p(x) = \prod_{\ \ \ \ a\in\mathbb{C}^\times \\ \text{ord}(a) = n} (x-a),
$$

which can be computed inductively using the formula

$$
x^n - 1 = \prod_{d\mid n}\Phi_d(x).
$$

If we replace $$\Bbb C$$ by $$\overline{\Bbb Z}_p$$ in the definition of $$\Phi_n(x)$$ (and denote the resulted function as $$\Phi_{n,p}(x)$$), then the above formula still **holds if $$p\not \mid n$$**. Especially, the above formula shows that when $$\text{char}(F)=p$$, then $$\Phi_{n, p}(x) \in \Bbb{Z}_p[x]$$. Moreover, we also have $$\Phi_n(x) \equiv \Phi_{n,p}(x) \pmod p $$, given $$p\not \mid n$$.

> What if $$p \mid n$$?

Let us denote $$\Phi_{n, p}(x)$$ still by $$\Phi_n(x)$$ for short. For $$GF(16)^\times$$, its elements are zeros of $$x^{15}-1$$. By the above formula, we have

$$
x^{15}-1 = \Phi_1(x)\Phi_3(x)\Phi_5(x)\Phi_{15}(x).
$$

Moreover, over $$\Bbb{Z}_2$$, we have

$$
\begin{align*}
\Phi_1(x) &= x - 1 \\
\Phi_3(x) &= x^2 + x + 1\\
\Phi_5(x) &= x^4 + x^3 + x^2 + x + 1 \\
\Phi_{15}(x) &= (x^4+x+1)(x^4+x^3+1) .
\end{align*}
$$

Therefore, there are exactly **three** irreducible monic polynomials of degree $$4$$. Besides, zeros of $$x^4 + x^3 + x^2 + x + 1$$ are of multiplicative order $$5$$, and zeros of $$x^4+x+1$$ and $$x^4+x^3+1$$ are of multiplicative order $$15$$.

> How to find the order of those zeros?

Now if $$\alpha$$ is a zero of $$x^4+x+1$$, then

$$
\Bbb{Z}_2(\alpha)^\times = \{1, \alpha, \cdots, \alpha^{14}\} \cong \Bbb{Z}_{15}.
$$

The elements of order $$3$$ are $$\alpha^5$$ and $$\alpha^{10}$$, which implies that 

$$
x^2 + x + 1 = (x-\alpha^5)(x-\alpha^{10}).
$$

Similarly, the elements of order $$5$$ are $$\alpha^3, \alpha^6, \alpha^9$$ and $$\alpha^{12}$$, which implies that 

$$
x^4+x^3+x^2+x+1 = (x-\alpha^3) (x-\alpha^6) (x-\alpha^9 )(x-\alpha^{12}).
$$

For elements of order $$15$$, they are $$\{1,2,4,7,8,11,13,14 \}$$, and they can be divided into two subsets: $$\{1,2,4,8 \}$$ and $$\{7, 14, 13, 11\}$$. We can see that 

$$
1 \xrightarrow[]{\times 2}2 \xrightarrow[]{\times 2}4 \xrightarrow[]{\times 2}8,
$$

and

$$
7 \xrightarrow[]{\times 2}14 \xrightarrow[]{\times 2}13 \xrightarrow[]{\times 2}11,
$$

modulo $$15$$. Then

$$
x^4+x+1 = (x-\alpha)(x-\alpha^2)(x-\alpha^4)(x-\alpha^8), \\
x^4+x^3+1 = (x-\alpha^7)(x-\alpha^{14})(x-\alpha^{13})(x-\alpha^{11}).
$$

But how are they factored?

### Question

綜合以上定義與觀察，回答

- What if $$p \mid n$$?
- How to find the order of those zeros?
- But how they are factored?
  - Why different irreducible polynomials have **distinct** linear factors?

並試圖歸納以上理論！

---