---
layout: page
title: More on Normal Subgroups
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/10/27
---

**Table of Content**

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

### Proposition (normal subgroup)

> $$Z(G)$$ is a **normal subgroup** of $$G$$.

**prove that $$Z(G)$$ is normal**

$$
gZ(G) = \{gx\vert x \in Z(G) \} = \{xg \vert x\in Z(G)\} = Z(G)g. \tag*{$\blacksquare$}
$$

> Center 的大小標示著 $$G$$ 的**可交換性**。

### Definition (commutator subgroup)

> Let $$G$$ be a group. An element of the form $$a^{-1}b^{-1}ab$$ is a **commutator** of the group. The subgroup **generated** by all the commutators is called the **commutator subgroup**, and is denoted by $$[G,G]$$.

#### Remark

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

We first show that $$[G,G]$$ is a normal subgroup of $$G$$, i.e. $$[G,G]\triangleleft G$$. It suffice to prove that the generators (the commutators) satisfy $$g^{-1}(a^{-1}b^{-1}ab)g \in [G,G]$$ for all $$a,b,g \in G $$.

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

The proof of the second statement has already been seen in the [last remark](#remark). ◼