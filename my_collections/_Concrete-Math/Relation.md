---
layout: page
title: Relation
usemathjax: true
tag: Concrete Mathematics, Relation
time: 2022/08/19
---

**Table of Content**
- [Basics](#basics)
  - [Definition $$\rm I$$ (binary relation)](#definition-rm-i-binary-relation)
  - [Definition $$\rm II$$ (on a set)](#definition-rm-ii-on-a-set)
  - [Definition $$\rm III$$ (reflexive)](#definition-rm-iii-reflexive)
  - [Definition $$\rm III$$ (symmetric)](#definition-rm-iii-symmetric)
  - [Definition $$\rm IV$$ (transitive)](#definition-rm-iv-transitive)
  - [Definition $$\rm V$$ (composition)](#definition-rm-v-composition)
  - [Definition $$\rm VI$$ (power)](#definition-rm-vi-power)
- [Some Relations](#some-relations)
  - [Equivalence Relation](#equivalence-relation)
- [Partial Orderings](#partial-orderings)
  - [Definition $$\rm I$$ (partial ordering)](#definition-rm-i-partial-ordering)
  - [Definition $$\rm II$$ (compare)](#definition-rm-ii-compare)
  - [Definition $$\rm III$$ (total ordering)](#definition-rm-iii-total-ordering)
  - [Definition $$\rm IV$$ (well-ordered)](#definition-rm-iv-well-ordered)
  - [Theorem (induction)](#theorem-induction)
    - [**The Principle of Well-Ordered Induction**](#the-principle-of-well-ordered-induction)
- [Some Definitions on Sets](#some-definitions-on-sets)
  - [Partition and Cell](#partition-and-cell)
  - [Disjoint Union](#disjoint-union)
- [Reference](#reference)
- [See also](#see-also)

---

## Basics

### Definition $$\rm I$$ (binary relation)
> Let $$A$$ and $$B$$ be sets. A *binary relation from $$A$$ to $$B$$* is a subset of $$A \times B$$.

**Relation**，是數個集合的成員之間的關係，類似 **Function**，但沒有不能一對多的限制。**Reation** 本身也是一集合 $$R$$；如果 $$(a, b) \in R$$，寫做 $$a\ R\ b$$，讀做 $$a$$ is related to $$b$$ by $$R$$。

> **Fuction** 事實上是 **Relation** 的特例。

### Definition $$\rm II$$ (on a set)
> *A relation on a set $$A$$* is a relation from $$A$$ to $$A$$。

### Definition $$\rm III$$ (reflexive)
> A relation $$R$$ on a set $$A$$ is called *reflexive* if $$(a, a) \in R$$, $$\forall a \in A$$.

### Definition $$\rm III$$ (symmetric)
> **symmetric**: $$(a, b) \in R$$ 和 $$(b, a) \in R$$ 同時成立，$$\forall a, b \in A$$ <br>
> **antisymmetric**: 如果 $$(a, b) \in R$$ 和 $$(b, a) \in R$$，則 $$a = b$$ <br>
> **asymmetric**: $$(a, b) \in R$$ 和 $$(b, a) \in R$$ 不同時成立，也就是 $$(a, a) \not\in R$$

### Definition $$\rm IV$$ (transitive)
> $$R$$ on a set $$A$$ is *transitive* if $$\forall a\forall b \forall c(((a,b) \in R \land (b, c) \in R) \implies (a, c) \in R)$$.

### Definition $$\rm V$$ (composition)
> Let $$R$$ be a relation from a set $$A$$ to a set $$B$$ and $$S$$ a relation from $$B$$ to a set $$C$$. $$(a, c) \in S \circ R$$, for which $$\exists b \in B$$ such that $$(a, b) \in R$$ and $$(b, c) \in S$$. ($$a \in A, c \in C$$)

> 想想 *function*

### Definition $$\rm VI$$ (power)
> $$R^1 = R$$ and $$R^{n+1} = R^n \circ R$$.

---

## Some Relations

### Equivalence Relation

**Definition**
> An **equivalence relation** $$R$$ on a set $$S$$ is one that satisfies *reflexive, symmetric, and transitive*, $$\forall x, y, z \in S$$.

> 與底下的 **poset** 比較

**Example**

對於任意非空集合 $$S$$，$$(S, =)$$ 是 **equivalence relation**。

---

## Partial Orderings
### Definition $$\rm I$$ (partial ordering)
> A relation $$R$$ on a set $$S$$ is called a ***partial ordering*** or ***partial order*** if it is *reflexive, antisymmetric, and transitive*. And $$(S, R)$$ is called a ***partially ordered set***, or ***poset***. Members of $$S$$ are called *elements* of the poset.

**Example:** $$(\mathbb{Z}, \geq)$$ is a *poset*
> 證明 $$\geq$$ 在 $$\mathbb{Z}$$ 上是 *reflexive, antisymmetric, and transitive*。

### Definition $$\rm II$$ (compare)
>The elements $$a$$ and $$b$$ of a poset $$(S, \preceq)$$ are called ***comparable*** if either $$a \preceq b$$ of $$b \preceq a$$. Otherwise, $$a$$ and $$b$$ are called ***incomparable***.

**Example:** In the poset $$(\mathbb{Z}^{+}, \mid)$$, $$5$$ and $$7$$ are **incomparable**.

> *Note $$\rm I$$:* $$\preceq$$ is used to denote the relation in *any* poset. <br>
> *Note $$\rm II$$:* $$a \prec b$$ 讀做 "$$a$$ precedes $$b$$" 或 "$$a$$ is less than $$b$$"


### Definition $$\rm III$$ (total ordering)
> 若 $$(S, \preceq)$$ 是 poset 且 $$S$$ 的任兩元素皆 *comparable*，則 $$S$$ 稱為 ***totally ordered set*** 或 ***linearly ordered set***，而 $$\preceq$$ 稱為 a ***total order*** 或 a ***linear order***。

### Definition $$\rm IV$$ (well-ordered)
> $$(S, \preceq)$$ is a ***well-ordered set*** if it is a poset such that $$\preceq$$ is a *total ordering* and every nonempty subset of $$S$$ has a ***least element***.

**Example:** $$(\mathbb{Z}^{+}, \leq)$$ is well-ordered, while $$(\mathbb{Z}, \leq)$$ is not.

### Theorem (induction)
#### **The Principle of Well-Ordered Induction**
> Suppose that $$S$$ is a well-ordered set. Then $$P(x)$$ is true for all $$x \in S$$, if <br>
> ***Inductive Step***: For every $$y \in S$$, if $$P(x)$$ is true for all $$x \in S$$ with $$x \prec y$$, then $$P(y)$$ is true.

> 廣義的數學歸納法

**Proof**

Suppose it is not the case that $$P(x)$$ is true for all $$x \in S$$ ... (proof by contradiction).

---

## Some Definitions on Sets

### Partition and Cell
A **partition** of a set $$S$$ is a collection of nonempty subsets of $$S$$ such that every element of $$S$$ is in exactly one of the subsets. The subsets are the **cells** of the partition.

> 想想貝氏定理的分割圖（或任何分割圖）

$$\bar x$$：指包含 $$x$$ 的 cell，稱作 *the equivalence class containing* $$x$$；而 $$x$$ 叫做 *a representative of the cell*。

### Disjoint Union

設 $$\{S_1, S_2, \cdots\}$$ 是 $$S$$ 的一個 partition，則 

$$S = \bigsqcup_i S_i。$$

---

## Reference
- Discrete Mathematics and Its Applications, K. H. Rosen, 7/e (Global edition)
- A First Course in Abstract Algebra, John B. Fraleigh, Victor J. Katz, 7/e

---

## See also
- The Art of Computer Programming Vol. 1, p.20, prob. 15