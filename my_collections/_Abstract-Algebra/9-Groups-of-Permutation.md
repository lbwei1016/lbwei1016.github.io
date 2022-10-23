---
layout: page
title: Groups of Permutation
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/09/30
---

**Table of Content**
- [Theorem](#theorem)
- [Cycle Notations](#cycle-notations)
  - [Cyclic Permutation](#cyclic-permutation)
  - [Theorem (cycle notation)](#theorem-cycle-notation)
    - [Corollary (order)](#corollary-order)

---

> 參 [More on Groups](../5-More-on-Groups/#the-nature-of-groups)

## Theorem
> Let $$A$$ be a nonempty set. Then the set $$S_A$$ of all permutations of $$A$$ is **a group under composition**.

Let $$S_n$$ denote the group of all permutations of the set $$\{1, 2, \cdots n\}$$ of $$n$$ elements. The group $$S_n$$ is called the **symmetric group on $$n$$ letters**. For $$\sigma \in S_n$$, we express $$\sigma$$ in the form

$$\sigma = \begin{pmatrix}
  1 & 2 & \cdots & n \\ \sigma(1) & \sigma(2) & \cdots & \sigma(n)
\end{pmatrix}, $$

called the two-line notation of $$\sigma$$.

> For $$\sigma \circ \tau$$, we write $$\sigma \tau$$.

> $$S_n$$ is *nonabelian* for all $$n \ge 3$$.

---

## Cycle Notations

For a permutation 

$$\sigma = \begin{pmatrix}
1 & 2 & 3 & 4 & 5 \\ 2 & 3 & 1 & 5 & 4  
\end{pmatrix},$$

we could also denote $$\sigma$$ by $$(123)(45)$$ or $$(45)(123)$$, which are called the **cycle notation** of $$\sigma$$.

### Cyclic Permutation
When a permutation only contains **one cycle** of length $$> 1$$, it is called a **cyclic permutation (or a cycle)** and we can denote this permutation by this cycle for short.

**e.g.**

For $$\sigma_1 = (12)(3)(4)(5)$$, denote $$\sigma_1$$ by $$(12)$$ for short; for $$\sigma_2 = (1)(2)(345)$$, denote $$\sigma_2$$ by $$(345)$$ for short.

We can see that $$\sigma = \sigma_1\sigma_2 = \sigma_2\sigma_1 = (12)(345)$$.

> 可以將 cycle notation 視為 *disjoint cycles 的 product*。

### Theorem (cycle notation)
> In a permutation group,
> 1. every permutation can be written as a **product of disjoint cycles**;
> 2. two **disjoint** cycles **commute**.

> A cycle of length $$d$$ is of order $$d$$.

#### Corollary (order)
> If a permutation can be written as a product of disjoint cycles of length $$d_1, \cdots, d_k$$ . Then its order is equal to $$lcm(d_1, \cdots, d_k)$$.

> $$\sigma$$ is of order $$n$$: $$\sigma^n = e$$.

> 想想 [cyclic groups](../8-Cyclic-Subgroups/#definition-order)。