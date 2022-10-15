---
layout: page
title: Conditioning
usemathjax: true
tag: Conditional Probability
time: 2022/10/05
---

**Table of Content**
- [Conditioning a Random Variable on an Event](#conditioning-a-random-variable-on-an-event)
- [Conditioning one Random Variable on Another](#conditioning-one-random-variable-on-another)
- [Reference](#reference)

---

## Conditioning a Random Variable on an Event 

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

$$p_X(x) = \sum_i P(A_i)p_{X|A_i}(x),$$

and this is called the **total probability theorem**.

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

## Conditioning one Random Variable on Another

Define

$$p_{X\vert Y}(x \vert y) = {p_{X,Y}(x,y) \over p_Y(y)},$$

i.e.

$$p_{X,Y}(x,y) = p_X(x)p_{Y \vert X}(y \vert x) = p_Y(y)p_{X \vert Y}(x \vert y).$$

Moreover,

$$
E[X \vert Y = y] = \sum_x xp_{X \vert Y}(x \vert y), \\
E[X] = \sum_yp_Y(y)E[X \vert Y=y].
$$

For **linearity**, we have

$$
E[(X+Y) \vert Z] = E[X \vert Z] + E[Y \vert Z].
$$

For variance, we have

$$
var(X \vert Y) = E[(X-E[X \vert Y])^2 \vert Y] = E[X^2 \vert Y] - (E[X \vert Y])^2.
$$

> 展開整理就可證明。

---

## Reference
- Introduction to Probability, 2/e, by Dimitri P. Bertsekas, John N. Tsitsiklis