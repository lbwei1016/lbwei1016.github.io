---
layout: page
title: Groups
usemathjax: true
tag: Abstract Algebra
time: 2022/09/22
---

**Table of Content**
- [Structural Properties](#structural-properties)
  - [Definition](#definition)
- [Identity Element](#identity-element)
  - [Definition](#definition-1)
  - [Theorem (uniqueness)](#theorem-uniqueness)
  - [Theorem (after mapped)](#theorem-after-mapped)
- [Groups](#groups)
  - [Definition (group)](#definition-group)
  - [Abelian Group](#abelian-group)
- [Properties of Groups](#properties-of-groups)
  - [Cancellation Law](#cancellation-law)
  - [Unique Solution](#unique-solution)
  - [Unique identity element and inverse](#unique-identity-element-and-inverse)

---

## Structural Properties

### Definition

> A **structural property** of a binary structure is one that must be shared by any **isomorphic structure**.

**e.g. (structural)**

- The set has $$4$$ elements.
- The operation is commutative.
- The equation $$a ∗ x = b$$ has a solution in $$S$$ for all $$a, b \in S$$.

> isomorphism map 過去之後，仍然保留的性質。

**e.g. (non-structural)**

1. The set $$S$$ is a subset of $$\mathbb{C}$$.（沒人說一定要在 $$\mathbb{C}$$）
2. The number $$4$$ is an element. 

**Problem**

> Show that the property that *the binary operator is commutative* is a structure property.

**Solution**

To prove the property, we have to show that if $$(S, *)$$ satisfies $$*$$ is commutative, then for any $$(S', *')$$ **isomorphic** to $$(S, *)$$, it also satisfies that $$*'$$ is commutative.

Assume $$*$$ is commutative on $$(S, *)$$. Given $$(S', *')$$ isomorphic to $$(S, *)$$, there exists a isomorphism $$\phi: S \to S'$$. Since $$\phi$$ is **onto**, for any $$a', b' \in S'$$, there exists $$a, b \in S$$ such that $$\phi(a) = a', \phi(b) = b'$$, respectively.

Then we have

$$a' *' b' = \phi(a) *' \phi(b) = \phi(a*b) = \phi(b*a) = \phi(b) *' \phi(a) = b' *' a'.$$

Hence $$*'$$ is commutative on $$(S', *')$$, which implies *the binary operator is commutative* is a structure property. ◼

---

## Identity Element

### Definition

> Let $$(S, *)$$ be a binary structure. An element $$e$$ of $$S$$ is an identity element for $$*$$ if $$e * s = s * e = s$$ for all $$s \in S$$.

**e.g.**

- $$0$$ in $$(Z, +)$$
- $$\bar 1$$ in $$(\mathbb{Z}_n, ·)$$

### Theorem (uniqueness)

> A binary structure $$(S, *)$$ has at most one identity element. That is, if there is an identity element, then it is **unique**.

**Proof**（反證法，略）

### Theorem (after mapped)

> Suppose that $$(S, *)$$ has an identity element $$e$$ for $$*$$. If $$\phi: S \to S'$$ is an isomorphism of $$(S, *)$$ with $$(S', *')$$, then $$\phi(e)$$ is an identity element for $$*'$$.

**Proof**

We need to show that 

$$\phi(e) *' s' = s' *' \phi(e) = s'$$

for all $$s' \in S'.$$

> 用 isomporhism 的性質。

--- 

## Groups
### Definition (group)

> A group $$(G, *)$$ is a set $$G$$, with a binary operation $$*$$, such that
> 1. $$*$$ is **associative**.
> 2. There exists an **identity element** $$e \in G$$ for $$*$$
> 3. There is an **inverse** $$a'$$ of $$a$$ such that $$a' * a = a * a' = e$$, for all $$a \in G$$.

**e.g. (a group)**

- $$(\mathbb{Z}, +)$$;
- $$(\mathbb{Z}_n, +)$$;
- $$(M_{m\times n}(\mathbb{R}), +)$$; ...

> 第三例是 entry 為實數的 $$m \times n$$ matrices。

**e.g. (not a group)**

- $$(\mathbb{Z}, \dot{})$$, only $$a = \pm 1$$ has an inverse; 
- $$(\mathbb{Z}_n, \dot{})$$, inverse of $$\bar 0$$ doesn't exist;
- $$(\mathbb{Z}_{>0}, +)$$, no identity element; ...

再舉一個大例子：

> The set $$GL(n, \mathbb{R})$$ of all invertible $$n \times n$$ matrices under matrix multiplication *is a group*. ($$GL$$ stands for general linear.)

要驗證 $$GL$$ 是不是 group，除了[定義](#definition)的三個條件之外，還要確認 $$GL$$ 是不是 **closed under multiplication**！（因為 $$GL$$ 只是某 binary structure 的子集）

> 利用 $$det(AB) = det(A)det(B)$$ 驗證。

### Abelian Group
> A group $$(G, *)$$ is **abelian** if its binary operation is **commutative**.

> $$+$$ 保留給 commutative binary operation，其他用 $$\dot{}$$ (multiplication)。(Notation)

---

## Properties of Groups

> Suppose $$G$$ is a group.

### Cancellation Law

> $$ab = ac \implies b = c$$, and $$ba = ca \implies b = c$$, for all $$a, b, c \in G$$.

> 用 $$a^{-1}$$ 和 $$e$$ 證明。

### Unique Solution

> $$ax = b$$ and $$ya = b$$ have unique solutions $$x$$ and $$y$$ in $$G$$.

**Proof $$\rm I$$ (existence)**

Let $$x = a^{-1}b$$ ...

**Proof $$\rm II$$ (uniqueness)**

Suppose $$ax_1 = b = ax_2$$ ...

### Unique identity element and inverse

> $$a^{-1}$$ and $$e$$ is unique, for $$a \in G$$.

> 基本上 *uniqueness* 都是用反證法。

**Corollary**

> For all $$a, b \in G$$, $$(ab)^{-1} = b^{-1}a^{-1}$$.