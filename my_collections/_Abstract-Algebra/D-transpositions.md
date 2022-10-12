---
layout: page
title: Transposition
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/10/12
---

**Table of Content**


---

## Transposition
### Definition (transposition)
> A cycle $$(ij)$$ of length $$2$$ in $$S_n$$ is a **transposition**. When $$j=i \pm 1$$, it is called an **adjacent transposition**.

### Theorem (product)
> Any permutation in $$S_n$$ of at least two elements is a product of **(adjacent) transposition**.

#### Proof

If $$\sigma$$ is the identity element, we have $$\sigma = (1,2)(1,2)$$. Otherwise, write $$\sigma$$ as a product of cycles. Now for a transposition $$(i, i+k)$$ with $$k \ge 2$$, we have

$$(i,i+k) = (i+k,i+k-1)(i,i+k-1)(i+k,i+k-1),$$

> 遞迴的感覺。

which implies that every transposition is a product of adjacent transpositions.

Now for each cycle $$(a_1,a_2,\cdots,a_n)$$ we have

$$(a_1,a_2,\cdots,a_n) = (a_1,a_n)(a_1,a_{n-1})\cdots(a_1,a_2).$$

Since every cycle is also a product of adjacent transpositions, every permutation can be written as a product of adjacent transpositions.

**e.g.**

$$(3,4,1,7) = (3,7)(3,1)(3,4)$$

### Note

$$(i, i+k)$$ 是 $$2k-1$$ 個 adjacent trans. 的乘積，所以對於同一 permutation，transposition 和 adjacent trans. 個數的奇偶性相同。

而長度為 $$n$$ 的 cycle $$$$(a_1,a_2,\cdots,a_n)$$，是 $$n-1$$ 個 trans. 的乘積，所以奇偶性 ? ... cont.

---

## Inversions

Given a permutation $$\sigma \in S_n$$, let 

$$C(\sigma) = \#\{(i, j) \vert 1 \le i < j \le n, \sigma(i) > \sigma(j)\},$$

called *the number of inversions* of $$\sigma$$. When $$C(\sigma)$$ is even/odd, $$\sigma$$ is called an **even/odd permutation**.

### Theorem (# of inversions)

> For an adjacent transposition $$\tau$$ and a permutation $$\sigma \in S_n$$, we have

$$
C(\tau \sigma) = C(\sigma) \pm 1.
$$

Especially, we have 

$$
(-1)^{C(\tau \sigma)} = (-1)^{C(\sigma)+1} = (-1)^{C(\tau)}(-1)^{C(\sigma)},
$$

since $$C(\tau) = 1$$.
 
### Corollary (even permutation)
> Given a permutation in $$S_n$$, the following are equivalent.
> 1. The permutation is **even**.
> 2. The permutation is a product of **even** numbers of *adjacent transpositions*.
> 3. The permutation is a product of **even** numbers of *transpositions*.