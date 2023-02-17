---
layout: page
title: More on Group Action
usemathjax: true
tag: Abstract Algebra, Group
time: 2023/02/17
---

**Table of Content**
- [$$p$$-Groups](#p-groups)
  - [Definition (fixed subset)](#definition-fixed-subset)
    - [Remark](#remark)
  - [Theorem (order modulo)](#theorem-order-modulo)
  - [Theorem (center of $$p$$-groups)](#theorem-center-of-p-groups)
  - [Class equation](#class-equation)
    - [Definition (centralizer)](#definition-centralizer)
  - [Theorem (order $$p^2$$)](#theorem-order-p2)

---

## $$p$$-Groups
### Definition (fixed subset)
> Let $$X$$ be a $$G$$-set. For any element $$g\in G$$, we define
>
> $$
> X^g = \{x\in X \mid gx=x\},
> $$
>
> which is called the **$$g$$-fixed subset of $$X$$**. Additionally, we define 
>
> $$
> X^G = \bigcap_{g\in G}X^g,
> $$
>
> which is called the **$$G$$-fixed subset of $$X$$**. Note that **$$x\in X^G$$ iff $$G_x = \{x\}$$**.

#### Remark

> Note that **$$x\in X^G$$ iff $$G_x = \{x\}$$**.

為什麼？因為 $$X^G$$ 是 $$X^g$$ 的聯集，代表 $$X^G$$ 含有「**對所有 $$g\in G$$，不受 $$g$$ 影響的 $$x$$**」。

另外要注意的是，此處使用的 group action 是「左乘」，但我們也可以設 group action 為 *conjugation*；也就是說，

$$
X^g = \{x\in X \mid gxg^{-1}=x\}
$$

也是合法的定義。（見 [Examples](../U-group-action/#examples) 的最末項。）

### Theorem (order modulo)
> Let $$p$$ be a **prime** and let $$G$$ be a finite **$$p$$-group** (i.e., the order of $$G$$ is a power of $$p$$) that acts on a finite set $$X$$. Then it holds that **$$\vert X\vert \equiv \vert X^G\vert \pmod p $$**, where $$X^G$$ is the fixed subset of $$X$$ under the action of $$G$$.

**Proof**

Let $$X_1,\cdots,X_k$$ be the collection of $$G$$-orbits that contain at least two elements. Then we have

$$
X = X^G \sqcup X_1 \sqcup \cdots \sqcup X_k.
$$

By [the orbit-stabilizer theorem](../U-group-action/#theorem-the-orbit-stabilizer-theorem), for all $$i$$, $$\vert X_i\vert$$ divides $$\vert G\vert$$, implying that $$\vert X_i \vert$$ is a multiple of $$p$$. Since the $$G$$-orbit form a partition of $$X$$, we obtain

$$
\vert X\vert = \vert X^G\vert + \vert X_1\vert + \cdots \vert X_k\vert \equiv \vert X^G\vert \pmod p. ◼
$$

### Theorem (center of $$p$$-groups)
> If $$G$$ is a finite $$p$$-group for some prime $$p$$, then the center **$$Z(G)$$ is non-trivial**. In particular, $$G$$ is not a [simple group](../I-more-on-normal-subgroups/#simple-groups) if $$G$$ is not of order $$p$$ (i.e., $$\vert G\vert = p^2, p^3, \cdots$$).

> not a simple group ?

> $$Z(G) \triangleleft G$$. See [Homomorphism & Normal Subgroups](../H-homomorphism-and-normal-groups/#definition-normal-subgroup).

**Proof**

Let $$G$$ act on $$X=G$$ by conjugation. By the theorem of the fixed subset of $$p$$-groups, we have

$$
\vert X^G \vert \equiv \vert X\vert \equiv \vert G\vert \equiv 0 \pmod p.
$$

Note that $$x\in X^G$$ iff $$gxg^{-1}=x$$ for all $$g\in G$$. Thus, $$X^G = Z(G)$$, which contains at least the identity. Combining the results, $$Z(G)$$ has at least $$p$$ elements.

### Class equation

For each element $$x\in G$$, the set of all elements conjugate to $$x$$ is referred to as the **conjugacy class** of $$x$$, denoted by $$[x]$$. *The stabilizer of $$x$$ under conjugation* is called the **centralizer** of $$x$$, deonted by $$C_G(x)$$. The size of the conjugacy class of $$x$$ is $$[G:C_G(x)]$$, as stated by [the orbit-stabilizer theorem](../U-group-action/#theorem-the-orbit-stabilizer-theorem).

Let $$[G]$$ be the collection of all conjugacy classes of $$G$$. Then the **class equation** states that 

$$
\vert G\vert =\vert Z(G)\vert + \sum_{[x]\in [G], x\not \in Z(G)} [G: C_G(x)].
$$

#### Definition (centralizer)
> Let $$X$$ be a $$G$$-set. The centralizer of $$x\in X$$ is defined as
>
> $$
>   C_G(x) = \{g\in G \mid gx = xg\}.
> $$

> Under conjugacy, stabilizer becomes centralizer!

### Theorem (order $$p^2$$)
> Let $$G$$ be a group of order $$p^2$$, where $$p$$ is a prime. Then $$G$$ is **abelian**. Consequently, every group of order $$p^2$$ is isomorphic to $$\Bbb Z_p\times \Bbb Z_p$$ or $$\Bbb Z_{p^2}$$.

**Proof**

Since $$G$$ is a $$p$$-group, by this [theorem](#theorem-center-of-p-groups), $$Z(G)$$ is non-trivial. If $$Z(G) = G$$,  $$G$$ is abelian. Suppose that $$Z(G)$$ is a proper subgroup of $$G$$. Then $$Z(G)$$ and $$G/Z(G)$$ are both cyclic groups of order $$p$$. Let $$Z(G) = \langle a \rangle$$ and $$G/Z(G) = \langle bZ(G)\rangle$$ for some $$b\not \in Z(G)$$. Then every element in $$G$$ is of the form $$b^ia^j$$. On the other hand, this implies that 

$$
b(b^ia^j) = b^i(ba^j) = (b^ia^j)b,
$$

since $$a\in Z(G)$$. Thus we can conclude that $$b$$ is also contained in $$Z(G)$$, which is a contradiction. ◼