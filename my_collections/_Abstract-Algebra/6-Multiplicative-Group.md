---
layout: page
title: Multiplicative Group
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/09/26
---

**Table of Content**
- [Multiplicative Group $$\mathbb{Z}_n$$](#multiplicative-group-mathbbz_n)
  - [Theorem (inverse)](#theorem-inverse)
  - [Theorem (making a group)](#theorem-making-a-group)
- [Reference](#reference)

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
> Denote $$\mathbb{Z}_n^{\times}$$ the subset of $$\mathbb{Z}_n$$ consisting all elements with **multiplicative inverse**. $$(\mathbb{Z}_n^{\times}, \dot{})$$ is a *group*.

---

## Reference
- [Wolfram MathWorld](https://mathworld.wolfram.com/MultiplicativeGroup.html)