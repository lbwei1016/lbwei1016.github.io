---
layout: page
title: Solving Recurrences II
usemathjax: true
tag: Concrete Mathematics, Recurrence
time: 2022/09/06
---

> *Solve* 指的是解出 *closed form*。<br>
> 本系列討論僅止於 *linear recurrences*。

> *The point of a closed form is not necessarily to provide us with a fast method of calculation, but rather to tell us how $$F_n$$ relates to other quantities in mathematics.* -- [CMath]

**Table of Content**
- [Summation Factor](#summation-factor)
  - [Procedure](#procedure)
  - [Reference](#reference)

---

> **First-Order Recurrences** <br>
> 形式：$$a_n = Ca_{n-1} + f(n)$$ <br>
> 若 $$f(n) = 0$$，則稱為 *homogeneous*。

## Summation Factor

> 出自 [CMath]

Sum 和 recurrence 的關係相當密切，因為

$$S_n = \sum_{k=0}^n a_k$$

等價於

$$\begin{eqnarray}
S_0 &=& a_0\ ; \\
S_n &=& S_{n-1} + a_n,\ n > 0。
\end{eqnarray}$$

於是遞迴形如

$$a_nT_n = b_nT_{n-1} + c_n$$

可以利用 *Sum* 的想法來解。

### Procedure

首先等號左右都乘上 $$s_n$$，使得

$$s_nb_n = s_{n-1}a_{n-1} \tag{1}$$

再令

$$S_n = s_na_nT_n； \tag{2}$$

於是

$$s_na_nT_n = s_nb_nT_{n-1} + s_nc_n \tag{3}$$

就變成

$$S_n = S_{n-1} + s_nc_n。 \tag{4}$$

因此

$$S_n = s_0a_0T_0 + \sum_{k=1}^ns_kc_k  = s_1b_1T_0 + \sum_{k=1}^ns_kc_k， \tag{5}$$

> 這裡的 sum 應該要能輕鬆解出

而原遞迴式的解則是

$$T_n = {S_n \over s_na_n}。 \tag{6}$$

如何求出關鍵的 $$s_n$$？利用 $$(1)$$：$$s_n = s_{n-1}a_{n-1} / b_n$$，則

$$s_n = k{a_{n-1}a_{n-2} \cdots a_1 \over b_nb_{n-1} \cdots b_2}，$$

其中 $$k$$ 可以是任意非零常數！

> Note: $$a_i, b_i$$ 必須全部都非零！

---

### Reference
- [CMath] (p.27), Concrete Mathematics: A Foundation for Computer Science, by Ronald Graham, Donald Knuth, and Oren Patashni