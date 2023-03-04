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
  - [Theorem (subfield)](#theorem-subfield)
  - [Corollary (factorization)](#corollary-factorization)
    - [Exercise I](#exercise-i)
    - [Exercise II](#exercise-ii)
    - [Exercise III](#exercise-iii)
    - [Remark](#remark-2)
- [Summary](#summary)


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

[basis](../algebraic-extension/#theorem-basis) + [unique expression](../field-extension/#theorem-unique-expression).

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
> **No** finite field is algebraically closed.

**Proof**

Suppose $$F$$ and $$E$$ are two finite fields, and $$F\le E$$. We have

$$
[E:\Bbb Z_p] = [E:F][F:\Bbb Z_p].
$$

Since $$F, E$$ are both finite, $$[E:\Bbb Z_p]$$ and $$[F:\Bbb Z_p]$$ are finite, which implies that $$[E:F]$$ is finite as well. By this [lemma](../algebraic-closure/#lemma-finite-degree-implies-algebraic), there exists $$\alpha \in E$$ such that $$\alpha$$ is algebraic over $$F$$. Hence, $$F$$ is not algebraically closed. ◼

### Theorem (zero; closure)
> Let $$E$$ be a field of $$p^n$$ elements contained in $$\overline{\Bbb{Z}}_p$$. Then the elements of $$E$$ are **precisely** the **zeros of $$x^{p^n}-x$$** in $$\overline{\Bbb{Z}}_p$$.

**Proof**

There are $$p^n-1$$ elements in $$E^\times$$. By [Lagrange's theorem](../Lagrange-thm), every nonzero element of $$E$$ is a zero of $$x^{p^n-1}-1$$. Thus, every elements if $$E$$ is a zero of $$x^{p^n}-x = x(x^{p^n-1}-1)$$.

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
> Let $$\alpha$$ be a zero of $$f(x)\in \Bbb Z_p[x]$$ in $$\overline{\Bbb Z}_p$$. Then $$\alpha^p$$ is also a zero of $$f(x)$$.

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

> 參考 [Field extension](../field-extension/#remark-3)。

---

## Cyclotomic Polynomials over Finite Fields

> See [More on cyclotomic polynomials](../poly-factorization/#more-on-cyclotomic-polynomials).

Recall that $$n$$-th cyclotomic polynomial is defined to be

$$
\Phi_p(x) = \prod_{\substack{a\in\mathbb{C}^\times \\ \text{ord}(a) = n}} (x-a),
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

> Because of this [corollary](#corollary-factorization), $$\Phi_{15}(x)$$ must be factored into irreducible polynomials of degree $$1, 2$$ or $$4$$.

Therefore, there are exactly [three](#exercise-i) irreducible monic polynomials of degree $$4$$ over $$\Bbb Z_2$$. Besides, zeros of $$x^4 + x^3 + x^2 + x + 1$$ are of multiplicative order $$5$$, and zeros of $$x^4+x+1$$ and $$x^4+x^3+1$$ are of multiplicative order $$15$$.

> Q: How to find the order of those zeros?
> 
> A: This is by [definition](../poly-factorization/#more-on-cyclotomic-polynomials). (See the substack of $$\prod$$.) To it state explicitly: All the zeros of $$\Phi_n(x)$$ are of degree $$n$$. (any [exceptions](#exercise-iii)?)

Now if $$\alpha$$ is a zero of $$x^4+x+1$$, then

$$
\Bbb{Z}_2(\alpha)^\times = \{1, \alpha, \cdots, \alpha^{14}\} \cong \Bbb{Z}_{15}.
$$

> 因為 $$\alpha$$ 的 order 是 $$15$$，所以他是 $$\Bbb Z_2(\alpha)^\times$$ 的 generator！

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
  - By definition.
- But how are they factored?
  - Why different irreducible polynomials have **distinct** linear factors?
    - Because $$x^{p^n}-x$$ has no repeated root, and cyclotomic polynomials are factors of $$x^{p^{n-1}}-1$$. (See the proof of this [theorem](#theorem-exsistence).)

並試圖歸納以上理論！

### Theorem (subfield)
> In $$\overline{\Bbb Z}_p$$, $$\Bbb{F}_{p^m}$$ is contained in $$\Bbb{F}_{p^n}$$ iff $$m\mid n$$.

**Proof**

Suppose $$\Bbb{F}_{p^m} \le \Bbb{F}_{p^n}$$. Then

$$
n = [\Bbb{F}_{p^n}:\Bbb{Z}_p]=[\Bbb{F}_{p^n}:\Bbb{F}_{p^m}][\Bbb{F}_{p^m}:\Bbb{Z}_p] = m[\Bbb{F}_{p^n}:\Bbb{F}_{p^m}].
$$

Thus $$m\mid n$$.

Conversely, assume that $$m \mid n$$. It suffice to prove that if $$\alpha\in \overline{\Bbb Z}_p $$ is a zero of $$x^{p^m}-x$$, then it is also a zero of $$x^{p^n}-x$$.

For all $$\alpha\in \Bbb{F}_{p^m}$$, we have $$\alpha^{p^m} = \alpha$$. Then

$$
\alpha^{p^n} = (\alpha^{p^m})^{p^{n-m}} = \alpha^{p^{n-m}} = \cdots.
$$

Since $$m\mid n$$, we eventually arrive at $$\alpha^{p^n}=\alpha$$. ◼

### Corollary (factorization)
> The polynomial $$x^{p^n}-x$$ is equal to the **product of all monic irreducible polynomials** over $$\Bbb{Z}_p$$ with degree **$$d$$ dividing $$n$$**.

**Proof**

Let $$f(x)$$ be a monic irreducible polynomial of degree $$d$$ over $$\Bbb{Z}_p$$, with $$d\mid n$$ and $$\beta$$ be its zero in $$\overline{Z}_p$$. Since $$d\mid n$$, we have

$$
\Bbb{Z}_p(\beta) = \Bbb{F}_{p^d} \le \Bbb{F}_{p^n}.
$$

Therefore, $$\beta$$ is a zero of $$x^{p^n}-x$$, which implies that $$f(x)\mid x^{p^n}-x$$. 

Conversely, let $$f(x)$$ be a monic irreducible factor of $$x^{p^n}-x$$ of degree $$d$$, with a zero $$\beta$$ in $$\overline{\Bbb Z}_p$$. Since $$\beta$$ is also a zero of $$x^{p^n}-x$$, we have $$\beta \in \Bbb{F}_{p^n}$$. Thus, 

$$
\Bbb{F}_{p^d} = \Bbb{Z}_p(\beta) \le \Bbb{F}_{p^n},
$$

and then we conclude that $$d\mid n$$. ◼

> 先證所有 $$d\mid n$$ 都是 factor，再證所有 factor 都 $$d\mid n$$！

#### Exercise I

> Find the product of monic irreducible polynomials of degree four over $$\Bbb Z_3 $$.

We know that $$x^{3^4}-x$$ is equal to the product of all monic irreducible polynomials over $$\Bbb Z_3$$ with degree $$d$$ dividing $$4$$, i.e. $$1, 2$$ and $$4$$. However we only need the product of those of degree $$4$$, which is

$$
{x^{3^4}-x\over x^{3^2}-x} = {x^{81}-x\over x^{9}-x} = x^{72} + x^{64} + \cdots + 1. \tag*{$\blacksquare$}
$$

#### Exercise II
> Show that $$\Phi_{11}(x)$$ is irreducible over $$\Bbb Z_3$$.

Suppose $$\alpha$$ is a zero of $$\Phi_{11}(x)$$. By definition, the order of $$\alpha$$ is $$11$$.

Then, suppose $$[\Bbb Z_3(\alpha):\Bbb Z_3] = d$$, which can only be one of $$1, 2, 5$$ and $$10$$, since [all the irreducible factors of a cyclotomic polynomial have the same degree](https://math.stackexchange.com/questions/3945405/showing-that-the-irreducible-factors-of-the-cyclotomic-polynomial-in-mathbbq). By Lagrange's Theorem, $$\vert \langle \alpha \rangle\vert$$ divides $$\vert \Bbb{Z}_3(\alpha)^\times\vert$$, which is to say

$$
11 \mid 3^d-1.
$$

After some calculation, we can discover that only when $$d=10$$, $$11$$ is a factor of $$3^d-1$$. Thus $$[\Bbb Z_3(\alpha):\Bbb Z_3] = 10$$ and $$\Phi_{11}(x)$$ is irreducible over $$\Bbb Z_3$$. ◼

> In general, $$\Phi_{n}(x)$$ is irreducible over $$\Bbb Z_p$$ iff **$$p$$ is a generator of $$\Bbb Z_n^\times$$**.

#### Exercise III
> Check whether $$\Phi_9(x)$$ is irreducible over $$\Bbb Z_3$$.

First note that $$\deg\Phi_9(x) = 6$$. Suppose $$\alpha$$ is a zero of $$\Phi_9(x)$$, and suppose $$[\Bbb Z_3(\alpha): \Bbb Z_3] = d$$. Then by Lagrange's Theorem, we have $$9 \mid 3^d - 1$$, where $$d=1, 2, 3$$ or $$6$$. Unfortunately, none of the values fit. How? Let's then try to factorize $$\Phi_9(x)$$ over $$\Bbb Z_3$$.

$$\Phi_9(x) = x^6 + x^3 + 1 = x^6 -2x^3 + 1$$. After some more calculations, we have

$$
\Phi_9(x) = (x-1)^6,
$$

which yields that $$\alpha = 1\in \Bbb Z_3$$! It turns out that our belief in "$$\text{ord}(\alpha) = 9$$" is incorrect. This is because $$3\mid 9$$, which violates our assumption that $$p\not \mid n$$ [here](#cyclotomic-polynomials-over-finite-fields).

In this case, $$\Phi_9(x)$$ is indeed reducible over $$\Bbb Z_3$$. ◼

#### Remark

在[這裡](../field-extension/#remark-2)，我們說明了對於 field extension，加入 generator 是比較好的。但是如何找到 a zero $$\alpha$$ of an irreducible polynomial $$f(x)$$，使得 $$\alpha$$ 是 generator？

如果 $$\alpha$$ 是 generator，則 $$\alpha$$ 的 order 必須是 $$p^n-1$$，等同於，$$\alpha$$ 是 $$\Phi_{p^n-1}(x)$$ 的 zero 之一；也就是說，$$f(x)$$ 必須是 $$\Phi_{p^n-1}(x)$$ 的不可約因式之一。

於是，做體擴張的時候都選 $$\Phi_{p^n-1}(x)$$ 的 zero 加入，就保證是 generator 了！

---

## Summary

Every finite field $$F$$ is a finite **extension of $$\Bbb Z_p$$** in $$\overline{\Bbb Z}_p$$, and $$\vert F\vert = p^n$$ where $$n=[F:\Bbb Z_p]$$.

To construct $$\Bbb F_{p^n}$$, we have to find an irreducible polynomial $$f(x)$$ of degree $$n$$ over $$\Bbb Z_p$$. Then, $$\Bbb Z_p(\alpha)$$ is the desired field where $$\alpha$$ is a zero of $$f(x)$$ in $$\overline{\Bbb Z}_p$$.
