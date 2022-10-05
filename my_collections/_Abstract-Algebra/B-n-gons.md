---
layout: page
title: Symmetry Groups on N-gons
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/10/04
---

**Table of Content**
- [The Order of the Symmetry Group](#the-order-of-the-symmetry-group)
  - [Lemma (stabilizer)](#lemma-stabilizer)
  - [Theorem (stabilizer / ordit)](#theorem-stabilizer--ordit)
- [The Group of Symmetries of a Regular $$N$$-gon](#the-group-of-symmetries-of-a-regular-n-gon)

---

## The Order of the Symmetry Group
Let $$G$$ be the group of symmetries of some object $$X$$. Fix a point $$x$$ in $$X$$, let 

$$G_x = \{gx|g \in G\},$$

called the **$$G$$-orbit** of $$x$$. Suppose $$G_x$$ is finite and write

$$G_x = \{x_1=x, x2,\cdots,x_n\} = \{g_1x,g_2x,\cdots,g_nx\}$$

for some $$g_i \in G$$. Set 

$$G_i = \{g \in G | gx=x_i\}.$$

It is clear that $$G$$ is the *disjoint union* of all $$G_i$$. Moreover,

$$G_1 = \{g \in G | gx=x\}$$

is also called the **stabilizer** of $$x$$ in $$G$$, denoted by $$\text{Stab}_G(x)$$, which is a subgroup of $$G$$.

> $$G$$-orbit of $$x$$: 將 $$G$$ 內的所有變換加諸於 $$x$$ 身上，所形成的集合；$$G_i$$ 只取可使 $$x$$ 變換成 $$x_i$$ 的部分。

> **stabilizer** 使 $$x$$ 保持不變，因此稱其穩。

> $$g_ix = x_i$$.

### Lemma (stabilizer)
> $$g_iG_1 = G_i$$ for all $$i$$.

**Proof**

Consider the map $$\phi_i: G_1 \to G_i$$, given by $$\phi_i(g) = g_ig$$. We have for all $$g \in G_1$$, $$\phi_i(g)x = g_igx = g_ix = x_i$$. Therefore, $$\phi_i(g) \in G_i$$.

On the other hand, let $$\rho_i: G_i \to G_1$$ given by $$\rho_i(g) = g_1^{-1}g$$. Since both $$\rho_i \circ \phi_i$$ and $$\phi_i \circ \rho_i$$ are equal to the identity map, $$\rho_i$$ is the inver map of $$\phi_i$$.

Hence, $$\phi_i$$ is a bijection, which implies that

$$|G_1| = |G_i|$$

and $$G_i = g_iG_1$$. ◼

> identity map: $$f(x) = x$$.

### Theorem (stabilizer / ordit)
> Let $$G$$ be a group of symmetries of $$X$$. Fix $$x \in X$$ and let $$G_x = \{g_1x,\cdots,g_nx\}$$. Then
> 
> $$|G| = |G_x| \dot{} |\text{Stab}_G(x)|$$
>
> and
> 
$$G = \bigsqcup_{i=1}^{n-1}g_i\text{Stab}_G(x).$$ 

---

## The Group of Symmetries of a Regular $$N$$-gon
Let $$X$$ be a regular $$n$$-gon with the group of symmetries $$G$$. Let $$o$$ be the center of $$X$$ and $$x$$ be one of its vertex. We first have

$$G_x = \{x, \sigma(x),\cdots,\sigma^{n-1}(x)\},$$

where $$\sigma$$ is the **rotation** around the center $$o$$ of $$2\pi/n$$ degree.

