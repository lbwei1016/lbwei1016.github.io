---
layout: page
title: Sylow Theorem
usemathjax: true
tag: Abstract Algebra, Sylow Theorem
time: 2023/03/02
---

**Table of Content**
- [**Theorem (Sylow theorems)**](#theorem-sylow-theorems)
  - [Corollary (contain; normal)](#corollary-contain-normal)
- [The first Sylow theorem](#the-first-sylow-theorem)

---

Sylow theorems can be used to find normal subgroups, and in turn [determine group structures](../NH/#theorem-determine-structure-of-g)!

## **Theorem (Sylow theorems)**
> Suppose $$\vert G\vert=p^nm$$ where $$p$$ is a prime with $$p\not \mid m$$.
>
> 1. There exists a subgroup of order $$p^i$$ for $$1<i\leq n$$. Moreover, **every subgroup of order $$p^i$$ is normal in some subgroup of order $$p^{i+1}$$** when $$i<n$$.
> 2. Any two **Sylow $$p$$-subgroups** are **conjugated**.
> 3. Let **$$n_p$$** be the number of **Sylow p-subgroups**. Then $$n_p$$ satisfies the following **two conditions**:
>
> $$
> \begin{align*}
> &n_p \equiv 1 \pmod p, \tag{1}  \\
> &n_p \mid m. \tag{2}
> \end{align*}
> $$

> The subgroup $$H$$ of order $$p^n$$ is called a **Sylow $$p$$-subgroup**, which is exactly a maximal $$p$$-subgroup.

### Corollary (contain; normal)
> 1. Every $$p$$-subgroup is contained in a Sylow $$p$$-subgroup.
> 2. **A Sylow $$p$$-subgroup is normal iff $$n_p = 1$$.**

---

> 把上面擠在一起的 sylow 搬下來 (未完工)

Let $$G$$ be a group of order $$p^nm$$, where $$p$$ does not divide $$m$$.

## The first Sylow theorem
> There exists a subgroup of order $$p^i$$ for $$1<i\leq n$$. Moreover, **every subgroup of order $$p^i$$ is normal in some subgroup of order $$p^{i+1}$$** when $$i<n$$.

**Proof**

To prove this, we construct a series of $$p$$-subgroups $$H_1 < H_2 < \cdots < H_n$$, with $$\vert H_i\vert = p^i$$ and $$H_i \trianglelefteq H_{i+1}$$ for $$i<n$$, by induction.

By Cauchy's theorem, $$G$$ has a subgroup $$H_1$$ of order $$p$$. Suppose that for some $$i<n$$, $$H_i$$ has been constructed. We then wish to construct $$H_{i+1}$$. 

Since $$i<n$$, we have $$p\mid [G:H_i]$$. By [this lemma](../normalizer/#lemma-index-congruent):

$$
[N_G(H_i):H_i ] \equiv [G:H_i] \equiv 0\pmod p,
$$

which means that $$p$$ divides the order of $$N_G(H_i)/H_i$$. By Cauchy's theorem, there is a subgroup $$K$$ of $$N_G(H_i)/H_i$$ of order $$p$$.

Now consider the canonical homomorphism $$\phi: N_G(H_i)\to N_G(H_i)/H_i$$ defined by $$\phi(g) = gH_i$$. Let $$R=\phi^{-1}(K)$$ and [thus](../homomorphism-and-normal-groups/#properties) $$R < N_G(H_i)$$. We can verify that $$\text{ker}(\phi) = H_i$$. Also, $$H_i < R$$, since $$\{e\} \subset K$$ and $$R = \phi^{-1}(K)$$. Thus, $$R/\text{ker}(\phi) \cong \phi(R) = K$$ by [the first isomorphism theorem](../3-isomorphism/#the-first-isomorphism-theorem) . In other words, 

$$
[R:H_i] = \vert K\vert = p \implies \vert R\vert = p^{i+1}.
$$

Moreover, $$H_i$$ is normal in $$N_G(H_i)$$ by [definition](../normalizer/#definition-normalizer), and thus $$H_i$$ is also normal in $$R$$. The desired $$H_{i+1}$$ is exactly $$R$$. ◼

> $$H_i < R$$, since $$\{e\} \subset K$$ and $$R = \phi^{-1}(K)$$. 怪怪的？

---