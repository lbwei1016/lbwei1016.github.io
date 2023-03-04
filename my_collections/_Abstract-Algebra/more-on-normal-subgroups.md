---
layout: page
title: More on Normal Subgroups
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/10/27
---

**Table of Content**
- [Theorem (correspondence of normal subgroups)](#theorem-correspondence-of-normal-subgroups)
- [Center and Commutator](#center-and-commutator)
  - [Definition (center)](#definition-center)
  - [Proposition (normal subgroup)](#proposition-normal-subgroup)
  - [Definition (commutator subgroup)](#definition-commutator-subgroup)
    - [Remark (when $$G/N$$ is abelian?)](#remark-when-gn-is-abelian)
  - [Theorem (normal subgroup)](#theorem-normal-subgroup)
  - [Remark (center and commutator)](#remark-center-and-commutator)
  - [Example (find the center and the commutator)](#example-find-the-center-and-the-commutator)
- [Normal Core](#normal-core)
- [Normal Subgroup and Homomorphism](#normal-subgroup-and-homomorphism)
  - [Interlude: Automorphism](#interlude-automorphism)
    - [Automorphism group](#automorphism-group)
    - [Inner Automorphism](#inner-automorphism)
- [Simple Groups](#simple-groups)
  - [Definition](#definition)
  - [Normal Series](#normal-series)
  - [Theorem (classification of simple groups)](#theorem-classification-of-simple-groups)

---

## Theorem (correspondence of normal subgroups)

> Let $$\phi: G\to G'$$ be a group homomorphism. If $$N$$ is a normal subgroup of $$G$$, then **$$\phi(N)$$ is a normal subgroup of $$\phi(G)$$**. Conversely, if $$N'$$ is a normal subgroup of $$\phi(G)$$, then **$$\phi^{-1}(N')$$ is a normal subgroup of $$G$$**.

注意到 scope 的不同！第一項 $$\phi(N)$$ is a normal subgroup of $$\phi(G)$$，僅是 $$\phi(G)$$ 的 subgroup 而非整個 $$G'$$；第二項則是整個 $$G$$。

---

## Center and Commutator
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

> *Prove that $$[S_n, S_n] = A_n$$.*

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

> 見 [remark](../H-homomorphism-and-normal-groups/#remark)。

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

When $$H$$ is **not** normal, 

$$
\bigcap_{g\in G} gHg^{-1}
$$

is called the **normal core** of $$H$$, which is the **largest** normal subgroup contained in $$H$$.

> 改成 $$\bigcup$$ 就不是 subgroup 了！

---

## Normal Subgroup and Homomorphism

From [this theorem](../H-homomorphism/#theorem-homomorphism-and-normal-subgroups), we know that every normal subgroup $$N$$ of $$G$$ is a kernel of some group homomorphism $$\rho$$. To gain more insight of $$N$$, we shall look for a more *canonical* homomorphism.

**e.g.**

- Consider $$\rho: G\to \text{Aut}(G)$$ given by $$\rho(g) = \rho_g$$, where $$\rho_g: G\to G$$ is defined as $$\rho_g(x)=gxg^{-1} $$, and then $$\text{ker}(\rho) = Z(G)$$.
- Consider $$\rho: G\to S_{G/H} $$ given by $$\rho(g) = \lambda_g$$, where $$\lambda_g: G\to G$$ is defined as $$\lambda_g(xH) = gxH$$, and then $$\text{ker}(\rho) = \bigcap_{g\in G}gHg^{-1}$$.

這兩種 homomorphism 的 kernel 都是特殊的 normal subgroup。

第一例中的 $$\rho$$ 其實是 homomorphism，可以試著驗證看看；底下證明 $$\text{ker}(\rho) = Z(G)$$。

**Proof**

For all $$g \in \text{ker}(\rho)$$, we have

$$
\begin{align*}
&\rho(g) = I_G, \text{where } I_G \text{ is the identity automorphism on } G. \\
\Rightarrow\ &\rho_g(x) = I_G(x) = x,\ \forall x \in G \\
\Rightarrow\ &gxg^{-1} = x \\
\Rightarrow\ &gx = xg,\ \forall x \in G.
\end{align*}
$$

Thus, $$g \in Z(G)$$. ◼

第二個例子稱作 **generalized [Caley theorem](../C-Cayley-thm)**。$$S_{G/H}$$ 相較於 Cayley theorem 的 $$S_G$$，是較小的群，因此比較容易[應用](../C-Cayley-thm/#application)，但這是有代價的：Cayley theorem 中的 $$\text{ker}(\phi) = \{e\}$$，而此處 $$\text{ker}(\rho) = \bigcap_{g\in G}gHg^{-1}$$，也就是說，$$\rho$$ 不是 **one-to-one**！

底下證明 $$\text{ker}(\rho) = \bigcap_{g\in G}gHg^{-1}$$：

**Proof**

For all $$g \in \text{ker}(\rho)$$, we have $$\rho(g) = \lambda_e$$, i.e.

$$
\rho_g(x) = \lambda_e(xH) \iff gxH = xH.
$$

That is to say

$$
x^{-1}gxH = H \iff x^{-1}gx \in H \iff g \in xHx^{-1},\forall x \in H.
$$

This means that $$\text{ker}(\rho) = \bigcap_{x\in G}xHx^{-1}$$. ◼

> 事實上，Cayley theorem 是 $$H = \{e\}$$ 時的特例。

> Generalized Caley theorem 的應用待補。

### Interlude: Automorphism

What is an **automorphism**? An **automorphism** is an *isomorphism* with the same domain and codomain.

> $$\rho: G\to G$$，如果 $$\rho$$ 是 isomorphism，則 $$\rho$$ 又被稱為 **automorphism**。

#### Automorphism group

Given

$$
\text{Aut}(G) = \{\rho:G\to G \vert \rho \text{ is an isomorphism}\},
$$

then $$\text{Aut}(G)$$ is called the group of **automorphism** on $$G$$, which is in fact a **subgroup of $$S_G$$**.

> The set of all isomorphisms of $$G$$.

#### Inner Automorphism

- [Wolfram MathWorld](https://mathworld.wolfram.com/InnerAutomorphism.html)
- [Proof Wiki](https://proofwiki.org/wiki/Mapping_from_Group_Element_to_Inner_Automorphism_is_Homomorphism)

---

## Simple Groups

### Definition
> A group $$G$$ is **simple** if $$\{e\}$$ and $$G$$ are the **only two distinct normal subgroups** of $$G$$.

**e.g.**

If $$p$$ is a prime, then $$\mathbb{Z}_p$$ is a simple group.

For $$n\ge 5$$, the alternating group $$A_n$$ is a simple group.

### Normal Series

A **normal series** of a finite group $$G$$ is a sequence of subgroups $$G_i$$ of $$G$$ satisfies

$$
G_0 = \{e\} \triangleleft G_1 \triangleleft \cdots \triangleleft G_k = G.
$$

Note that $$G_i$$ is only *normal* in $$G_{i+1}$$ instead of $$G$$, and $$G_i/G_{i+1}$$ is *simple* for all $$i$$.

### Theorem (classification of simple groups)
> Every finite simple groups is isomorphic to one of the following groups:
> - a member of one of three infinite classes of such, namely:
>   - $$\mathbb{Z}_p$$ for all prime $$p$$.
>   - $$A_n$$ for $$n\ge 5$$.
>   - the groups of Lie type. (Certain matrix groups over finite fields.)
> - one of $$26$$ groups called the *sporadic groups*.
> - the *Tits group* (sometimes considered a $$27$$th sporadic group.)