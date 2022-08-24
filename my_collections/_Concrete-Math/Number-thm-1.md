---
layout: page
title: Number Theory I
usemathjax: true
tag: Concrete Mathematics, Number Theory
time: 2022/08/23
---

**Table of Contents**
- [Primes](#primes)
  - [Fermat's (Little) Theorem](#fermats-little-theorem)
- [Euler's Theorem](#eulers-theorem)
  - [Theorem](#theorem)
  - [Euler totient function](#euler-totient-function)
    - [Properties](#properties)

---

## Primes

### Fermat's (Little) Theorem
> If $$n \perp p$$ , then $$n^{p-1} \equiv 1 \pmod p$$, for all $$n \in \mathbb{Z}^+$$

## Euler's Theorem
### Theorem
> generalization of [Fermat's (Little) Theorem](#fermats-little-theorem)

> If $$n \perp m$$ , then $$n^{\phi(m)} \equiv 1 \pmod m$$, for all $$n \in \mathbb{Z}^+$$

### Euler totient function
- $$\phi(m)$$
> number of integers in $$\{0, 1, \cdots, m-1\}$$ being *relative prime* to $$m$$.

#### Properties
$$\phi(p) = p-1 \tag{1}$$

$$\phi(p^k) = p^k - p^{k-1} \tag{2}$$

$$\phi(m) = m \prod_{p \setminus m} (1 - {1 \over p}) \tag{3}$$

$$\sum_{d \setminus m} \phi(d) = m \tag{4}$$

> Assume $$m = \prod_{p \setminus m} p^{m_p}$$. (質因數分解)


