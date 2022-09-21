---
layout: page
title: Introduction
usemathjax: true
tag: Basics
time: 2022/09/15
---

**Table of Content**

---

## Axioms

1. **Nonnegativity**: $$P(A) \geq 0$$.
2. **Normalization**: $$P(\Omega) = 1$$.
3. **Finite additivity**: If $$A \cup B = \emptyset$$, then $$P(A \cup B) = P(A) + P(B)$$.

第三點可以用更強的 **Countable additivity axiom** 取代，如下：

>If $$A_1, A_2, \cdots$$ is an infinite sequence of **disjoint** events, then
>
$$P(A_1 \cup A_2 \cup \cdots) = P(A_1) + P(A_2) + \cdots.$$

> $$\{A_i\}$$ must be countable.

但是為什麼需要 **Countable additivity axiom**？原本的不夠用嗎？首先令 $$S_n = C_1 \cup \cdots \cup C_n$$。考慮極限情況下，

原本的 axiom:

$$\lim_{n \to \infty}P(S_n) = \lim_{n \to \infty}\sum^n_{k=1}P(C_k) \tag{1}$$

強化版 axiom:

$$P(\lim_{n \to \infty}S_n) = \lim_{n \to \infty}\sum^n_{k=1}P(C_k) \tag{2}$$

$$(1)$$ 的左式，是對「函數」（probabilty set function: $$P(C_k)$$） 取極限，而 $$(2)$$ 的左式則是對「事件的聯集」取極限；除非 $$P(C_k)$$ 是連續函數，否則 $$\lim$$ 沒辦法任意移動，兩者也就不一定相等。也就是說，使用 **Finite additivity axiom** 無法表示 *infinite sequence of events* 的機率，因為對 $$P$$ 取極限基本上沒有幫助。於是只好引入 **Countable additivity axiom**。

---

## Some identities

### Multiplication Rule (Chain Rule)

> 基於 *conditional probability*，就是 $$(1)$$。

$$P(B | A) = P(B \cap A) / P(A) \tag{1}$$

$$P(\bigcap^n_{i=1}A_i) = \prod^n_{i=1} P(A_i | \bigcap^{i-1}_{j=1}A_j) \tag{2}$$

> 定義 $$\bigcap^0_{j=1}A_j = \Omega$$。

$$P(A_1 \cap A_2 \cap A_3) = P(A_1)P(A_2|A_1)P(A_3|A_1 \cap A_2) \tag{3}$$

> $$(3)$$ 是 $$(2)$$ 的展開。

### Sum 

$$P(B) = \sum_i P(A_i)P(B|A_i) \tag{4}$$

> $$\{A_i\}$$ 是樣本空間的一個 partition。

### Bayes' Rule

$$P(A_i|B) = {P(A_i \cap B) \over P(B)} = {P(A_i)P(B | A_i) \over \sum_i P(A_i)P(B|A_i)} $$

這個規則可以**反轉** $$A_i$$ 和 $$B$$ 在 conditional probability 的角色，也就是 

$$P(A_i|B) \leftrightarrow P(B|A_i)$$

看何者已知，就能求出另一機率。

---

## Independence




