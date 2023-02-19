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
  - [Lemma (fixed subset and stabilizer)](#lemma-fixed-subset-and-stabilizer)
  - [Theorem (order modulo)](#theorem-order-modulo)
  - [Theorem (center of $$p$$-groups)](#theorem-center-of-p-groups)
  - [Class equation](#class-equation)
    - [Definition (centralizer)](#definition-centralizer)
  - [Theorem (order $$p^2$$)](#theorem-order-p2)
  - [Definition (invariant)](#definition-invariant)
    - [Proof ($$Y$$ is a $$G$$-set)](#proof-y-is-a-g-set)
  - [Theorem (Cauchy's theorem)](#theorem-cauchys-theorem)
    - [**Proof**](#proof)
  - [**Remark**](#remark-1)

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

> 所以說，$$X^g$$ 就是那些經過 $$g$$ action 也不改變的 $$x$$，而 $$X^G$$ 就是經過所有 $$g$$ 都不改變的 $$x$$。

另外要注意的是，此處使用的 group action 是「左乘」，但我們也可以設 group action 為 *conjugation*（group $$G$$ acts on $$X$$ *by conjugation*）；也就是說，

$$
X^g = \{x\in X \mid gxg^{-1}=x\}
$$

也是合法的定義。（見 [Examples](../U-group-action/#examples) 的最末項。）

最後，$$g$$-fixed subset 可以和 stabilizer 相對應：一個收 $$x$$，另一個收 $$g$$。

### Lemma (fixed subset and stabilizer)
> Let $$G$$ be a group and $$X$$ a $$G$$-set. Then we have
> 
> $$\sum_{g\in G}\vert X^g\vert = \sum_{x\in X}\vert\text{Stab}_G(x)\vert.$$

**Proof**

Define a matrix $$M$$, whose rows are indexed by $$g\in G$$ and columns are indexed by $$x\in X$$, with entries 

$$
m_{g, x} = \begin{cases}
  1, &\text{if } gx = x, \\
  0, &\text{otherwise}.
\end{cases}
$$

If we count the number of $$1$$s in $$M$$ by the rows, we obtain the left hand side of the equation; on the other hand, if we count it by the columns, we exactly obtain the right hand side. By the *double counting principle*, the equation is valid. ◼

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

> 針對某一 $$x$$，收集所有使得 $$x$$ 可以交換的 $$g$$；也就是說，**the centralizer of $$x$$ 使 $$x$$ 彷彿置身 [center](../I-more-on-normal-subgroups/#definition-center)！**

> $$gx = xg,\  \forall g \in C_G(x)$$.

### Theorem (order $$p^2$$)
> Let $$G$$ be a group of order $$p^2$$, where $$p$$ is a prime. Then $$G$$ is **abelian**. Consequently, every group of order $$p^2$$ is isomorphic to $$\Bbb Z_p\times \Bbb Z_p$$ or $$\Bbb Z_{p^2}$$.

**Proof**

Since $$G$$ is a $$p$$-group, by this [theorem](#theorem-center-of-p-groups), $$Z(G)$$ is non-trivial. If $$Z(G) = G$$,  $$G$$ is abelian. Suppose that $$Z(G)$$ is a proper subgroup of $$G$$. Then $$Z(G)$$ and $$G/Z(G)$$ are both cyclic groups of order $$p$$. Let $$Z(G) = \langle a \rangle$$ and $$G/Z(G) = \langle bZ(G)\rangle$$ for some $$b\not \in Z(G)$$. Then every element in $$G$$ is of the form $$b^ia^j$$. On the other hand, this implies that 

$$
b(b^ia^j) = b^i(ba^j) = (b^ia^j)b,
$$

since $$a\in Z(G)$$. Thus we can conclude that $$b$$ is also contained in $$Z(G)$$, which is a contradiction. ◼

### Definition (invariant)
> Let $$X$$ be a $$G$$-set. A subset $$Y$$ of $$X$$ is called **$$G$$-invariant** if for all $$g\in G$$, $$gY \subset Y$$.
>
> In particular, $$Y$$ is also a $$G$$-set.

#### Proof ($$Y$$ is a $$G$$-set)

To prove this, we have to show that 

1. For all $$g\in G$$ and for all $$y\in Y$$, $$gy \in Y$$.
2. Let $$e$$ be the identiy of $$G$$. Then $$ey = y$$ for all $$y\in Y$$.
3. For all $$y\in Y$$ and for all $$g_1, g_2 \in G$$, $$g1(g2y) = (g1g2)y$$.

Since for all $$g\in G$$, $$gY\subset Y$$, **(1.)** is satisfied. **(2.)** and **(3.)** are trivially satisfied since $$Y$$ is a subset of a $$X$$, which is a $$G$$-set. ◼

### Theorem (Cauchy's theorem)
> Suppose that the order of a group $$G$$ is **divisible** by a **prime** $$p$$. Then $$G$$ has an element of order $$p$$.

#### **Proof**

Suppose that the order of $$G$$ is divisible by a prime $$p$$. Consider the $$p$$-th power of $$G$$,

$$
G^p = \{(g_1, \cdots, g_p)\mid g_i \in G \},
$$

and let $$\sigma = (1, \cdots, p) \in S_p$$. The group $$P = \langle \sigma \rangle$$ acts on $$G^p$$ by permuting the elements of $$(g_1, \cdots, g_p)$$.

Let $$Y = \{(g_1, \cdots, g_p)\in G^p \mid g_1\cdots g_p=e \}$$, where $$e$$ is the identity element of $$G$$. We observe that:

- $$\vert Y\vert  = \vert G\vert^{p-1}$$, since even if $$g_1, g_2,\cdots, g_{p-1}$$ are arbitrarily chosen, choose $$g_p = (g_1g_2\cdots g_{p-1})^{-1}$$ would  suffice.
- $$Y$$ is $$P$$-invariant, which means that $$Y$$ is a $$P$$-set.

By this [theorem](#theorem-order-modulo), we have

$$
\vert Y^P\vert \equiv \vert Y\vert = \vert G\vert^{p-1}\equiv 0 \pmod p.
$$

Note that $$y\in Y^P$$ iff $$y = (g,g,\cdots,g)$$ for some $$g\in G$$ with $$g^p = e$$, since $$Y^P \subset Y$$. Because $$\vert Y^P\vert \equiv 0\pmod p$$ and $$(e, e, \cdots, e) \in Y^P$$, $$Y^P$$ must contain at least $$p$$ elements. Then for any $$(g,\cdots, g)\in Y^P$$ with $$g\not = e$$, the order of $$g$$ is $$p$$, which satisfies the conclusion of this theorem. ◼

> 只有形如 $$(g, g, \cdots, g)$$ 這樣的 element 才不會被任何 $$\sigma_i \in P$$ 影響！

### **Remark**

[Lagrange's theorem](../F-Lagrange-thm) 指出，若有 order 為 $$n$$ 的 element，則 group size 可被 $$n$$ 整除。反過來成立嗎？若 $$G$$ 是交換群，根據 [the fundamental theorem of finitely generated abelian groups](../G-Finitely-Generated-Abelian-Groups/#theorem--fundamental-theorem-of-finitely-generated-abelian-groups)，$$G$$ 可以被拆為數個 $$\Bbb Z_{p_i^{e_i}}$$ 的 direct product，其中 $$p_i$$ 是 $$\vert G \vert$$ 的質因數且 $$e_i \in \Bbb N$$。可以觀察到，$$\Bbb Z_{p^k} = \langle 1 \rangle$$ 所有元素的 order 涵括了 $$p^k$$ 的所有因數：$$\langle p^i\rangle$$ 的 order 正是 $$p^{k-i}$$。於是對於 abelian group，Lagrange's theorem 的逆定理是成立的。

但若不是交換群呢？柯西定理就派上用場了，只不過多了質數的限制。