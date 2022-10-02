---
layout: page
title: Subgroups
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/09/26
---

**Table of Content**
- [Definition $$\rm I$$](#definition-rm-i)
- [Definition $$\rm II$$](#definition-rm-ii)
- [Theorem $$\rm I$$](#theorem-rm-i)
- [Theorem $$\rm II$$ (Criterion of Subgroups)](#theorem-rm-ii-criterion-of-subgroups)

---

## Definition $$\rm I$$
> If a subset $$H$$ of a group $$G$$ is **closed** under the binary operation of $$G$$ and if $$H$$ with the induced operation from $$G$$ is itself a group,
then $$H$$ is a subgroup of $$G$$.

> Denoted by $$H \leq G$$ or $$G \geq H$$.

**Example**

Under addition, we have $$\mathbb{Z \leq Q \leq R \leq C}$$.

## Definition $$\rm II$$
> If $$G$$ is a group, then the subgroup consisting of $$G$$ itself is the **improper subgroup** of $$G$$. All other subgroups are **proper subgroups** of $$G$$.

> The subgroup $$\{e\}$$ is the trivial subgroup of $$G$$. All other subgroups are nontrivial.

## Theorem $$\rm I$$
> Let $$H$$ be a subgroup of $$G$$. Then the identity $$e_H$$ of $$H$$ is equal to the identity $$e_G$$ of $$G$$. Moreover, for all $$a \in H$$, the inverse of $$a \in H$$ is equal to the inverse of $$a \in G$$.

**Proof**

> By the definitions of identity and inverse.

## Theorem $$\rm II$$ (Criterion of Subgroups)
> A subset $$H$$ of a group $$G$$ is a subgroup of $$G$$ if and only if
1. $$H$$ is closed under the binary operation of $$G$$,
2. $$H$$ contains $$e_G$$ .
3. for all $$a \in H$$, the inverse $$a^{-1}$$ is also in $$H$$.

其實 1. 和 3. imply 2.，但 2. 的必要性在於防止 $$H$$ 是空集合，不過空集合作為 subgroup 沒什麼意義（是嗎？）。
