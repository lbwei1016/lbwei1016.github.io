---
layout: page
title: More on Automorphisms
usemathjax: true
tag: Abstract Algebra, Automorphism
time: 2023/04/17
---

**Table of Content**
- [Automorphism Groups](#automorphism-groups)
  - [Definition (automorphism groups)](#definition-automorphism-groups)
  - [Remark](#remark)
  - [Acting on the set of roots](#acting-on-the-set-of-roots)
  - [Uniqueness of automorphisms](#uniqueness-of-automorphisms)
  - [Theorem (group size upper bound)](#theorem-group-size-upper-bound)

---

> Check [here](../more-on-normal-subgroups/#interlude-automorphism) for some basic information.

## Automorphism Groups
### Definition (automorphism groups)
> Let $$E$$ be a field extension over a field $$F$$. The **group of automorphisms** on $$E/F$$ is defined as
>
> $$\begin{align*}
  \text{Aut}(E/F) &= \{\rho: E\to F\mid \rho \text{ is a field isomorphism and } \rho(x)=x \text{, for all } x\in F \} \\
  &= \{\rho: E\to E\mid \rho \text{ is a } F \text{-linear field isomorphism}\}. 
\end{align*}
> $$

### Remark

How to see that the above two definitions are equivalent? Suppose $$\rho$$ is a field ispmorphism and $$\rho(x)=x$$, for all $$x\in F$$. Then for any $$k\in F$$ and $$x, y\in E$$, we have

$$
\rho(kx+y) = \rho(k)\rho(x)+\rho(y) = k\rho(x)+\rho(y),
$$

which indeed shows that $$\rho$$ is $$F$$-linear.

> $$\rho(z)=\bar z$$ is an element if $$\text{Aut}(\Bbb C/\Bbb R)$$.

### Acting on the set of roots

Let $$f(x)\in F[x]$$, and let $$\alpha$$ be a root of $$f(x)$$ in $$E$$. Then $$f(\rho(\alpha)) = \rho(f(\alpha)) = \rho(0) = 0$$. (Why? Exapnd everything and use the **definition** of automorphism!). Therefore, **$$\rho(\alpha)$$ is also a root of $$f(x)$$**!. This means that $$\text{Aut}(E/F)$$ can [act](../group-action) on **the set of roots of $$f(x)$$ in $$E$$**.

### Uniqueness of automorphisms

Suppose $$E=F(\alpha)$$ and $$[E:F]=\alpha$$. From [here](./field-extension/#theorem-unique-expression), we know that every element in $$E$$ can be written as

$$
a_0+a_1\alpha+\cdots+a_{n-1}\alpha^{n-1}, a_i \in F.
$$

Then

$$
\rho(a_0+a_1\alpha+\cdots+a_{n-1}\alpha^{n-1}) = a_0+a_1\rho(\alpha)+\cdots+a_{n-1}\rho(\alpha)^{n-1},
$$

which means that **$$\rho$$ is uniquely determined by $$\rho(\alpha)$$**.

### Theorem (group size upper bound)
> Let $$E=F(\alpha)$$ be a simple algebraic field extension over $$F$$. Suppose $$\text{Irr}(\alpha, F)(x)$$ has $$m$$ *distinct* roots in $$E$$. Then
>
> $$
> \vert \text{Aut}(E/F)\vert=m\le[E:F].
> $$
>
> In particular, $$\vert \text{Aut}(E/F)\vert=[E:F]$$ if $$f(x)$$ **splits** over $$F$$ without repeated roots, i.e., 
>
> $$
> f(x) = (x-\alpha_1)(x-\alpha_2)\cdots(x-\alpha_m), \alpha_i \in E.
> $$