---
layout: page
title: Binary Operations
usemathjax: true
tag: Algebra
time: 2022/09/20
---

**Table of Content**
- [Definition](#definition)
  - [Binary Operation](#binary-operation)
  - [Induced Operation](#induced-operation)
- [Commutativity and Associativity](#commutativity-and-associativity)

---

## Definition
### Binary Operation

> A **binary operation** $$*$$ on a set $$S$$ is a function *mapping $$S \times S$$ into $$S$$.*

**e.g.**

一般的 $$+$$ (addition) 是 $$\mathbb{R}$$ 上的 binary operation；但 $$/$$ (division) 不是，因為 $$a/0$$ 未定義。

### Induced Operation
> Let $$*$$ be a binary operation on a set $$S$$ and let $$H$$ be a subset of $$S$$. If for all $$a, b \in H$$ we also have $$a ∗ b \in H$$, then $$H$$ is **closed
under $$*$$**.

> In this case, the binary operation on $$H$$ given by restricting $$∗$$ to $$H$$ is the induced operation of $$*$$ on $$H$$.

**e.g.**

We have $$\mathbb{R} \subset \mathbb{C}$$. The addition $$+$$ on $$\mathbb{C}$$ induces a binary operation on $$\mathbb{R}$$.

---

## Commutativity and Associativity
> 參 [Introduction to Vectors](../../Linear-Algebra/1_Introduction-to-Vectors/#axiom)