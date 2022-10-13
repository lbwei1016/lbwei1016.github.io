---
layout: page
title: Transposition
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/10/12
---

**Table of Content**
- [Transposition](#transposition)
  - [Definition (transposition)](#definition-transposition)
  - [Theorem (product)](#theorem-product)
    - [Proof](#proof)
- [Inversions](#inversions)
  - [Theorem (# of inversions)](#theorem--of-inversions)
  - [Corollary (even permutation)](#corollary-even-permutation)
  - [Sign Representation](#sign-representation)
- [Alternating Groups](#alternating-groups)
  - [Theorem (even permutation forms a subgroup)](#theorem-even-permutation-forms-a-subgroup)
  - [Proof](#proof-1)
  - [Definition (alternating groups)](#definition-alternating-groups)

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

**Note:**

$$(i, i+k)$$ 是 $$2k-1$$ 個 adjacent trans. 的乘積，所以對於同一 permutation，transposition 和 adjacent trans. 個數的奇偶性相同。

而長度為 $$n$$ 的 cycle $$(a_1,a_2,\cdots,a_n)$$，是 $$n-1$$ 個 trans. 的乘積，所以 *A permutation $$\sigma$$ of length $$n$$ is even iff $$n$$ is odd.*。

### Sign Representation

Let $$\text{sgn}: S_n \to \{\pm 1\}$$, given by $$\text{sgn}(\sigma)=(-1)^{C(\sigma)}$$. Then $$\text{sgn}$$ is a group homomorphism.

> 也就是說，permutation 的奇偶性被保留下來了。

---

## Alternating Groups

### Theorem (even permutation forms a subgroup)
> If $$n \ge 2$$, then the set $$A_n$$ of all **even permutations** of $$\{1,2,\cdots,n\}$$ forms a **subgroup** of order **$$n!/2$$** of $$S_n$$.

### Proof

First we prove that $$A_n$$ is a subgroup.

- closedness

If $$\sigma_1$$ and $$\sigma_2$$ are both products of an even number of transpositions, so is $$\sigma_1\sigma_2$$.

- identity

$$e = (1,2)(1,2)$$, which is even.

- inverse

If $$\sigma = \tau_1 \cdots \tau_{2n}$$ is a product of an even number of transpositions, then $$\sigma^{-1} = \tau_{2n}^{-1}\cdots\tau_1^{-1} $$ is also even.

We now prove that $$\vert A_n \vert = n!/2$$. It suffices to prove that the number of even permutations in $$S_n$$ is equal to the number of odd permutations in $$S_n$$.

Let $$B_n$$ be the set of all odd permutations in $$S_n$$. (Note that $$B_n$$ is **not a subgroup** since it is **not closed** under multiplication.) Define $$\lambda: A_n \to B_n$$ by $$\lambda(\sigma) = (1,2)\sigma$$. We claim that $$\lambda$$ is one-to-one and onto, which implies $$\vert A_n \vert = \vert B_n \vert  = \vert S_n \vert/2 = n!/2$$.

- one-to-one

If $$(1,2)\sigma_1 = (1,2)\sigma_2$$, by cancellation law, we have $$\sigma_1 = \sigma_2$$. Thus $$\lambda$$ is one-to-one.

- onto

If $$\sigma \in B_n$$ is an odd permutation, then $$(1,2)\sigma$$ is even and we have $$\lambda((1,2)\sigma) = (1,2)(1,2)\sigma = \sigma$$. Thus, $$\lambda$$ is onto. ◼

### Definition (alternating groups)
> The subgroup of $$S_n$$ consisting of the **even permutations** of $$n$$ letters is the **alternating group $$A_n$$** on $$n$$ letters.