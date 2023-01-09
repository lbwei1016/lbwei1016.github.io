---
layout: page
title: The Bernoulli Process
usemathjax: true
tag: Probability, Statistics
time: 2022/01/04
---

**Table of Content**
- [Stochastic Process](#stochastic-process)
- [Bernoulli Process](#bernoulli-process)
  - [Definition](#definition)
  - [Properties](#properties)
    - [Fresh start](#fresh-start)
  - [Time of the $$k$$-th arrival](#time-of-the-k-th-arrival)
  - [Merging and Splitting processes](#merging-and-splitting-processes)
    - [Merge](#merge)
    - [Split](#split)

---

## Stochastic Process

有兩種觀點來看什麼是 **stochastic process**：
1. an infinite sequence of r.v.s
2. a **set** of infinite sequences of r.v.s (sample space)

第一種觀點關注的是單一 **random variable** 的資訊，像是 $$E[X_i], p_{X_i}(x)$$ 等等；第二種觀點則關注整個序列，例如 $$P(X_i=1 \text{ for all } i)$$。

---

## Bernoulli Process
### Definition
> A **Bernoulli process** is a sequence of **independent** Bernoulli trials, $$X_i$$, where $$X_i \sim \text{Ber}(p)$$.

> Independence and time homogeneity are the assumptions.

### Properties
#### Fresh start

Let $$X_1, X_2, \cdots$$ be a Bernoulli process, and let $$N$$ be a random time. Then the process $$X_{N+1}, X_{N+2}, \cdots$$ is **also a Bernoulli process**, which is independent of $$N$$ and $$X_1, \cdots, X_N$$.

> 不管在哪重新開始都一樣！

### Time of the $$k$$-th arrival

Let $$Y_k$$ be the time of the $$k$$-th arrival, and let $$T_k$$ be the $$k$$-th inter-arrival time, where $$T_k = Y_k - Y_{k-1}$$. We can see that $$Y_k = T_1 + \cdots T_k$$, and by the [fresh start property](#fresh-start), we know that every $$T_i$$ are independent. Thus $$T_i \sim \text{Geo}(p)$$.

> 畫個圖比較好想！

Moreover, 

$$
P(Y_k = t) = {t-1\choose k-1}p^k(1-p)^{t-k}.
$$

> 在 $$t-1$$ 個 slots 中選 $$k-1$$ 個；保留一次成功給 $$t$$。

> 見 [Pascal r.v.](../2-discrete-rv/#pascal)。

### Merging and Splitting processes
#### Merge

Let $$X_1, X_2\cdots$$ and $$Y_1, Y_2, \cdots$$ be two Bernoulli processes, where $$X_i \sim \text{Ber}(p), Y_i \sim \text{Ber}(q)$$. Then the merged process $$Z_1, Z_2, \cdots$$ is **also a Bernoulli process**, where $$Z_i \sim \text{Ber}(p+q-pq)$$.

#### Split

If we split successes into two streams using independent flips of a coin with bias $$q$$, we get two **dependent** Bernoulli processes.

Why dependent? Because a success in one process guarantees the failure in the other process.

> $$\text{Ber}(p) \to \text{Ber}(pq), \text{Ber}(p(1-q)) $$.

> 假設 coin flip 和原 Bernoulli process 獨立。

> 畫個圖比較好想！