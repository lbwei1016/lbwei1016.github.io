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
  - [Question (prove subgroup)](#question-prove-subgroup)

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

> $$H$$ is closed，但沒有說 for $$g_1,g_2 \not \in H,\ g_1g_2 \in H$$ 是錯的！（外部可闖入；可用 $$\mathbb{Z}_{12}$$ 找例子。）

### Question (prove subgroup)

**Q1:**

Let $$G = \mathbb{Z}\times\mathbb{Z}, H = \langle(2,1),(1,2)\rangle,$$ and $$N = \langle(3, 0), (0, 3) \rangle$$. Show that $$N \le H$$.

**Solution**

It is obivous that $$H\le G$$ and $$N\le G$$ since they are [defined as groups](../B-n-gons/#dihedral-group). Thus it suffices to show that $$N$$ is a subset of $$H$$: For all $$h \in H$$, $$h = (2a+b, a+2b)$$, where $$a,b \in \mathbb{Z}$$; for all $$g\in N$$, $$g=(3c, 3d)$$, where $$c,d\in \mathbb{Z}$$. To show that for all $$g\in N$$, $$g$$ is also in $$H$$, we have

$$
2a+b = 3c, a+2b = 3d,
$$

which means that $$a=2c-d$$ and $$b=2d-c$$ and they are both integers. Thus $$N\subseteq H$$ and $$N\le H$$. ◼

**Q2:**

Let $$g$$ be an element if a group $$G$$. Show that the following is a subgroup:

$$
C_G(g) = \{x\in G\vert gx=xg\}.
$$

**Solution**

**closedness**

For all $$x,y \in C_G(g)$$, $$gx = xg$$ and $$gy = yg$$. Then $$gxy = xgy = xyg$$, which means that $$xy \in C_G(g)$$.

**identity**

Since $$eg = e = ge$$, $$e\in C_G(g)$$.

**inverse**

For all $$x \in C_G(g)$$, $$gx = xg$$. Multiply both sides of the equation by $$x^{-1}$$ from both left and right, we obtain $$x^{-1}g = gx^{-1}$$. We conclude that $$x^{-1}\in C_G(g)$$.

Combing the above results, $$C_G(g)$$ is a subgroup. ◼