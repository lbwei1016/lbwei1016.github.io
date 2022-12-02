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
    - [Exercise](#exercise)
    - [Theorem (transcendental and homomorphism)](#theorem-transcendental-and-homomorphism)
  - [Definition (minimal degree polynomial)](#definition-minimal-degree-polynomial)
    - [Lemma (irreducible)](#lemma-irreducible)
    - [Proposition (uniqueness)](#proposition-uniqueness)
    - [Proposition (factor)](#proposition-factor)
  - [Definition (monic irreducible)](#definition-monic-irreducible)
    - [Remark](#remark-1)
- [Theorem (algebraic extension)](#theorem-algebraic-extension)
  - [Theorem (unique expression)](#theorem-unique-expression)
    - [Proof](#proof)
    - [Exercises](#exercises)
  - [Remark](#remark-2)
- [Extension Fields and Residue Classes](#extension-fields-and-residue-classes)

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

#### Exercise
> Show that $$x^2-\pi$$ is irreducible over $$\mathbb{Q}(\pi)$$.

**Solution**

Suppose $$f(\pi)/g(\pi)$$ is a zero of $$x^2-\pi$$ where $$g(\pi)\not = 0$$. Then 

$$
\Big({f(\pi)\over g(\pi)}\Big)^2 - \pi = 0, \\
f(\pi)^2 - \pi g(\pi)^2 = 0,
$$

which means that $$\pi$$ is a zero of $$f(x)^2 - xg(x)^2 \in \mathbb{Q}[x]$$. This is a contradiction. Therefore, $$\pi$$ is irreducible over $$\mathbb{Q}(\pi)$$. ◼

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

$$\text{Irr}(\alpha, F) = \text{Irr}(\alpha, F)(x) $$, and that $$\text{Irr}(\alpha, F)(\alpha) = 0 $$.

#### Remark

如何找出 $$\text{Irr}(\alpha, F)$$？先找到 $$f(x)$$ 使得 $$f(\alpha)=0$$，再驗證 $$f(x)$$ is irreducible！ 

如果 $$\deg{(\alpha, F)} = n$$ 而且 $$\vert F\vert = m$$，則 $$\vert F(\alpha)\vert = n^m$$. 

---

## Theorem (algebraic extension)
> Let $$F(\alpha)$$ be an **algebraic** extension field of $$F$$. Then **$$F(\alpha) = F[\alpha]$$**.

> **algebraic** extension: $$\exists f(x)\in F[x]$$ such that $$f(\alpha)=0$$.

**Proof**

It is clear that $$F[\alpha] \subset F(\alpha)$$. It remains to show that every $$f(\alpha)/g(\alpha)\in F(\alpha)$$ is also in $$F[\alpha]$$.

Since $$g(\alpha)\not = 0$$, $$g(x)$$ is not divisible by $$\text{Irr}(\alpha, F)$$. Moreover, $$\text{Irr}(\alpha, F)$$ is irreducible, so $$1$$ is a [GCD](../O-poly-factorization/#definition-gcd) of $$g(x)$$ and $$\text{Irr}(\alpha, F)$$. Thus, we can find $$p(x)$$ and $$q(x)$$ such that 

$$
p(x)g(x) + q(x)\text{Irr}(\alpha, F) = 1
$$

Then we have $$p(\alpha)q(\alpha) = 1$$, which implies that 

$$
{f(\alpha)\over g(\alpha)} = {f(\alpha)p(\alpha)\over g(\alpha)p(\alpha)} = f(\alpha)p(\alpha) \in F[\alpha]. \tag*{$\blacksquare$}
$$

### Theorem (unique expression)
> Let $$F(\alpha)$$ be an **algebraic** extension field of $$F$$. Then any $$\beta\in F(\alpha)$$ can be **uniquely** expressed in the form **$$\beta=b_0+b_1\alpha+\cdots+b_{n-1}\alpha^{n-1}$$**, where $$n=\deg(\text{Irr}(\alpha, F))$$.

#### Proof

By [this theorem](#theorem-algebraic-extension), we have $$F(\alpha)=F[\alpha]$$ since $$\alpha$$ is algebraic over $$F$$. Thus $$\beta=f(\alpha)$$ for some $$f(x)\in F[x]$$.

**existence**

By the division algorithm, there exists $$q(x)$$ and $$r(x)$$ such that $$f(x) = q(x)\text{Irr}(\alpha, F) + r(x)$$ with $$r(x) = 0$$ or $$\deg{r(x)} < n$$. Then $$r(\alpha)=f(\alpha) = \beta$$. 

**uniqueness**

Now suppose $$\beta=f(\alpha)=g(\alpha)$$ where $$f(x)$$ and $$g(x)$$ are two distinct polynomials of degree less than $$n$$. However, $$f(x)-g(x)$$ then become a non-zero polynomial with the zero $$\alpha$$ and of degree *less* than $$n$$, which is a contradiction. ◼

#### Exercises

> Let $$\beta = 1/(\sqrt[3]{4} - 2\sqrt[3]{2} + 2) \in \mathbb{Q}(\sqrt[3]{2}) $$. Write $$\beta$$ into the form $$a_0 + a_1\sqrt[3]{2} + a_2\sqrt[3]{4}$$ where $$a_i\in \mathbb{Q} $$.

**Solution**

Let $$f(x)=\text{Irr}(\sqrt[3]{2}, \mathbb{Q}) = x^3-2$$. Let $$g(x) = x^2-2x+2$$, and then $$\beta=g^{-1}(\sqrt[3]{2})$$. 

Now our goal is to find the **inverse** of $$g(x)$$ in $$\mathbb{Q}(\sqrt[3]{2})\Big/f(x)\mathbb{Q}(\sqrt[3]{2}) $$. This can be achieved by applying the [Euclidean Algorithm](../../Concrete-Math/extgcd.md). After some calculation, we have

$$
{1\over 10 }\cdot g(x)(x^2+3x+4) - {1\over 10} \cdot f(x)(x+1) = 1.
$$

Thus, $$g^{-1}(x) = (x^2+3x+4) / 10$$, and $$\beta = (\sqrt[3]{4}^2+3\sqrt[3]{2}+4)/10$$. ◼

> $$\sqrt[3]{2}$$ is **algebraic** over $$\mathbb{Q}$$.

### Remark

Let $$f(x) = x^2+1 \in \mathbb{Z}_3[x]$$. Since $$f(0)=1$$ and $$f(1)=f(2)=2$$, $$f(x)$$ is irreducible over $$\mathbb{Z}_3[x]$$. Let $$\alpha$$ be a zero of $$f(x)$$ in some extension of $$\mathbb{Z}_3$$. Then

$$
\mathbb{Z}_3(\alpha) = \{a_0+a_1\alpha\mid a_i \in \mathbb{Z}_3\},
$$

which is a field of $$9$$ elements.

Since [the multiplicative group of every finite field is cyclic](../N-zeros-of-polynomials/#corollary-the-multiplicative-group-of-a-field), we can find a generator of $$\mathbb{Z}_3^\times(\alpha)$$; let's first check whether $$\alpha$$ is a generator:

$$
\alpha^2 = -1 \Rightarrow \alpha \text{ is not a generator.}
$$

Now let $$\beta=\alpha+1$$, and then

$$
\beta^2 = (\alpha+1)^2 = 2\alpha, \\
\beta^4 = 4\alpha^2 = -4 = -1 \Rightarrow \beta \text{ is a generotor}.
$$

Thus, $$\mathbb{Z}_3^\times(\alpha) = \langle \beta\rangle$$.

Since $$\mathbb{Z}_3(\alpha) = \mathbb{Z}_3(\alpha+1) = \mathbb{Z}_3(\beta)$$ and $$\beta$$ is a generator, it is preferred to add $$\beta$$ to $$\mathbb{Z}_3$$ than $$\alpha$$. 

> $$\beta$$ is a zero of $$g(x) = (x-1)^2+1 = x^2-2x+2 = x^2+x+2 = \text{Irr}(\beta, F)$$.

If our field extension is $$\mathbb{Z}_3(\beta)$$, we have

$$
\beta^2 = 2\beta + 1, \\
\beta^3 = 2\beta+2, \\
\cdots \\
\beta^7 = \beta+1, \\
\beta^8 = 1,
$$

which means that we can express **all** non-zero elements in $$\mathbb{Z}_3(\beta)$$ as some power of $$\beta$$!

> 用 power 表示，算 **inverse** 很方便。

---

## Extension Fields and Residue Classes

Recall the [evaluation homomorphism](../M-rings-of-polynomials/#evaluation-homomorphism); here we define it as

$$
e_\alpha: F[x] \to E,
$$

such that $$f(x) \mapsto f(\alpha)$$. Then

$$
\text{ker}(e_\alpha) = \{f(x)\in F[x]\mid f(\alpha)=0 \} = \text{Irr}(\alpha, F)F[x].
$$

By [the first ring isomorphism theorem](../M-rings-of-polynomials/#theorem-first-ring-isomorphism-theorem), we have

$$
F[x]\big/\text{Irr}(\alpha, F)F[x] \cong F[\alpha]=F(\alpha).
$$

Therefore, there are two equivalent ways to construct a **simple algebraic field extension** of $$F$$:

- **add some element** from a larger field containing $$F$$
- consider the **residue classes** of $$F[x]$$ modulo some irreducible polynomials.