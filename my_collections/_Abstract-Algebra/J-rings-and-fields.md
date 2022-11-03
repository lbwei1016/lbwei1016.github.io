---
layout: page
title: Rings and Fields
usemathjax: true
tag: Abstract Algebra, Ring, Field
time: 2022/11/32
---

**Table of Content**
- [Ring](#ring)
  - [Definition (ring)](#definition-ring)
  - [Examples](#examples)
  - [Some Little Definitions](#some-little-definitions)
- [Definition (about multiplication)](#definition-about-multiplication)
  - [Remark](#remark)
- [Subrings and Subfields](#subrings-and-subfields)
- [Homomorphism](#homomorphism)
  - [Definition (homomorphism)](#definition-homomorphism)
  - [Theorem (subring)](#theorem-subring)

---

## Ring
### Definition (ring)
> A **ring** $$\langle R,+,\cdot \rangle$$ is a set $$R$$ together with two binary operations $$+$$ and $$\cdot$$, called **addition** and **multiplication**, such that the following axioms are satisfied:
> - $$\langle R,+\rangle$$ is an *abelian* group.
> - Multiplication is associative.
> - For all $$a,b,c\in R$$, the **left distributive law** $$a\cdot(b+c) = (a\cdot b)+(a\cdot c)$$ and the **right distributive law** $$(a+b)\cdot c = (a\cdot c) + (b\cdot c)$$ hold. 

### Examples

- $$\mathbb{Z}_n$$ is a ring with $$\bar a + \bar b = \overline{a+b}$$ and $$\bar a \cdot \bar b = \overline{a\cdot b} $$.
- $$M_n(\mathbb{R})$$ of all $$n\times n$$ matrices is a ring.
- Let $$R_1$$ and $$R_2$$ be rings. The *direct product* of $$R_1$$ and $$R_2$$, $$R_1 \times R_2$$, is a ring, where $$+$$ and $$\cdot$$ are defined elementwise.
- Let $$\text{End}(V)$$ be the set if *all linear transformations from $$V$$ to $$V$$*. Let addition and multiplication be defined by 

$$
f+g: v\to f(v) + f(g),\ f\circ g: v\to f(g(v)).
$$

  Then $$\langle \text{End}(V), +, \circ \rangle$$ is a ring called the **endomorphism ring of $$V$$**.

### Some Little Definitions

- By convention we set $$0 \cdot a = 0_R$$, where the $$0$$ on the left-hand side is the integer $$0$$, while $$0_R$$ on the right is the **additive identity** element of $$R$$.

- A ring with a multiplicative identity is a **ring with unity**.

---

## Definition (about multiplication)

Let $$R$$ be a ring with unity $$1\not = 0$$.

1. An element $$u$$ of $$R$$ is a **unit** if it has a multiplicative inverse.
2. If every nonzero element of $$R$$ is a unit, then $$R$$ is a **division ring** (or **skew field**).
3. A *commutative division ring* is a **field**.

> **Field** 在這裡終於出現了！

### Remark

1. multiplicative **identity** element and **inverse(s)** are both **unique**.
2. For a ring $$R$$ with unity, the set of units forms a multiplicative group, denoted by $$R^{\times}$$, called **the group of units**.

---

## Subrings and Subfields

> 可從 [subgroup](../7-Subgroups) 的定義延伸，但是 denoted by $$S < R$$（$$S$$ 是 $$R$$ 的 subring/subfield）。

---

## Homomorphism
### Definition (homomorphism)

> For rings $$R$$ and $$R'$$, $$\phi: R\to R'$$ is a (ring) homomorphism if 
> 1. $$\phi(a+b) = \phi(a) + \phi(b)$$,
> 2. $$\phi(ab) = \phi(a)\phi(b)$$.
> 
> for all $$a,b \in R$$.


The **kernel** of $$\phi$$ is

$$\text{ker}(\phi) = \{a\in R\vert \phi(a) = 0\}.$$

> 映到加法單位元素才是 kernel！

### Theorem (subring)
> Let $$\phi: R\to R'$$ be a ring homomorphism. Then $$\phi(R)$$ is a **subring** of $$R'$$.

**e.g.**

The function $$\phi: \mathbb{Z}\to \mathbb{Z}_n$$ defined by $$\phi(a) = \bar a$$ is a ring homomorphism.

> 加法和乘法都要檢查！