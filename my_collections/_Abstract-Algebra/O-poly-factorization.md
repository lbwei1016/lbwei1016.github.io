---
layout: page
title: Polynomial Factorization
usemathjax: true
tag: Abstract Algebra, Polynomial, Field
time: 2022/11/24
---

**Table of Content**
- [Gauss's Lemma](#gausss-lemma)
  - [Definition (content)](#definition-content)
    - [Theorem (product of primitive)](#theorem-product-of-primitive)
  - [Theorem (Gauss's Lemma)](#theorem-gausss-lemma)
  - [Corollary (irreducible)](#corollary-irreducible)
  - [Corollary (zero format)](#corollary-zero-format)
- [Factorization Modulo a Prime](#factorization-modulo-a-prime)
  - [Lemma (reduction modulo a number)](#lemma-reduction-modulo-a-number)
  - [Theorem (irreducible or not)](#theorem-irreducible-or-not)
  - [Theorem (Eisenstein criterion)](#theorem-eisenstein-criterion)

---

## Gauss's Lemma

### Definition (content)
> For an **integer** polynomial $$f(x) = a_nx^n+\cdots+a_0$$, we define the content of $$f(x)$$ to be $$\gcd(a_0,\cdots,a_n)$$, denoted by $$\text{Con}(f)$$.

> When $$\text{Con}(f) = 1$$, $$f(x)$$ is called **primitive**.

#### Theorem (product of primitive)
> If $$f(x)$$ and $$g(x)$$ are primitive, so is $$f(x)g(x)$$.

**Proof**

Suppose not, let $$p$$ be a prime factor of $$\text{Con}(fg)$$. Then every coefficient of $$f(x)g(x)$$  must be congruent to zero modulo $$p$$. In other words, $$\bar{f}(x)\bar{g}(x)$$ is equal to zero in $$\mathbb{Z}_p[x]$$. 

On the other hand, since $$\text{Con}(f) = \text{Con}(g) = 1$$, there are some coefficients of $$f(x)$$ and $$g(x)$$ not divided by $$p$$. In other words, $$\bar{f}(x)$$ and $$\bar{g}(x)$$ are both not equal to zero in $$\mathbb{Z}_p[x]$$. Therefore, $$\bar{f}(x)$$ and $$\bar{g}(x)$$ are zero divisors of $$\mathbb{Z}_p[x]$$, which is a contradiction, since the polynomial ring over an integral domain is still an integral domain. ◼

### Theorem (Gauss's Lemma)
> Let $$f(x)$$ be a nonzero **primitive** integer polynomial. If $$f(x) = g(x)h(x) $$ for some $$g(x)$$ and $$h(x)$$ in $$\mathbb{Q}[x]$$, then there exist some $$a\in \mathbb{Q}^\times$$ such that $$\tilde{g}(x)=ag(x) $$ and $$\tilde{h}(x) = a^{-1}h(x) $$ are integer polynomials. Especially, $$f(x)$$ can be **factorized over $$\mathbb{Z}[x]$$** as a product of $$\tilde{f}(x)$$ and $$\tilde{g}(x)$$.

> 只要把 $$f(x)$$ 的係數的公因數提出來，$$f(x)$$ 就變成 primitive 了。

**Proof**

Suppose $$f(x)=g(x)h(x)$$. Let $$a$$ and $$b$$ be the rational numbers such that $$\tilde{g}(x)=ag(x)$$ and $$\tilde{h}(x)=bh(x)$$ are primitive integer polynomials. It remains to show that $$ab=1$$. Write $$ab=r/s$$, where $$r$$ and $$s$$ are coprime integers. Then

$$
f(x) = {1\over a}\tilde{g}(x)\cdot {1\over b}\tilde{h}(x) = {s\over r}\tilde{g}(x)\tilde{h}(x).
$$

Since $$\tilde{g}(x)$$ and $$\tilde{h}(x)$$ are primitive, $$\tilde{g}(x)\tilde{h}(x)$$ is also primitive. Therefore, 

$$
r = \text{Con}(rf(x)) = \text{Con}(s\tilde{g}(x)\tilde{h}(x)) = s,
$$

which means $$ab=1$$. ◼

### Corollary (irreducible)
> A primitive integer polynomial is irreducible over $$\mathbb{Q}[x]$$ iff it is irreducible over $$\mathbb{Z}[x]$$.

> 從有理數縮減至整數！

### Corollary (zero format)
> For $$f(x) = a_nx^n+\cdots+a_0 \in \mathbb{Z}[x]$$, the zeros of $$f(x)$$ are of the form $$b/c$$ with $$b\vert a_0$$ and $$c\vert a_n$$.

--- 

## Factorization Modulo a Prime
### Lemma (reduction modulo a number)
> Let $$m>1$$ be a positive integer. Define $$\phi_m: \mathbb{Z}[x]\to \mathbb{Z}_m[x]$$ by 
>
> $$
> \phi_m(a_nx^n + \cdots + a_0) = \bar{a_n}x^n+\cdots+\bar{a_0}.
> $$
>
> Then $$\phi_m$$ is a ring homomorphism, called **reduction modulo $$m$$**.

### Theorem (irreducible or not)
> If $$\bar{f}(x)$$ is irreducible over $$\mathbb{Z}_p$$, then $$f(x)$$ is irreducible over $$\mathbb{Q}$$. However, even if $$\bar{f}(x)$$ is reducible over $$\mathbb{Z}_p$$, $$f(x)$$ may still be **irreducible** over $$\mathbb{Q}$$.

### Theorem (Eisenstein criterion)
> For a polynomial $$f(x) = a_nx^n+\cdots+a_0\in \mathbb{Z}[x]$$. Suppoe there exists a prime $$p$$ such that
>
> - $$a_n \not \equiv 0 \text{ mod } p$$;
> 