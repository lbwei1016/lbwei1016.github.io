---
layout: page
title: Hypergeometric Functions II
usemathjax: true
tag: Concrete Mathematics, Hypergeometric
time: 2022/09/01
---

**Table of Content**

---

## Hypergeometric Transformation

### Reflection Law

$${1 \over (1-z)^a}F(a, b; c; {-z \over 1-z}) = F(a, c-b; c; z)$$

> $$a, b$$ 的角色可以互換（想當然爾）

### Differentiation

$${d \over dz}F(a_1, \cdots, a_m; b_1, \cdots, b_n; z) \\ = {a_1 \cdots a_m \over b_1 \cdots b_n}F(a_1+1, \cdots, a_m+1; b_1+1, \cdots, b_n+1; z) \tag{1}$$

> Define operator $$\vartheta = z {d \over dz}$$

$$\vartheta F(a_1, \cdots, a_m; b_1, \cdots, b_n; z) = \sum_{k \geq 0} k{a_1^{\bar k}, \cdots a_m^{\bar k} \over b_1^{\bar k}, \cdots b_n^{\bar k}} {z^k \over k!} \tag{2}$$

底下比較有用：

$$(\vartheta + a_1)F(a_1, \cdots, a_m; b_1, \cdots, b_n; z) \\ = a_1F(a_1+1, \cdots, a_m; b_1, \cdots, b_n; z) \tag{3}$$

$$(\vartheta + b_1 - 1)F(a_1, \cdots, a_m; b_1, \cdots, b_n; z) \\ = (b_1 - 1)F(a_1, \cdots, a_m; b_1-1, \cdots, b_n; z) \tag{4}$$

綜合 $$(1), (3), (4)$$，

$${d \over dz}(\vartheta + b_1 - 1)\cdots(\vartheta + b_n - 1)F = (\vartheta + a_1)\cdots(\vartheta + a_m)F \tag{5}$$

然後兩邊都乘上 $$z$$

$${\vartheta}(\vartheta + b_1 - 1)\cdots(\vartheta + b_n - 1)F = z(\vartheta + a_1)\cdots(\vartheta + a_m)F \tag{6}$$

> 第一個 $$\vartheta$$ 可以想成 $$(\vartheta + 1 - 1)$$，對應 [term ratio](../hypergeometric_func-1/#term-ratio) 中分母的 $$(k+1)$$；其餘依樣對應（互相記憶的好方法！）

利用 *differentail theory*，可以驗證兩 identity 是否相同（利用 $$(6)$$）

> *"Every new identity for hypergeometrics has consequences for binomial
coefficients."* [CMath] p.222

> 但要注意[退化](../hypergeometric_func-1/#degenerate)

## Partial Hypergeometric Sums
[待續] p.237

