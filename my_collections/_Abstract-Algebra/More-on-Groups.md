---
layout: page
title: More on Groups
usemathjax: true
tag: Abstract Algebra
time: 2022/09/22
---

**Table of Content**
- [Order](#order)
  - [Definition (order of a group)](#definition-order-of-a-group)
  - [Definition (order of an element)](#definition-order-of-an-element)
    - [**Remark (order divides order)**](#remark-order-divides-order)
- [Group of small order](#group-of-small-order)
  - [Order 1](#order-1)
  - [Order 2](#order-2)
  - [Order 3](#order-3)
  - [Order 4](#order-4)
  - [Order 6](#order-6)
  - [Order 8](#order-8)
- [Multiplicative Group $$\\mathbb{Z}\_n$$](#multiplicative-group-mathbbz_n)
  - [Theorem (inverse)](#theorem-inverse)
  - [Theorem (making a group)](#theorem-making-a-group)
- [The Nature of Groups](#the-nature-of-groups)
  - [Group of Symmetries](#group-of-symmetries)
- [Special Groups](#special-groups)
- [Reference](#reference)

---

## Order
### Definition (order of a group)
> The cardinality of a group $$G = $$ the order of $$G$$.

### Definition (order of an element)
> If $$g \in G$$ and for some $$m \in \mathbb{N}$$ such that $$g^m = e$$, then $$m$$ is called *exponent* of $$g$$. The **order** of $$g$$ is the **smallest such *exponent***, denoted by $$\text{ord}(g)$$. In this case we say $$g$$ is of finite order (otherwise infinite).

#### **Remark (order divides order)**
As a consequence of [Lagrange’s Theorem](../Lagrange-thm/#theorem), the order of an element $$g$$ of a group $$G$$ **divides** the group order \|$$G$$\| in case $$G$$ is finite.

## Group of small order
### Order 1

$$G = \{e\}$$ is unique and $$G \cong \mathbb{Z}_1 = \{\bar 0\}$$.


### Order 2

$$G = \{e, a\}$$, and $$a^{-1} = a$$ (the only choice).

藉由 **table**（如下）的方式，列出所有 element 經過 binary operation 的結果，再經過比對，可以得知 $$G \cong (\mathbb{Z}_2, +)$$。

| $$\cdot$$ |   e   |   a   |
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

> 只要 $$\vert G\vert$$ 是質數，則 $$G \cong \mathbb{Z}_p$$ 是唯一可能。

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

### Order 6

$$G \cong \mathbb{Z}_{6}$$ or $$G \cong S_3 \cong D_3$$.

### Order 8

如果 $$G$$ 可交換，則 $$G$$ 和 

$$
\mathbb{Z}_8, \mathbb{Z}_4\times\mathbb{Z}_2, (\mathbb{Z}_2)^3
$$

之一 isomorphic；如果不可交換，則和 $$D_4$$ 或 $$Q_8$$ isomorphic。

> $$Q_8 = \{\pm 1, \pm i, \pm j, \pm k \}$$.

---

## Multiplicative Group $$\mathbb{Z}_n$$

A **multiplicative group** is a group whose group operation is identified with multiplication. 但這裡主要討論的是 $$\mathbb{Z}_n$$。

### Theorem (inverse)
> For $$\bar a \in \mathbb{Z}_n$$, $$\bar a$$ has the **multiplicative inverse** if and only if $$a$$ and $$n$$ are *coprime*.

**Proof**

First, we show the *if* part. Consider $$a$$ and $$n$$ are coprime. By [Euclidean algorithm](../../Concrete-Math/extgcd), there exists $$(x, y)$$ such that 

$$ax + ny = \gcd(a, n) = 1.$$

We can see that $$\bar x$$ is the multiplicative inverse of $$\bar a$$ in $$\mathbb{Z}_n$$. 

Then, we show the *only if* part. Suppose $$\gcd(a, n) \not = 1$$, and $$\bar x$$ is the multiplicative inverse of $$\bar a$$. Then we can show that

$$ax + ny = 1,$$

for some $$y \in \mathbb{Z}$$. However, if we divide both sides by $$\gcd(a, n)$$, 

$$a'x + n'y = {1 \over \gcd(a, n)},$$

a contradiction occurs since $$a' = {a \over \gcd(a, n)}, n' = {n \over \gcd(a, n)} \in \mathbb{Z}$$, while $${1 \over \gcd(a, n)} \not \in \mathbb{Z}$$.

Thus we can conclude that $$a$$ and $$n$$ must be coprime. ◼

### Theorem (making a group)
> Let $$(S, *)$$ be an associative binary structure with identity and $$S'$$ be a subset of $$S$$ consisting **all elements with inverse**. Then $$(S', *)$$ is a group.

> 在「差點形成」（有 identity element 且 $$*$$ is associative） group 的 binary structure $$(S, *)$$ 中，只取出 $$S$$ 中有 inverse 的元素成為一 subset $$S'$$，則 $$(S', *)$$ 為一 group。


**Remark**
> Denote $$\mathbb{Z}_n^{\times}$$ the subset of $$\mathbb{Z}_n$$ consisting all elements with **multiplicative inverse**. $$(\mathbb{Z}_n^{\times}, \cdot)$$ is a *group*.

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

> 見 [Groups of Permutation](../Groups-of-Permutation)、[Dihedral Group](../n-gons/#dihedral-group)。

---

## Special Groups

- **General linear group**: of degree $$n$$ is the set of $$n\times n$$ **invertible matrices**, together with the operation of ordinary matrix multiplication, denote by $$\text{GL}_n(\mathbb{R})$$. (general linear group over $$\mathbb{R}.$$)
- **Special linear group**: $$\text{SL}_n(\mathbb{R})$$ is a group containing all $$n \times n$$ real matrices with **determinant equal to one**.

---

## Reference
- [Wiki](https://en.wikipedia.org/wiki/General_linear_group)
- [https://page.math.tu-berlin.de/~kant/Algebra/groups.pdf](https://page.math.tu-berlin.de/~kant/Algebra/groups.pdf)
- [Wolfram MathWorld](https://mathworld.wolfram.com/MultiplicativeGroup.html)