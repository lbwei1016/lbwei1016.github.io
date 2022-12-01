---
layout: page
title: Field Extension
usemathjax: true
tag: Abstract Algebra, Polynomial, Field
time: 2022/11/29
---

**Table of Content**
- [Definition (field extension)](#definition-field-extension)
  - [Definition (simple extension)](#definition-simple-extension)
    - [Remark](#remark)
  - [Definition (algebraic and transcendental)](#definition-algebraic-and-transcendental)
    - [Theorem (transcendental and homomorphism)](#theorem-transcendental-and-homomorphism)
  - [Definition (minimal degree polynomial)](#definition-minimal-degree-polynomial)
    - [Lemma (irreducible)](#lemma-irreducible)
    - [Proposition (uniqueness)](#proposition-uniqueness)
    - [Proposition (factor)](#proposition-factor)
  - [Definition (monic irreducible)](#definition-monic-irreducible)

---

## Definition (field extension)
> A field $$E$$ is an **extension field** of a field $$F$$ if $$F\le E$$.

### Definition (simple extension)
> Let $$F\le E$$. If there exists $$\alpha\in E$$ such that $$E=F(\alpha)$$, then $$E=F(\alpha)$$ is a **simple extension** of $$F$$.

#### Remark

Let $$E$$ be a field extension of $$F$$. For $$\alpha\in E$$, let 

$$
F[\alpha]:=\{f(\alpha): f(x)\in F[x]\},
$$

which is **the minimal subring** containing $$F$$ and $$\alpha$$; let 

$$
F(\alpha):=\{f(\alpha)/g(\alpha): f(x),g(x)\in F[x], g(\alpha) \not = 0 \},
$$

which is **the minimal subfield** containing $$F$$ and $$\alpha$$.

### Definition (algebraic and transcendental)
> An element $$\alpha$$ of an extension field $$E$$ of a field $$F$$ is **algebraic over $$F$$** if **$$f(\alpha) = 0$$** for some nonzero polynomial $$f(x)\in F[x]$$. If such a polynomial does not exist, then $$\alpha$$ is **transcendental over $$F$$**.

**Example**

- $$\sqrt{1+\sqrt{2}}$$ is algebraic over $$\mathbb{Q}$$ 
- $$\pi$$ and $$e$$ are transcendental over $$\mathbb{Q}$$, but are *algebraic over* $$\mathbb{R}$$.

> 就看 over 哪個 field！

#### Theorem (transcendental and homomorphism)
> Let $$E$$ be an extension field of a field $$F$$, and let $$\alpha\in E$$. Then $$\alpha$$ is *transcendental over* $$F$$ iff the **evaluation homomorphism** $$\phi_\alpha: F[x]\to E$$ is an **isomorphism** of $$F[x]$$ with a *subdoamin* of $$E$$.

**Proof**

It suffice to show that $$\alpha \in E$$ is transcendental over $$F$$ iff $$\phi_\alpha$$ is **one-to-one**.

> 因為只要 isomorphic to a *subdomain*！

> 可用 $$\text{ker}(\phi_\alpha) = \{0\}$$。

**Remark**

這個定理說明了，如果 $$\alpha$$ is transcendental over $$F$$，則 $$F[\alpha]$$ 和 $$F[x]$$ 看起來沒兩樣。

### Definition (minimal degree polynomial)
> Assume that $$F\le E$$ and $$\alpha \in E$$ is algebraic over $$F$$. Let $$I_\alpha = \{f(x)\in F[x]: f(\alpha)=0 \}$$ be a subset of $$F[x]$$ and let $$p_\alpha(x)$$ be a nonzero polynomial in $$I_\alpha$$ of **minimal degree**.

> 很像 kernel！

#### Lemma (irreducible)
> $$p_\alpha(x)$$ is irreducible.

**Proof**

Suppose $$p_\alpha(x) = r(x)s(x)$$. Then we have $$r(\alpha)s(\alpha) = 0$$. ...

#### Proposition (uniqueness)
> If $$p_\alpha(x)$$ and $$p_{\alpha}'(x)$$ are both nonzero monic polynomials in $$I_\alpha$$ of **minimal degree**, then $$p_\alpha(x) = p_{\alpha}'(x) $$.

**Proof**

$$
\deg{(p_\alpha(x) - p_{\alpha}'(x))} < \deg{p_\alpha(x)}...
$$

#### Proposition (factor)
> For all $$f(x)\in I_\alpha$$, $$p_\alpha(x)\mid f(x)$$. In other words, $$I_\alpha = p_\alpha(x)F[x]$$.

**Proof**

By the division algorithm, we have

$$
f(x) = p_\alpha(x)q(x) + r(x).
$$

Since $$f(\alpha) = 0$$, $$r(\alpha) = 0$$, which means that $$p_\alpha(x) \mid f(x)$$. ◼

> This proposition implies that $$p_\alpha(x)$$ is **the only monic irreducible** polynomial in $$I_\alpha$$.

### Definition (monic irreducible)
> The unique **monic irreducible** polynomial $$p(x)$$ in $$I_\alpha$$ is called the **irreducible polynomial for $$\alpha$$ over $$F$$**, and is denoted by **$$\text{Irr}(\alpha, F)$$**. The degree of $$\text{Irr}(\alpha, F)$$ is the **degree of $$\alpha$$ over $$F$$**, and is denoted by $$\deg{(\alpha, F)}$$.