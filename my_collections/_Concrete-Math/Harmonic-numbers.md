---
layout: page
title: Harmonic Numbers
usemathjax: true
tag: Concrete Mathematics, Special Numbers
time: 2022/09/06
---

**Table of Content**
- [Defintion](#defintion)
  - [Harmonic numbers of order $$r$$](#harmonic-numbers-of-order-r)
  - [Riemann's zeta function](#riemanns-zeta-function)
- [Identities](#identities)
- [Summation](#summation)
- [Reference](#reference)

---

## Defintion

$$H_n = \sum_{k=1}^n {1 \over k},\ n \in \mathbb{N}$$

> $$H_0 = \sum_{k=1}^0{1 \over k} = 0$$，沒有除以 $$0$$ 的風險

### Harmonic numbers of order $$r$$

$$H^{(r)}_n = \sum_{k=1}^n{1 \over k^r}$$

### Riemann's zeta function

$$\zeta(r) = H^{(r)}_\infty = \sum_{k \geq 1}{1 \over k^r}$$

---

## Identities

$$\lim_{n \to \infty}(H_n - \ln n) = \gamma \approx 0.577218$$

> $$\gamma$$: Euler's constant

---

## Summation

$$\sum_{0 \leq k < n}H_k = nH_n - n \tag{1}$$

> summation by parts

$$\sum_{k=1}^nH^{(2)}_k = (n+1)H^{(2)}_n - H_n \tag{2}$$

> 改變 sum 的順序

> 注意上界（含不含 $$n$$）

---

## Reference
- [CMath] (p.264), Concrete Mathematics: A Foundation for Computer Science, by Ronald Graham, Donald Knuth, and Oren Patashni