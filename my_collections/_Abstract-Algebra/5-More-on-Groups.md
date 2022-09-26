---
layout: page
title: More on Groups
usemathjax: true
tag: Abstract Algebra
time: 2022/09/22
---

**Table of Content**
- [Group of small order](#group-of-small-order)
  - [Order 1](#order-1)
  - [Order 2](#order-2)
  - [Order 3](#order-3)
  - [Order 4](#order-4)
- [The Nature of Groups](#the-nature-of-groups)

---

## Group of small order

> the cardinality of a group $$G = $$ the order of $$G$$

### Order 1

$$G = \{e\}$$ is unique and $$G \cong \mathbb{Z}_1 = \{\bar 0\}$$.


### Order 2

$$G = \{e, a\}$$, and $$a^{-1} = a$$ (the only choice).

藉由 **table**（如下）的方式，列出所有 element 經過 binary operation 的結果，再經過比對，可以得知 $$G \cong (\mathbb{Z}_2, +)$$。

|$$\dot{}$$|e|a|
|:---------:|:-:|:-:|
|**e**       |e|a|
|**a**       |a|e|

|$$+$$|$$\bar 0$$|$$\bar 1$$|
|:---------:|:-:|:-:|
|**$$\bar 0$$**       |$$\bar 0$$|$$\bar 1$$|
|**$$\bar 1$$**       |$$\bar 1$$|$$\bar 0$$|

> $$\bar 0 \to e, \bar 1 \to a$$.

### Order 3

By cancellation law, **every column and every row in the table cannot contain a repeated element**.

$$G \cong (\mathbb{Z}_3, +)$$

### Order 4

Let $$G = \{e, a, b, c\}.$$

**Case $$\rm I$$**: $$a^2 = b^2 = c^2 = e$$

> 大家都是自己的 inverse。

透過 **table** 可以得知

$$G \cong \mathbb{Z}_2 \times \mathbb{Z}_2。$$

**Case $$\rm II$$**: $$a^2 = b$$

> 至少一元素不是自己的 inverse。
> 可以看出，兩個 case 是所有可能性的一個 partition，其聯集涵蓋所有情況。

一樣透過 **table** 可以得知

$$G \cong (\mathbb{Z}_4, +)。$$

> 注意！$$G$$ 的 order 到 $$4$$ 的時候終於出現非唯一的群！

---

## The Nature of Groups

**Groups** 的一大特性就是 **symmetry**！在正三角形上，有六種操作可以使她不變（三旋轉、三鏡射），相當於 $$G$$ such that \|$$G$$\|$$=6$$。

$$X = \Delta$$（正三角形）, $$Sym(X) = \{e, a, a^2, b, c, d\}$$

$$a$$ 是旋轉，$$b, c, d$$ 是三種鏡射。

> 此處觀念待補。關鍵字：symmetric group