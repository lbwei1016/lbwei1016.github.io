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
- [Frobenius Automorphisms](#frobenius-automorphisms)
  - [Theorem (Frobenius generates)](#theorem-frobenius-generates)
    - [Lemma (divides)](#lemma-divides)
  - [Theorem (transitive action on roots)](#theorem-transitive-action-on-roots)
  - [**Frobenius Automorphism On Subextensions**](#frobenius-automorphism-on-subextensions)
    - [Theorem (one root for all)](#theorem-one-root-for-all)
    - [Remark](#remark-1)
  - [**Subgroups and Intermediate Fields**](#subgroups-and-intermediate-fields)
- [**Theorem (the Galois theory of finite fields)**](#theorem-the-galois-theory-of-finite-fields)

---

> Check [here](../more-on-normal-subgroups/#interlude-automorphism) for some basic information.

## Automorphism Groups
### Definition (automorphism groups)
> Let $$E$$ be a field extension over a field $$F$$. The **group of automorphisms** on $$E/F$$ is defined as
>
> $$\begin{align*}
  \text{Aut}(E/F) &= \{\rho: E\to E\mid \rho \text{ is a field isomorphism and } \rho(x)=x \text{, for all } x\in F \} \\
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
> In particular, $$\vert \text{Aut}(E/F)\vert$$ is the number of **distinct** zeros of $$\text{Irr}(\alpha, F)$$ in $$E$$.

---

## Frobenius Automorphisms

> 注意！以下討論的 $$F$$ 都是 finite field！

> Check out [Finite Field](../finite-field/) and [Characteristic](../integral-domain/#characteristic).

Let $$F=\Bbb F_q$$ and $$E = \Bbb F_{q^n}$$. Consider the map $$\sigma:E\to E$$ given by $$\sigma(x)=x^q$$. We can show that $$\sigma$$ is an element of $$\operatorname{Aut}(E/F)$$ by showing 

1. $$\sigma$$ is an additive homomorphism (use $$\text{char}E$$).
2. $$\sigma$$ is a multiplicative homomorphism.
3. $$\sigma$$ is a bijection (show kernel is trivial; injective iff surjective for finite mapping).
4. For all $$x\in F$$, we have $$\sigma(x)=x$$.

In fact, $$\sigma$$ is called the **Frobenius automorphism**, also denoted by $$\text{Frob}_{E/F}$$.

### Theorem (Frobenius generates)
> For a finite extension $$E$$ over a **finite field** $$F$$, the Frobenius automorphism **$$\text{Frob}_{E/F}$$** **generates** the automorphism group $$\text{Aut}(E/F)$$, i.e., **$$\text{Aut}(E/F) = \langle \text{Frob}_{E/F}\rangle$$**, which is of order $$[E:F]$$. 
>
> In particular, if $$[E:F]=n$$, then 
> 
> $$\text{Aut}(E/F) = \langle \text{Frob}_{E/F}\rangle \cong \Bbb Z_n.$$

> Finite field extension 的 automorphism group 才會被 $$\text{Frob}_{E/F}$$ 生成！

**Proof**

Suppose the order of $$\sigma = \text{Frob}_{E/F}$$ is $$m$$. Recall from [this theorem](#theorem-group-size-upper-bound), the size of $$\text{Aut}(E/F)$$ is bounded by $$n$$, which means that $$m\le n$$. 

Let $$\alpha$$ be a [generator of $$E^\times$$](../zeros-of-polynomials/#corollary-the-multiplicative-group-of-a-field) of order $$q^n - 1$$. Then 

$$
\begin{align*}
\alpha = \sigma^m(\alpha) = \alpha^{q^m} &\implies a^{q^m-1}=1 \\
&\implies (q^n-1)\vert (q^m-1) \\
&\implies m\ge n.
\end{align*}
$$

Hence, we conclude that $$m = n$$. 

Since $$n = m = \vert\langle \text{Frob}_{E/F}\rangle\vert \le \vert\text{Aut}(E/F)\vert\le n$$, we have $$\langle \text{Frob}_{E/F}\rangle = \text{Aut}(E/F)$$. ◼

#### Lemma (divides)
> Let $$d$$ be a positive integer. We have $$q^d-1\vert q^n-1$$ **iff** $$d\vert n$$.

**Proof Hint**

Since $$q$$ can be *anything*, we can even use it for polynomials: $$x^d-1\vert x^n-1$$ iff $$d\vert n$$. Use long division on polynomials!

### Theorem (transitive action on roots)
> Suppose $$E=F(\alpha)$$. Then the automorphisms in $$\text{Aut}(E/F)$$ act **transitively** on the roots of $$\text{Irr}(\alpha, F)(x)$$.

**Proof**

Since each automorphism in $$\text{Aut}(E/F)$$ is [uniquely determined](#uniqueness-of-automorphisms) by its action on $$\alpha$$, $$\sigma^i(\alpha)$$ are distinct roots of $$\text{Irr}(\alpha, F)(x)$$, for all $$0\le i\le n-1$$. Hence, we have

$$
\text{Irr}(\alpha, F)(x) = \prod_{i=0}^{n-1}\big(x - \sigma^i(\alpha) \big). \tag*{$\blacksquare$}
$$

> 記得 $$\langle \sigma \rangle = \langle \text{Frob}_{E/F}\rangle = \text{Aut}(E/F)$$！

### **Frobenius Automorphism On Subextensions**

From the definition of Frobenius automorphism ($$\sigma(x) = x^q$$), we can see that it is determined by the **underlying field $$F$$**, with size $$q$$. Thus, for an intermediate field $$K$$ between $$E$$ and $$F$$, we have

$$
\text{Frob}_{K/F}(x) = x^q = \text{Frob}_{E/F}(x)
$$

for all $$x\in K$$. Thus $$\text{Frob}_{E/F}\Big\vert_K 
= \text{Frob}_{K/F}$$.

Suppose $$K=F(\beta)$$ for some $$\beta\in E$$ and $$[K:F] = m$$. Then, all the roots of $$\text{Irr}(\beta, F)(x)$$ are $$\beta, \beta^q, \cdots, \beta^{q^{(m-1)}}$$ (by this [theorem](#theorem-transitive-action-on-roots)), and we have $$\beta^{q^m} = \beta$$. Therefore,

$$
\prod_{i=0}^{n-1}\Big(x-\text{Frob}^i_{E/F}(\beta)\Big) = \prod\Big(x-\beta^{q^i}\Big) = \Big[\text{Irr}(\beta, F)(x)\Big]^{n/m},
$$

where each root occurs $$n/m$$ times.

Here comes a theorem:

#### Theorem (one root for all)
> Let $$E$$ be a *finite* extension of a **finite field** $$F$$, and let $$f(x)$$ be an **irreducible** polynomial in $$F[x]$$ with a root in $$E$$. Then, **all the roots of $$f(x)$$ in $$\bar F$$ lie in $$E$$**, and $$\text{Aut}(E/F)$$ acts transitively on these roots. 

> 一個在 $$E$$，全都在 $$E$$。

> 因為乘法有封閉性！$$(\sigma(x) = x^q)$$

#### Remark

設 $$F=\Bbb Z_2$$、$$E = F(\alpha)$$，且 $$[E:F]=4$$。對於所有 $$\gamma \in E$$，在什麼情況底下等式會成立？

$$\text{Irr}(\gamma, F)(x) \stackrel{?}{=} \prod_{\sigma\in\text{Aut}(E/F)}\big(x - \sigma(\gamma) \big)$$

從上述說明可以得知，$$\gamma$$ 加入 $$F$$ 後必須促成四次擴張；而因為 $$\vert E\vert = 2^4$$，所以 $$E$$ 和 $$F$$ 之間的 intermediate field 只有 $$\Bbb F_{2^2} = \Bbb F_4$$。

> 因為只有 $$2\vert 4$$！（除了 $$1$$、$$4$$）

也就是說，所有 $$\gamma \in E\backslash\Bbb F_4$$ 都可以使該等式成立！

另外，令 $$\sigma = \text{Frob}_{E/F}$$。計算其實很方便：

$$
\sigma(\alpha + 1) = (\alpha + 1)^4 = \alpha^4 + 1^4
$$

> 因為是 automorphism，直接把次方分配進去！

### **Subgroups and Intermediate Fields**

Let $$K = F(\alpha)$$ for some $$\alpha \in E$$, and $$[K:F] = m$$. Let $$H$$ be a subgroup of $$G =\text{Aut}(E/F)$$. Then, $$H = \langle\sigma^m\rangle$$ for a *unique* integer $$m\vert n$$, where $$\sigma = \text{Frob}_{E/F}$$. Observe that 

$$
\sigma^m(x) = x^{q^m} = \text{Frob}_{E/K}(x),
$$

and thus

$$
H = \text{Aut}(E/K).
$$

Now consider the subset $$E^H$$ of $$E$$ **fixed** by $$H$$:

$$
E^H := \{a\in E\mid h(a) = a, \forall h\in H \},
$$

and note that 

$$ 
\begin{align*}
  E^H &= \{a\in E\mid \sigma^{m}(a) = a \} \\
  &= \{a\in E\mid a^{q^m}=a \} = \Bbb F_{q^m} = K.
\end{align*}
$$

> 怪怪的？！$$E^H$$ 的定義和最後那段不太一樣？

Let $$K$$ be an intermediate field between $$E$$ and $$F$$, so $$K = \Bbb F_{q^m}$$ for some $$m\vert n$$. Consider the subgroup of $$G$$ fixing $$K$$:

$$
G_K = \{g\in G\mid g(x) = x\forall x\in K\} = \langle \sigma^{m'}\rangle
$$

for some unique $$m'\vert n$$. We now show that $$m = m'$$, which implies that 

$$
G_k = \text{Aut}(E/K).
$$

Sine $$\sigma^m$$ fixes $$K$$, $$\sigma^m\in G_K$$ and $$m' \le m$$. Let $$\alpha$$ be a generator of $$K^\times$$ of order $$q^m-1$$. Then we have

$$
\alpha = \sigma^{m'(\alpha)} = \alpha^{q^{m'}} \implies \alpha^{q^{d'}-1} = 1,
$$

which implies that $$d \le d'$$. Therefore $$d=d'$$.

With the above arguments, we now come to the following theorem.

## **Theorem (the Galois theory of finite fields)**

> For a *finite* extension $$E$$ over a **finite field** $$F$$, let $$G = \text{Aut}(E/F)$$ and $$\sigma = \text{Frob}_{E/F}$$. Then, there is a **bijection between intermediate fields $$K$$**, between $$F$$ and $$E$$, **and subgroups $$H$$ of $$G$$**, which is given by:
>
> $$
> \begin{align*}
  K = \Bbb F_{q^d} &\xrightarrow[]{\rho} G_K = \langle\sigma^d\rangle \\
  E^H = \Bbb F_{q^d} &\xleftarrow[]{\tau} H = \langle \sigma^d \rangle.
\end{align*}
> $$
>
> Moreover, $$\rho\circ \tau$$ and $$\tau \circ\rho$$ are both the identity maps.
