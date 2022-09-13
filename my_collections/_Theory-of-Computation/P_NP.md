---
layout: page
title: Computational Complexity
usemathjax: true
tag: Theory of Computation
---

### Classification Problems
又稱為 **decision problems**。此類問題的答案是 *Yes or No*；例如「x 是不是質數？」
而 **decision procedure** 指的就是 **algorithm**。

其他問題分類有：Optimization problems, Quantified problems, etc.

> ***Turing machine*** in modern language, is simply a computer program. (Math and Computation, Avi Wigderson)

---

### $$\mathcal{P}$$ v.s. $$\mathcal{NP}$$
簡單來說，若某類問題 $$\mathcal{C \in P}$$，代表 $$\mathcal{C}$$ 可以「有效率地」（即在多項式時間內）被解決；若 $$\mathcal{C \in NP}$$，則問題 $$\mathcal{C}$$ 可以「有效率地」被驗證（存在 *witness* $$y$$）。

---

### $$\mathcal{coNP}$$
若 $$\mathcal{C \in NP}$$，則 $$\mathcal{\bar{C} \in coNP}$$。（$$\mathcal{\bar{C}}$$ 是 $$\mathcal{C}$$ 的補集）

---

### $$Reduction$$
存在兩問題 $$\mathcal{C, D}$$，若 $$\mathcal{C}$$ 可以經由 $$f \in \mathcal{P}$$（有效率）轉換為 $$\mathcal{D}$$，則 $$\mathcal{C \leq D}$$。此過程稱為 $$reduction$$。

### $$\mathcal{NP}$$-hard & $$\mathcal{NP}$$-complete
對於所有問題 $$\mathcal{C \in NP}$$，如果 $$\mathcal{C \leq D}$$ 都成立，則 $$\mathcal{D}$$ 被稱為 $$\mathcal{NP}$$-hard；若 $$\mathcal{D}$$ 也屬於 $$\mathcal{NP}$$，則 $$\mathcal{D}$$ 為 $$\mathcal{NP}$$-complete。

> $$SAT$$ 問題為 $$\mathcal{NP}$$-complete。

