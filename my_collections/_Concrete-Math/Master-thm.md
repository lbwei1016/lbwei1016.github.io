---
layout: page
title: Master Theorem
usemathjax: true
tag: Concrete Mathematics, Recurrence
time: 2022/08/23
---

$$\begin{eqnarray} 
T(n) &=& aT(n/b) + O(n^d) \\ &=&
\begin{cases}
O(n^d),\ d > \log_b a \\
O(n^d \log n),\ d = \log_b a \\
O(n^{\log_b a}),\ d < \log_b a \\
\end{cases}
\end{eqnarray}
$$