---
layout: page
title: More on Normal Subgroups
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/10/27
---

**Table of Content**
- [Theorem (correspondence of normal subgroups)](#theorem-correspondence-of-normal-subgroups)
- [Center & Commutator](#center--commutator)
  - [Definition (center)](#definition-center)
  - [Proposition (normal subgroup)](#proposition-normal-subgroup)
  - [Definition (commutator subgroup)](#definition-commutator-subgroup)
    - [Remark (when $$G/N$$ is abelian?)](#remark-when-gn-is-abelian)
  - [Theorem (normal subgroup)](#theorem-normal-subgroup)
  - [Remark (center and commutator)](#remark-center-and-commutator)
  - [Example (find the center and the commutator)](#example-find-the-center-and-the-commutator)
- [Normal Core](#normal-core)

---

## Theorem (correspondence of normal subgroups)

> Let $$\phi: G\to G'$$ be a group homomorphism. If $$N$$ is a normal subgroup of $$G$$, then **$$\phi(N)$$ is a normal subgroup of $$\phi(G)$$**. Conversely, if $$N'$$ is a normal subgroup of $$\phi(G)$$, then **$$\phi^{-1}(N')$$ is a normal subgroup of $$G$$**.

注意到 scope 的不同！第一項 $$\phi(N)$$ is a normal subgroup of $$\phi(G)$$，僅是 $$\phi(G)$$ 的 subgroup 而非整個 $$G'$$；第二項則是整個 $$G$$。

---

## Center & Commutator
### Definition (center)
> Let $$G$$ be a group. Then the subgroup
>
>$$
>Z(G) = \{x\in G\vert xg = gx,  \forall g\in G\}
>$$
>
>is called the **center** of $$G$$. 

> Center 的大小標示著 $$G$$ 的**可交換性**。

### Proposition (normal subgroup)

> $$Z(G)$$ is a **normal subgroup** of $$G$$.

**prove that $$Z(G)$$ is normal**

$$
gZ(G) = \{gx\vert x \in Z(G) \} = \{xg \vert x\in Z(G)\} = Z(G)g. \tag*{$\blacksquare$}
$$

### Definition (commutator subgroup)

> Let $$G$$ be a group. An element of the form $$a^{-1}b^{-1}ab$$ is a **commutator** of the group. The subgroup **generated** by all the commutators is called the **commutator subgroup**, and is denoted by $$[G,G]$$.

> Commutator 的大小標示著 $$G$$ 的**不可交換性**。

> 對於 $$S_n$$ 來說，commutator 一定是 **even permutation**！

#### Remark (when $$G/N$$ is abelian?)

Suppose that $$N$$ is a normal subgroup of $$G$$ such that $$G/N$$ is *abelian*. Then we have $$(aN)(bN) = (bN)(aN)$$, or equivalently, 

$$
\begin{align*}
&abN = baN, \\
&\Rightarrow (ba)^{-1}abN = N, \\ 
&\Rightarrow a^{-1}b^{-1}ab \in N.
\end{align*}
$$

Thus $$N$$ must contain all the commutators.

> The definition of commutator subgroups arises naturally when we try to determine **when $$G/N$$ is abelian**.


### Theorem (normal subgroup)

> The commutator subgroup $$[G,G]$$ is a normal subgroup. Moreover, suppose that $$N$$ is a normal subgroup of $$G$$. Then $$G/N$$ is abelian iff $$[G,G]<N$$.

**Proof**

We first show that $$[G,G]$$ is a normal subgroup of $$G$$, i.e. $$[G,G]\triangleleft G$$. It suffices to prove that the generators (commutators) satisfy $$g^{-1}(a^{-1}b^{-1}ab)g \in [G,G]$$ for all $$a,b,g \in G $$.

> 見 [remark](../H-homomorphism/#remark)。

We have

$$
\begin{align*}
g^{-1}(a^{-1}b^{-1}ab)g &= g^{-1}a^{-1}b^{-1}a(gbb^{-1}g^{-1})bg \\
&= g^{-1}a^{-1}b^{-1}agb(b^{-1}g^{-1}bg) \\
&= [(ag)^{-1}b^{-1}(ag)b](b^{-1}g^{-1}bg),
\end{align*}
$$

which is the product of two commutators. Thus, $$g^{-1}(a^{-1}b^{-1}ab)g\in [G,G] $$, and $$[G,G] \triangleleft G$$.

The proof of the second statement has already been shown in the [previous remark](#remark-when-gn-is-abelian). ◼

### Remark (center and commutator)

Center 和 commutator 是一種相反的概念：對於可交換群 $$G$$，$$Z(G) = G$$ 而 $$[G,G] = \{e\}$$。

### Example (find the center and the commutator)

以 $$S_3$$ 為例。$$S_3$$ 共有 $$6$$ 個 subgroups：

$$
\{e\}, {\langle (123) \rangle}, {\langle (23) \rangle}, {\langle (12) \rangle}, {\langle (13) \rangle}, S_3。
$$

可以明顯看出，$${\langle (23) \rangle}, {\langle (12) \rangle}, {\langle (13) \rangle}$$ 都不 normal（$$gH \not = Hg$$, for $$g = (123)$$），所以 $$S_3$$ 的 normal subgroups 共有 $$\{e\}, \langle (123) \rangle, S_3$$。

直接從定義看，$$Z(G)$$ 只可能是 $$\{e\}$$。因為 $$S_3$$ 不是 abelian，所以 $$[S_3, S_3] \not = \{e\}$$，又因為 [commutator 一定是 *even permutation*](#definition-commutator-subgroup)，所以 $$[S_3,S_3] \not = S_3$$；於是 $$[S_3, S_3] = \langle (123) \rangle$$。

---

## Normal Core 

