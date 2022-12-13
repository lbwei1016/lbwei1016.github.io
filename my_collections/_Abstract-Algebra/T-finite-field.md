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
  - [Theorem (zero; closure)](#theorem-zero-closure)
  - [Theorem (exsistence)](#theorem-exsistence)
    - [Definition (derivation)](#definition-derivation)
      - [Lemma (operations)](#lemma-operations)
    - [**Proof**](#proof)
  - [Remark](#remark-1)
  - [Theorem (Galois fields)](#theorem-galois-fields)


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

Recall that $$p \mid {p \choose k}$$ for all $$1\le k \le p-1$$. Thus for $$k$$ in that range,

$$
{p\choose k}u^kv^{p-k} = ap\cdot v^p u^kv^{-k} = a(p\cdot v^p) u^kv^{-k} = 0,
$$

for all $$u, v \in \overline{\Bbb Z}_p$$ since $$v^p=1$$ and $$p\cdot 1 = 0$$. This means that $$(u+v)^p = u^p + v^p$$ for all $$u, v \in \overline{\Bbb Z}_p$$, and thus

$$
(\alpha+\beta)^{p^n} = ((\alpha+\beta)^p)^{p^{n-1}} = (\alpha^p + \beta^p)^{p^{n-1}} = \cdots = a^{p^n} + \beta^{p^n} = \alpha + \beta.
$$

Therefore, $$\alpha+\beta \in S$$.

On the other hand, closedness of multiplication is easily proved, which is omitted here.

<ins>additive inverse</ins>

Suppose $$\alpha \in S$$. If $$p=2$$, then $$-\alpha=\alpha \in S$$. Otherwise, $$p$$ is odd and 

$$
(-\alpha)^{p^n} = -\alpha^{p^n} = -\alpha,
$$

which means $$-\alpha\in S$$. ◼

### Remark

綜合以上兩 theorem，對於任意 prime power $$p^n$$，存在**唯一**的 finite field，其包含 $$p^n$$ 個 $$\overline{\Bbb Z}_p$$ 中的元素，稱為 the **Galois field**，以 $$\Bbb{F}_{p^n}$$ 或 $$GF(p^n)$$ 表示。

### Theorem (Galois fields)
> Let $$F$$ be a field of $$p^n$$ elements. then $$F \cong \Bbb{F}_{p^n}$$.