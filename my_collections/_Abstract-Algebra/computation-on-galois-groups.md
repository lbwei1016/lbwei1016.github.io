---
layout: page
title: Computation on Galois Groups
usemathjax: true
tag: Abstract Algebra, Galois Theory
time: 2023/05/22
---

**Table of Content**
- [Cyclotomic extension](#cyclotomic-extension)
  - [Theorem (subextension: Galois)](#theorem-subextension-galois)
- [Transitive subgroups](#transitive-subgroups)
  - [Lemma (transitive -\> p-cycle)](#lemma-transitive---p-cycle)
  - [Lemma (again p-cycle)](#lemma-again-p-cycle)
  - [Remark](#remark)
- [Misc](#misc)
  - [Theorem (Hilbert)](#theorem-hilbert)
  - [Theorem (any finite group; Galois)](#theorem-any-finite-group-galois)


---

> Too many things to write. Here are only some important notes.

## Cyclotomic extension
### Theorem (subextension: Galois)
> Any subextension of a cyclotomic extension $$\Bbb Q(\zeta_n)/\Bbb Q$$ is **Galois**. 

**Proof**

We have $$\text{Gal}(\Bbb Q(\zeta_n)/\Bbb Q) \cong \Bbb Z_n^\times$$ and $$\Bbb Z_n^\times$$ is abelian. Since every subgroup of an abelian group is normal, by [the Galois theory](../Galois-theory), any subextension of $$\Bbb Q(\zeta_n)/\Bbb Q$$ is normal, and hence Galois. ■

---

## Transitive subgroups
### Lemma (transitive -> p-cycle)
> Let $$p$$ be a prime. Then **any** transitive subgroup of $$S_p$$ has a **$$p$$-cycle**.

**Proof**

Let $$H$$ be a transitive subgroup of $$S_p$$, and let $$H$$ act on $$\{1, 2, \cdots, p\}$$. By [the orbit-stabilizer theorem](../group-action/#theorem-the-orbit-stabilizer-theorem), we have

$$
\vert H\vert = \vert H_x\vert \cdot \vert \text{Stab}_H(x)\vert = pq,
$$

for some positive integer $$q$$. Then by [Cauchy's theorem](../more-group-action/#theorem-cauchys-theorem), $$H$$ has an element of order $$p$$, which implies that $$H$$ has a $$p$$-cycle. ■

> Since $$H$$ is transitive, $$\vert H_x\vert = p$$.

### Lemma (again p-cycle)
> If $$f(x)$$ is irreducible over $$\Bbb Q$$ of some prime degree $$p$$, then $$G = \text{Gal}(\Bbb{Q}_f/\Bbb Q)$$ contains a $$p$$-cycle.

**Proof**

Since $$f(x)$$ is irreducible, $$\deg(f) = p \mid \vert G\vert$$. By Cauchy's theorem, $$G$$ has an element of order $$p$$. ■

### Remark

計算 Galois group $$G$$ 的時候，只要給定的不可約多項式 $$f(x)$$ 的次數 $$n$$ 是質數，$$G$$ 就一定有 $$n$$-cycle！但若 $$n$$ 不是質數，就得找某質數 $$p$$，使得 $$f(x)$$ 在 $$\Bbb{Z}_p$$ 下是不可約的（然後 by Dedkind's theorem）。

---

## Misc
### Theorem (Hilbert)
> For **all** positive integers $$n$$, there exists an integer polynomial $$f(x)$$ of degree $$n$$ such that the **Galois group** of its splitting field $$\Bbb{Q}_f$$ over $$\Bbb Q$$ is **isomorphic to $$S_n$$**.

### Theorem (any finite group; Galois)
> For every **finite** group $$G$$, there exists a **Galois extension** $$E/F$$ such that $$\text{Gal}(E/F) \cong G$$.

**Proof**

Suppose $$\vert G\vert = n$$. By [Hilbert's theorem](#theorem-hilbert), there exists an integer polynomial $$f(x)$$ of degree $$n$$ such that the Galois group of its splitting field $$\Bbb{Q}_f$$ over $$\Bbb Q$$ is isomorphic to $$S_n$$. Let $$E = \Bbb{Q}_f$$. By [Cayley's theorem](../Cayley-thm), $$G$$ is isomorphic to a subgroup of $$S_n$$. Then, by [the fundamental theorem of Galois theory](../Galois-theory/#theorem-the-fundamental-theorem-of-galois-theory), there exists a subextension of $$E$$, $$E^G$$, such that $$\text{Gal}(E/E^G) \cong G$$. ■ 