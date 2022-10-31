---
layout: page
title: Master Theorem
usemathjax: true
tag: Concrete Mathematics, Recurrence
time: 2022/08/23
---

**Table of Content**
- [Theorem (Master Theorem)](#theorem-master-theorem)
- [簡化版](#簡化版)

---

## Theorem (Master Theorem)

Let $$a\ge 1$$ and $$b > 1$$ be constants, and let $$T(n)$$ be defined as

$$
T(n) = aT(n/b) + f(n),
$$

where we interpret $$n/b$$ to mean either $$\lfloor n/b \rfloor$$ or $$\lceil n/b \rceil$$. Then $$T(n)$$ has the following asymptotic bounds:

1. If $$f(n) = O(n^{\log_ba - \epsilon})$$ for some constant $$\epsilon > 0$$, then $$T(n) = \Theta(n^{\log_ba})$$.
2. If $$f(n) = \Theta(n^{\log_ba})$$, then $$T(n) = \Theta(n^{\log_ba}\lg n)$$.
3. If $$f(n) = \Omega(n^{\log_ba+\epsilon}) $$ for some constant $$\epsilon > 0$$, and if $$af(n/b) \le cf(n)$$ for some constant $$c < 1$$ and all sufficiently large $$n$$, then $$T(n) = \Theta(f(n))$$.

注意，$$f(n)$$ 必須 **polynomially** larger or smaller than $$n^{\log_b a}$$（要差 $$n^\epsilon$$），否則 **master theorem** 無法使用；$$3.$$ 有額外的限制也要小心。

---

## 簡化版

$$\begin{eqnarray} 
T(n) &=& aT(n/b) + O(n^d) \\ &=&
\begin{cases}
O(n^d),\ d > \log_b a \\
O(n^d \log n),\ d = \log_b a \\
O(n^{\log_b a}),\ d < \log_b a \\
\end{cases}
\end{eqnarray}
$$

---