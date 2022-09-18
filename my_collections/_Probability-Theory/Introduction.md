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

第三點可以用更強的 **Countable 

> 以下未整理

令 $$S_n = C_1 \cup \cdots \cup C_n$$。

原本的 axiom:

$$\lim_{n \to \infty}P(S_n) = \lim_{n \to \infty}\sum^n_{k=1}P(C_k) \tag{1}$$

強化版 axiom:

$$P(\lim_{n \to \infty}S_n) = \lim_{n \to \infty}\sum^n_{k=1}P(C_k) \tag{2}$$

我對 $$(1)$$ 的解讀是，把 $$P(C_k)$$ 看作集合的函數，所以左式是對「函數」取極限；而 $$(2)$$ 的左式則是對「集合的聯集」取極限。除非 $$P(C_k)$$ 是連續函數，否則 $$\lim$$ 沒辦法任意移動，兩者也就不一定相等。
