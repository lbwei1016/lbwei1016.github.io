---
layout: page
title: Introduction
usemathjax: true
tag: Abstract Algebra, Set, Basics
time: 2022/09/19
---

**Table of Content**
- [Set](#set)
  - [Cardinality](#cardinality)
    - [Schröder–Bernstein theorem](#schröderbernstein-theorem)
    - [Problems](#problems)
- [Misc](#misc)

---

## Set
### Cardinality
#### Schröder–Bernstein theorem
> $$(| A | \geq | B |) \land (| A | \leq | B |) \implies | A | = | B |$$

#### Problems

$$| \mathbb{C} | = | \mathbb{R} | ? \tag{1}$$

**Proof**

Define the mapping $$\phi: [0, 1) \times [0, 1) \to [0, 1)$$, where 

$$\phi((0.a_1a_2\cdots, 0.b_1b_2\cdots)) = 0.a_1b_1a_2b_2.$$

This is a bijection. ◼

$$| 2^{\mathbb{N}} | = | \mathbb{R} | \tag{2}$$

Define the mapping $$\rho: 2^{\mathbb{N}} \to [0, 1)$$, where

$$\rho(A) = (0.a_1a_2a_3\cdots)_2,\ a_i = [i \in A].$$

This is a bijection. ◼

> *Note:* $$\mathbb{R}$$ 和 $$[0, 1)$$ 之間存在 bijection。

---

## Misc

$$\mathbb{Q}^{\times} = \mathbb{Q} \backslash \{0\}$$ 

$$\mathbb{Z}_n = \mathbb{Z}/n\mathbb{Z} = \{\bar 0, \bar 1, \cdots, \overline{n-1} \}$$

> $$\bar 0, \bar 1, \cdots, \overline{n-1}$$ 是 $$\mathbb{Z}_n$$ 的 elements。

> 見 [Relation](../../Concrete-Math/Relation)