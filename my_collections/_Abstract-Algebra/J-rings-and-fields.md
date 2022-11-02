---
layout: page
title: Rings and Fields
usemathjax: true
tag: Abstract Algebra, Ring, Field
time: 2022/11/32
---

**Table of Content**

---

## Ring
### Definition
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

### Some Definitions

- By convention we set $$0 \cdot a = 0_R$$, where the $$0$$ on the left-hand side is the integer $$0$$, while $$0_R$$ on the right is the **additive identity** element of $$R$$.

- A ring with a multiplicative identity is a **ring with unity**.