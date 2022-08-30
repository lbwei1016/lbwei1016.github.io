---
layout: page
title: Hypergeometric Functions
usemathjax: true
tag: Concrete Mathematics, Binomial
time: 2022/08/230
---

**Table of Content**

---

## Definitions

$$F(a_1, \cdots, a_m; b_1, \cdots, b_n; z) = \sum_{k \geq 0} {a_1^{\bar k}, \cdots a_m^{\bar k} \over b_1^{\bar k}, \cdots b_n^{\bar k}} {z^k \over k!}$$

> 這是 hypergeometric series；有兩行的表示法，但我不知道怎麼用 *MathJax* 表示

## 說明

*Hypergeometric function*，超幾何函數。許多 infinite sums 都能以這樣的形式表現，於是可以利用 hypergeometric function 的眾多性質，系統性的操作這些 sum（包括在 [Binomial Coefficient](../Binomial-Coefficient) 見到的 sum）；以下舉些例子：

$$F(1; 1; z) = \sum_{k \geq 0} {z^k \over k!} = e^z$$

$$F(-n, 1; 1; 1) = \sum_k {(-n)^{\bar k} 1^{\bar k} \over 1^{\bar k}} {z^k \over k!} = \sum_k {n \choose k}(-1)^k$$

> 

