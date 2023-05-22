---
layout: page
title: Computation on Galois Groups
usemathjax: true
tag: Abstract Algebra, Galois Theory
time: 2023/05/22
---

**Table of Content**


---

> Too many things to write. Here are only some important notes.

## Cyclotomic extension
### Theorem (subextension: Galois)
> Any subextension of a cyclotomic extension $$\Bbb Q(\zeta_n)/\Bbb Q$$ is **Galois**. 

**Proof**

We have $$\text{Gal}(\Bbb Q(\zeta_n)/\Bbb Q) \cong \Bbb Z_n^\times$$ and $$\Bbb Z_n^\times$$ is abelian. Since every subgroup of a abelian group is a normal subgroup, by [the Galois theory](../Galois-theory), any subextension of $$\Bbb Q(\zeta_n)/\Bbb Q$$ is normal, and hence Galois. ■

---

## Transitive subgroups
### Lemma (transitive -> p-cycle)
> Let $$p$$ be a prime. Then **any** transitive subgroup of $$S_p$$ has a **$$p$$-cycle**.

**Proof**

Let $$H$$ be a transitive subgroup of $$S_p$$, and let $$H$$ act on $$\{1, 2, \cdots, p\}$$. By [the orbit-stabilizer theorem](../group-action/#theorem-the-orbit-stabilizer-theorem), we have

$$
\vert H\vert = \vert H_x\vert \cdot \vert \text{Stab}_H(x)\vert = pq,
$$

for some positive integer $$q$$. Then by [the Cauchy's theorem](../more-group-action/#theorem-cauchys-theorem), $$H$$ has an element of order $$p$$, which implies that $$H$$ has a $$p$$-cycle. ■