---
layout: page
title: Normal Subgroups with Small Indexes & Normalizer
usemathjax: true
tag: Abstract Algebra, normal subgroups
time: 2023/03/02
---

**Table of Content**
- [Normal Subgroups with Small Indexes](#normal-subgroups-with-small-indexes)
  - [Theorem (smallest index; normal)](#theorem-smallest-index-normal)
    - [Proof](#proof)
  - [Corollary (two primes)](#corollary-two-primes)
- [Normalizer](#normalizer)
  - [Definition (conjugate subgroups)](#definition-conjugate-subgroups)
  - [Definition (normalizer)](#definition-normalizer)
  - [Lemma (index congruent)](#lemma-index-congruent)
- [Reference](#reference)

---

## Normal Subgroups with Small Indexes
### Theorem (smallest index; normal)
> Let $$G$$ be a finite group and $$p$$ be the smallest prime factor of $$\vert G\vert$$. Then every subgroup $$H$$ of **index $$p$$** is a **normal** subgroup.

> [This proposition](../H-homomorphism-and-normal-groups/#proposition-index-two) is a special case of this theorem.

#### Proof

Let $$X=G/H$$. Then $$\vert X\vert =p$$ and $$G$$ acts on $$X$$ by left multiplication, which induces a group homomorphism $$\rho: G\to S_X$$. We claim that $$H$$ is the **kernel** of $$\rho$$, which implies that $$H$$ is normal.

From [the first isomorphism theorem](../X-3-isomorphism/#the-first-isomorphism-theorem), we have 

$$
G/\text{ker}\rho \cong \rho(G) \leq S_X,
$$

which means that 

$$
[G:\text{ker}\rho] \mid p!
\implies [G:\text{ker}\rho]\mid \gcd(p!, \vert G\vert).
$$

> $$\vert G/\text{ker}\rho\vert = [G:\text{ker}\rho]$$; $$\vert S_X\vert = p!$$.

Since $$p$$ is the smallest prime divisor of $$\vert G\vert$$, $$[G:\text{ker}\rho] = 1$$ or $$p$$.

On the other hand, we have

$$
\text{ker}\rho = \bigcap_{xH\in X} \text{Stab}_G(xH) \subset \text{Stab}_G(H) = H.
$$

> For some $$xH\in X$$ and for all $$g\in \text{Stab}_G(xH), gxH = \rho(g)xH = xH$$.

> 然後取交集，對所有 $$xH\in X$$！

Comparing the indexes, we have

$$
[G : \text{ker}\rho] = [G : H][H : \text{ker}\rho] = p[H : \text{ker}\rho].
$$

Together with the result $$[G:\text{ker}\rho]=1$$ or $$p$$, we conclude that $$[G:\text{ker}\rho]=p$$ and $$[H:\text{ker}\rho]=1$$, which implies that $$H=\text{ker}\rho$$. ◼

### Corollary (two primes)
> If $$\vert G\vert = pq$$, where $$p>q$$ are two primes, then $$G$$ contains a normal subgroup of order $$p$$.

---

## Normalizer
### Definition (conjugate subgroups)
> Two subgroups $$H_1$$ and $$H_2$$ of a group $$G$$ are called **conjugate subgroups** if there **exists** a $$g$$ in $$G$$ such that $$gH_1g^{-1} = H_2$$. Note that this defines an **equivalence relation**. 

### Definition (normalizer)
> Let $$H$$ be a subgroup of a group $$G$$. The set
> 
> $$
>   \{g\in G\mid gHg^{-1}=H \}
> $$
> 
> is called the **normalizer** of $$H$$ in $$G$$ denoted by **$$N(H)$$**, which is the *largest subgroup of $$G$$ containing $$H$$ as a normal subgroup*.

Let $$X$$ be the set of subgroups of $$G$$ **conjugate** to $$H$$, and let $$G$$ acts on $$X$$ by conjugation. For $$x=H$$, we have $$\text{Stab}_G(x) = N(H)$$ and

$$
\vert G\vert = \vert X\vert \vert N(H)\vert ,
$$

by the [orbit-stablizer theorem](../U-group-action/#theorem-the-orbit-stabilizer-theorem).

### Lemma (index congruent)
> Let $$H$$ be a **$$p$$-subgroup** of a finite group $$G$$. Then 
>
> $$
>   [N(H):H]\equiv [G:H] \pmod p.
> $$

**Proof**

Let $$X$$ be the set of all left cosets of $$H$$. Let $$H$$ acts on $$X$$ by left multiplication. Since $$H$$ is a [$$p$$-group](../V-more-group-action/#theorem-order-modulo), we have

$$
\vert X\vert \equiv\vert X^H\vert \pmod p.
$$

Moreover, for $$gH\in X^H$$,

$$
(hg)H = gH,
$$

for all $$h\in H$$, which implies that 

$$
g^{-1}hg \in H \implies g \in N(H).
$$

Therefore, $$\vert X^H\vert =[N(H):H]$$ and we have

$$
\vert X\vert =[G:H] \equiv [N(H):H]=\vert X^H\vert \pmod p. \tag*{$\blacksquare$}
$$

---

## Reference
- [Groupprops: Conjugate subgroups](https://groupprops.subwiki.org/wiki/Conjugate_subgroups)