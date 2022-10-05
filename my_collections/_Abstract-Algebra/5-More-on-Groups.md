---
layout: page
title: More on Groups
usemathjax: true
tag: Abstract Algebra
time: 2022/09/22
---

**Table of Content**
- [Group of small order](#group-of-small-order)
  - [Order 1](#order-1)
  - [Order 2](#order-2)
  - [Order 3](#order-3)
  - [Order 4](#order-4)
- [The Nature of Groups](#the-nature-of-groups)
  - [Group of Symmetries](#group-of-symmetries)
- [Special Groups](#special-groups)
- [Reference](#reference)

---

## Group of small order

> the cardinality of a group $$G = $$ the order of $$G$$

### Order 1

$$G = \{e\}$$ is unique and $$G \cong \mathbb{Z}_1 = \{\bar 0\}$$.


### Order 2

$$G = \{e, a\}$$, and $$a^{-1} = a$$ (the only choice).

藉由 **table**（如下）的方式，列出所有 element 經過 binary operation 的結果，再經過比對，可以得知 $$G \cong (\mathbb{Z}_2, +)$$。

| $$\dot{}$$ |   e   |   a   |
| :--------: | :---: | :---: |
|   **e**    |   e   |   a   |
|   **a**    |   a   |   e   |

|     $$+$$      | $$\bar 0$$ | $$\bar 1$$ |
| :------------: | :--------: | :--------: |
| **$$\bar 0$$** | $$\bar 0$$ | $$\bar 1$$ |
| **$$\bar 1$$** | $$\bar 1$$ | $$\bar 0$$ |

> $$\bar 0 \to e, \bar 1 \to a$$.

### Order 3

By cancellation law, **every column and every row in the table cannot contain a repeated element**.

$$G \cong (\mathbb{Z}_3, +)$$

### Order 4

Let $$G = \{e, a, b, c\}.$$

**Case $$\rm I$$**: $$a^2 = b^2 = c^2 = e$$

> 大家都是自己的 inverse。

透過 **table** 可以得知

$$G \cong \mathbb{Z}_2 \times \mathbb{Z}_2。$$

**Case $$\rm II$$**: $$a^2 = b$$

> 至少一元素不是自己的 inverse。
> 可以看出，兩個 case 是所有可能性的一個 partition，其聯集涵蓋所有情況。

一樣透過 **table** 可以得知

$$G \cong (\mathbb{Z}_4, +)。$$

> 注意！$$G$$ 的 order 到 $$4$$ 的時候終於出現非唯一的群！

---

## The Nature of Groups

**Groups** 的一大特性就是 **symmetry**！在正三角形上，有六種操作可以使她不變（三旋轉、三鏡射），相當於 $$G$$ such that \|$$G$$\|$$=6$$。

$$X = \Delta$$（正三角形）, $$Sym(X) = \{e, a, a^2, b, c, d\}$$

$$a$$ 是旋轉，$$b, c, d$$ 是三種鏡射。

### Group of Symmetries
Let $$X$$ be a **geometric object** and $$G$$ be the set of **symmetries** of $$X$$.
Then it is clear that $$G$$ have the following properties.
- The composition of two symmetries is a **binary operator** on $$G$$,
which is associative.
- The **identity** map (the trivial symmetry) is an element in $$G$$ and any symmetry composited with the identity map or the identity composited with any symmetry is equal to itself.
- The **inverse** map of a symmetry is still a symmetry.
- The **composition** of a symmetry and its inverse is equal to the identity map.

Therefore, the set of symmetries together with the composition operator form an **abstract group**.

When $$A$$ is just a set, a symmetry on $$A$$ is just a bijective function from $$A$$ to itself. When $$A$$ is finite, its symmetry is also called **a permutation of $$A$$**.

> 見 [Groups of Permutation](../9-Groups-of-Permutation)、[Dihedral Group](../B-n-gons/#dihedral-group)。

---

## Special Groups

- **General linear group**: of degree $$n$$ is the set of $$n\times n$$ **invertible matrices**, together with the operation of ordinary matrix multiplication, denote by $$GL_n(\mathbb{R})$$. (general linear group over $$\mathbb{R}.$$)

---

## Reference
- [Wiki](https://en.wikipedia.org/wiki/General_linear_group)
