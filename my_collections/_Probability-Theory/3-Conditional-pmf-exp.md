---
layout: page
title: Conditional PMF & Expectation
usemathjax: true
tag: PMF
time: 2022/10/05
---

**Table of Content**

---

## Overview

$$\begin{align*}
p_{X|A}(x) &= P(X=x|A), \tag{1} \\
\sum_x p_{X|A}(x) &= 1, \tag{2} \\
E[X|A] &= \sum_x xp_{X|A}(x), \tag{3} \\
E[g(X)|A] &= \sum_x g(x)p_{X|A}(x), \tag{4} \\
\end{align*}$$

> 只是加上 condition，其他一切照舊。

Given $$\{A_i\}$$ is a partition of the sample space.

In conditional probability, we have

$$P(B) = \sum_i P(A_i)P(B|A_i).$$

Here in **conditional pmf**, we have

$$p_X(x) = \sum_i P(A_i)p_{X|A_i}(x).$$

> 想像 $$B = \{X=x\}$$.

Moreover, if we multiply both sides with $$x$$ and sum over it, we get

$$\begin{align*}
E[X]=\sum_x xp_X(x) &= \sum_x x\sum_i P(A_i)p_{X|A_i}(x) \\
&= \sum_i \sum_x xP(A_i)p_{X|A_i}(x) \\
&= \sum_i P(A_i)\sum_x xp_{X|A_i}(x) \\
&= \sum_i P(A_i)E[X|A_i].
\end{align*}
$$

This is called the **total expectation theorem**.

> 將樣本空間拆成數個好計算的 disjoint event spaces，個別計算期望值後再依權重（該 event space 的機率）取和。

---

## Conditioning a Geometric Random Variable

---

