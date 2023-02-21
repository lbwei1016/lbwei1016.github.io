---
layout: page
title: Groups of Permutation
usemathjax: true
tag: Abstract Algebra, Group Theory
time: 2022/10/12
---

**Table of Content**
- [Theorem (permutation group)](#theorem-permutation-group)
- [Cycle Notations](#cycle-notations)
  - [Cyclic Permutation](#cyclic-permutation)
  - [Theorem (cycle notation)](#theorem-cycle-notation)
    - [Corollary (order)](#corollary-order)
- [Transposition](#transposition)
  - [Definition (transposition)](#definition-transposition)
  - [Theorem (product)](#theorem-product)
    - [Proof](#proof)
  - [Theorem (generator)](#theorem-generator)
- [Inversions](#inversions)
  - [Theorem (# of inversions)](#theorem--of-inversions)
  - [Corollary (even permutation)](#corollary-even-permutation)
  - [Sign Representation](#sign-representation)
- [Alternating Groups](#alternating-groups)
  - [Theorem (even permutation forms a subgroup)](#theorem-even-permutation-forms-a-subgroup)
  - [Proof](#proof-1)
  - [Definition (alternating groups)](#definition-alternating-groups)
- [Conjugate and Commute](#conjugate-and-commute)
  - [**Lemma (conjugate)**](#lemma-conjugate)
  - [Theorem (subgroup; elements that commute)](#theorem-subgroup-elements-that-commute)
  - [Remark](#remark)
  - [Example](#example)
- [Reference](#reference)

---

> 參 [More on Groups](../5-More-on-Groups/#the-nature-of-groups)。

## Theorem (permutation group)
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
> If a permutation can be written as a product of disjoint cycles of length $$d_1, \cdots, d_k$$ . Then its order is equal to $$\text{lcm}(d_1, \cdots, d_k)$$.

> $$\sigma$$ is of order $$n$$: $$\sigma^n = e$$.

> 想想 [cyclic groups](../8-Cyclic-Subgroups/#definition-order)。

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

### Theorem (generator)

$$
\begin{align*}
S_n &= \Big\langle (i,j) \vert 1 \le i \le j \le n \Big\rangle \\  
&= \Big\langle (i,i+1) \vert 1 \le i < n \Big\rangle \\ 
&= \Big\langle (1,j) \vert 1 \le i < n \Big\rangle \\ 
&= \Big\langle (1,2)(1,2,\cdots,n) \Big\rangle \\
\end{align*}  
$$

> [集合表示法見此](../B-n-gons/#dihedral-group)。

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

---

## Conjugate and Commute
### **Lemma (conjugate)**
> Let $$\sigma$$ and $$\tau$$ be two elements in $$S_n$$. Suppose that $$\sigma = (a_1, a_2 \cdots, a_k)(b_1, b_2\cdots,b_l)\cdots$$. Then the conjugate of $$\sigma$$ by $$\tau$$ is
>
> $$
> \tau\sigma\tau^{-1} = (\tau(a_1), \tau(a_2) \cdots, \tau(a_k))(\tau(b_1), \tau(b_2)\cdots,\tau(b_l))\cdots .
> $$

**[Proof (MIT math)](https://math.mit.edu/~mckernan/Teaching/12-13/Spring/18.703/l_6.pdf)** 


### Theorem (subgroup; elements that commute)
> Let $$\pi \in S_n$$. Then **all the elements in $$S_n$$ that commute with $$\pi$$ form a subgroup**, and we denote it by $$H_\pi$$ here. In particular, we have $$\langle \pi \rangle \leq H_\pi$$.

**Proof**

Suppose $$\sigma, \tau \in H_\pi$$.

1. $$(\sigma\tau)\pi = \sigma(\tau\pi) = \sigma(\pi\tau) = \pi(\sigma\tau)$$.
2. $$e\pi = \pi e$$.
3. $$\pi\tau = \tau\pi \implies \tau^{-1}\pi = \pi\tau^{-1}$$. ◼

### Remark

兩元素可交換，相當於用對方對自己共軛之後，和自己相等！也就是：$$\sigma\pi\sigma^{-1} = \pi$$。於是，我們可以用[上述的引理](#lemma-conjugate)！

### Example

Let $$G = S_4$$ and $$X = \{(1234),(1243),\cdots \}$$ be that set of cycls of length $$4$$. Let $$G$$ acts on $$X$$ by conjugation. Determine if the action of $$G$$ is faithful.

**Solution**

Since all $$x\in X$$ are four cycles, we take $$\sigma_0=(1234)$$ for demonstration. 

Suppose that $$G$$ is not faithful, i.e., there exists $$\pi \in G$$, $$\pi \not = e$$ such that $$\pi\sigma\pi^{-1} = \sigma$$ for all $$\sigma\in X$$. By this [lemma](#lemms-conjugate), we have 

$$
\pi\sigma_0\pi^{-1} = (\pi(1), \pi(2), \pi(3), \pi(4)) = (1, 2, 3, 4) = \sigma_0.
$$

We can see that $$\pi$$ must be a $$4$$-cycle or consist of two $$2$$-cycles. Now, let's try to find the subgroup that contains all the elements that commutes with $$\sigma_0$$. First, we have

$$
\langle \sigma_0 \rangle = \{e, (1234),(13)(24), (4321) \}.
$$

It can be verified that the remaining elements of $$X$$, $$(12)(34)$$, and $$(14)(23)$$ do not commute with $$\sigma_0$$. Thus, $$H_{\sigma_0} = \langle \sigma_0 \rangle$$. By symmetry, we can deduce that $$H_{\sigma_1} = \langle \sigma_1 \rangle$$ and $$H_{\sigma_2} = \langle \sigma_2 \rangle$$, for $$\sigma_1, \sigma_2\in X$$. However, $$\pi \in H_{\sigma_0} \cup H_{\sigma_1} \cup H_{\sigma_2}$$ = $$\{e\}$$, which is a contradiction. Therefore, $$G$$ is faithful. ◼

---

## Reference

- [MIT math](https://math.mit.edu/~mckernan/Teaching/12-13/Spring/18.703/l_6.pdf)
- [Quora](https://www.quora.com/How-do-I-find-all-permutations-that-commute-with-the-permutation-1-3-4-2-5)