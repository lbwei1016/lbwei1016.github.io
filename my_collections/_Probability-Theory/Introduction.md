---
layout: page
title: Introduction
usemathjax: true
tag: Basics
time: 2022/09/22
---

**Table of Content**
- [Axioms](#axioms)
- [Some identities](#some-identities)
  - [Multiplication Rule (Chain Rule)](#multiplication-rule-chain-rule)
  - [Sum](#sum)
  - [Bayes' Rule](#bayes-rule)
- [Independence](#independence)
  - [Definition](#definition)
  - [Facts](#facts)
- [Conditional Independence](#conditional-independence)
  - [Definition](#definition-1)
  - [Problem](#problem)

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

> 這裡定義 $$\bigcap^0_{j=1}A_j = \Omega$$。

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

### Definition

> Events $$A$$ and $$B$$ are **independent** if $$P(A \cap B) = P(A)P(B).$$

事件的獨立與否與其代表的集合之間的關係無關（如交集、聯集的情形）；獨立與否由**指派給事件的機率決定**，也就是說，只要滿足定義，就是獨立。

例如，兩事件**互斥**經常被拿來與獨立比較（說他們不獨立），但考慮以下情況：

$$A \cap B = \emptyset,\ P(A) = 0$$

則定義是被滿足的！（$$P(\emptyset) = 0$$）

從本例可以看出，關鍵在於如何指派 $$P(A), P(B)$$。

### Facts

若 $$A, B$$ 獨立，則，$$\{A, A^c\} \times \{B, B^c\}$$ 中任一對事件皆獨立。

**Proof**（舉其中一例）

因為

$$A = (A \cap B) \cup (A \cap B^c)$$

則

$$P(A) = P(A)P(B) + P(A \cap B^c)$$

於是

$$P(A \cap B^c) = P(A)(1 - P(B)) = P(A)P(B^c) \tag*{$\blacksquare$}$$

--- 

## Conditional Independence

### Definition

> Let $$A, B, C$$ be events. $$A$$ and $$B$$ are said to be **conditionally independent** given $$C$$ if only if $$P(C) > 0$$ and
>
>$$P(A \cap B | C) = P(A | C)P(B | C).$$

> $$A, B$$ 獨立，不代表他們在 $$C$$ 發生下也獨立；一切取決於指派的機率。

### Problem

Given two unfair coins, $$A$$ and $$B$$: 

$$P(H | A) = 0.9, P(H | B) = 0.1$$

> $$H$$ 代表 head。

We choose either coin with equal probability, and ask

$$P($$ toss $$11 = H$$ \| first $$10$$ tosses are heads $$)$$, 

which can be denoted by

$$P(H_{11} | H_{1-10}).$$

**Solution**

直覺上，由於前十次都要是 head，對於機率只有 $$(0.1)^{10}$$ 的 $$B$$ 來說非常困難，因此可以猜測

$$P(H_{11} | H_{1-10}) \approx P(H|A)。$$

實際計算之前，先嘗試化簡

$$\begin{eqnarray} 
P(H_{11} | H_{1-10}) &=& {P(H_{11} \cap A \cap H_{1-10}) + P(H_{11} \cap B \cap H_{1-10}) \over P(H_{1-10})} \\
&=& {P(H_{11}|A \cap H_{1-10})P(A \cap H_{1-10}) \over P(H_{1-10})} + P_B \\
&=& P(H_{11}|A \cap H_{1-10})P(A|H_{1-10}) + P_B \\
\end{eqnarray}$$

> $$P_B$$ 和加號左方是相似的，僅 $$A$$ 變成 $$B$$；此為方便只展開 $$A$$。

我們知道，選好硬幣之後，任兩次硬幣投擲間都互相獨立，而且不管哪一次投擲獲得 head 的都機率一樣；也就是說，$$H_{1-10}$$ 的發生與否對 $$H_{11}$$ 而言毫無影響，而且 $$P(H_{11}$$ \| $$A)= P(H$$ \| $$A)$$。於是

$$P(H_{11}|A \cap H_{1-10}) = P(H_{11}|A) = P(H|A)$$

這是已知！統整一下：

$$P(H_{11} | H_{1-10}) = P(H|A)P(A|H_{1-10}) + P(H|B)P(B|H_{1-10})。$$

> 其實不化簡，直接算也不麻煩，但是化簡的過程與結果提供了不同的觀點。

於是我們發現，「在已經投十次 head 的情況下，再投出一次 head 的機率」可以簡潔地以 $$A$$ 和 $$B$$ 個別的觀點表達。