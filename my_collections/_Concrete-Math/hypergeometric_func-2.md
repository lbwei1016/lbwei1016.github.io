---
layout: page
title: Hypergeometric Functions II
usemathjax: true
tag: Concrete Mathematics, Hypergeometric
time: 2022/09/01
---

**Table of Content**
- [Hypergeometric Transformation](#hypergeometric-transformation)
  - [Reflection Law](#reflection-law)
  - [Differentiation](#differentiation)
    - [Example $$\rm I$$](#example-rm-i)
  - [More on Differential Operators](#more-on-differential-operators)
- [Partial Hypergeometric Sums](#partial-hypergeometric-sums)

---

## Hypergeometric Transformation

### Reflection Law

$${1 \over (1-z)^a}F(a, b; c; {-z \over 1-z}) = F(a, c-b; c; z)$$

> $$a, b$$ 的角色可以互換（想當然爾）

### Differentiation

$${d \over dz}F(a_1, \cdots, a_m; b_1, \cdots, b_n; z) \\ = {a_1 \cdots a_m \over b_1 \cdots b_n}F(a_1+1, \cdots, a_m+1; b_1+1, \cdots, b_n+1; z) \tag{1}$$

> Define operator $$D = {d \over dz},\ \vartheta = zD$$

$$\vartheta F(a_1, \cdots, a_m; b_1, \cdots, b_n; z) = \sum_{k \geq 0} k{a_1^{\bar k}, \cdots a_m^{\bar k} \over b_1^{\bar k}, \cdots b_n^{\bar k}} {z^k \over k!} \tag{2}$$

底下比較有用：

$$(\vartheta + a_1)F(a_1, \cdots, a_m; b_1, \cdots, b_n; z) \\ = a_1F(a_1+1, \cdots, a_m; b_1, \cdots, b_n; z) \tag{3}$$

$$(\vartheta + b_1 - 1)F(a_1, \cdots, a_m; b_1, \cdots, b_n; z) \\ = (b_1 - 1)F(a_1, \cdots, a_m; b_1-1, \cdots, b_n; z) \tag{4}$$

綜合 $$(1), (3), (4)$$，

$$D(\vartheta + b_1 - 1)\cdots(\vartheta + b_n - 1)F = (\vartheta + a_1)\cdots(\vartheta + a_m)F \tag{5}$$

然後兩邊都乘上 $$z$$

$${\vartheta}(\vartheta + b_1 - 1)\cdots(\vartheta + b_n - 1)F = z(\vartheta + a_1)\cdots(\vartheta + a_m)F \tag{6}$$

> 第一個 $$\vartheta$$ 可以想成 $$(\vartheta + 1 - 1)$$，對應 [term ratio](../hypergeometric_func-1/#term-ratio) 中分母的 $$(k+1)$$；其餘依樣對應（互相記憶的好方法！）

這個微分方程可以將解表示為 *hypergeometric function*。

#### Example $$\rm I$$

若

$$\vartheta G = z(\vartheta+1)^2G$$

則

$$G = F(1,1;;z) \tag*{$\blacksquare$}$$

或是用來驗證兩 identity 是否相同（是否符合同一微分方程）。

> *"Every new identity for hypergeometrics has consequences for binomial
coefficients."* [CMath] p.222

> 但要注意[退化](../hypergeometric_func-1/#degenerate)

### More on Differential Operators

$$\vartheta^n = \sum_k\begin{Bmatrix}n \\ k\end{Bmatrix}z^kD^k$$

$$z^nD^n = \sum_k\begin{bmatrix}n \\ k\end{bmatrix}(-1)^{n-k}\vartheta^k$$

> $$\vartheta$$ 和 $$D$$ 互相轉換

---

## Partial Hypergeometric Sums
[待續] p.237

