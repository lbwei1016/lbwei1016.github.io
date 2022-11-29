---
layout: page
title: Field Extension
usemathjax: true
tag: Abstract Algebra, Polynomial, Field
time: 2022/11/29
---

**Table of Content**


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

### Definition (algebraic & transcendental)
> An element $$\alpha$$ of an extension field $$E$$ of a field $$F$$ is **algebraic over $$F$$** if **$$f(\alpha) = 0$$** for some nonzero polynomial $$f(x)\in F[x]$$. If such a polynomial does not exist, then $$\alpha$$ is **transcendental over $$F$$**.

**Example**

- $$\sqrt{1+\sqrt{2}}$$ is algebraic over $$\mathbb{Q}$$ 
- $$\pi$$ and $$e$$ are transcendental over $$\mathbb{Q}$$, but are *algebraic over* $$\mathbb{R}$$.

> 就看 over 哪個 field！

#### Theorem (transcendental & homomorphism)
> Let $$E$$ be an extension field of a field $$F$$, and let $$\alpha\in E$$. Then $$\alpha$$ is *transcendental over* $$F$$ iff the **evaluation homomorphism** $$\phi_\alpha: F[x]\to E$$ is an **isomorphism** of $$F[x]$$ with a *subdoamin* of $$E$$.

**Proof**

It suffice to show that $$\alpha \in E$$ is transcendental over $$F$$ iff $$\phi_\alpha$$ is **one-to-one**.

> 因為只要 isomorphic to a *subdomain*！

> 可用 $$\text{ker}(\phi_\alpha) = \{0\}$$。

**Remark**

這個定理說明了，如果 $$\alpha$$ is transcendental over $$F$$，則 $$F[\alpha]$$ 和 $$F[x]$$ 看起來沒兩樣。