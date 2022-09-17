---
layout: page
title: Generating Functions
usemathjax: true
tag: Concrete Mathematics, Generating Functions
time: 2022/09/13
---

**Table of Contents**
- [Why Generating Functions?](#why-generating-functions)
- [What is a Generating Function?](#what-is-a-generating-function)
- [Basics](#basics)
  - [Linear Combination](#linear-combination)
  - [Shift Right](#shift-right)
  - [Shift Left](#shift-left)
  - [Constant Multiple](#constant-multiple)
  - [Differentiation](#differentiation)
  - [Integration](#integration)
  - [Multiplication](#multiplication)
- [More Generating Functions](#more-generating-functions)

---

## Why Generating Functions?

以往對數列的操作，僅針對單一元素（$$a_3 = 8$$）或某遞迴關係（$$a_n = 2a_{n-1}$$）；有沒有可能同時操作「整個」數列呢？如此一來，計算由多個數列組成的新數列（如 $$<a_n + b_n>, <a_nb_n>$$）或許能變得容易許多？抑或是得以系統性地解遞迴關係？

> 如果 $$a_n, b_n$$ 遞迴結構相同，解 $$<a_n + b_n>$$ 等可用 [the repertoire method](../solving-recurrence-1/#the-repertoire-method) 的想法；若不同，則得個別解出 closed form。（是嗎？）

---

## What is a Generating Function?

**Generating function** 是一個函數，可以展開為 *infinite power series*，例如 $$G(z) = 1 / 1-2z = \sum_n2^nz^n$$；其中我們感興趣的是 $$z^n$$ 的係數，也就是 $$[z^n]G = 2^n$$：欲操作的數列就在係數。

換句話說：$$<g_n>$$ 是我們想操作的數列，它的 **generating function** 就是 $$G(z) = \sum_n g_nz^n$$。

> $$G$$ is called a generating function, because they
generate the coeffcients of interest.

> 為了方便起見，定義 $$g_{-1} = g_{-2} = \cdots = 0$$，如此在大多數情形就不必理會 $$\sum$$ 的邊界。

某 **generating function** $$G$$ 可以從兩種觀點來詮釋：
1. a function of a complex variable $$z$$
2. a power series, with $$z$$ acting as a *placeholder*

第一種觀點中，$$G$$ 定義為符合任意微積分性質；第二種觀點中，*placeholder* 意指 $$z^n$$ 可以解釋為任意具有組合性質、出現 $$n$$ 次的物件（像是 $$n$$ 個骨牌、$$n$$ 個硬幣），然後再抽象化，以 $$z$$ 表示。

> *Note:* 我們不考慮 generating functions' *convergence*，因為即使 power series 發散，所有 gf 的操作依然具正當性；即使操作不合法，我們也可以用 gf 求出「答案」後再 *prove by induction*（事後諸葛）。詳見 [CMath] p.331, 332。

> **gf:** generating function

---

## Basics

> Let $$F(z)$$ be the generating function for $$<f_n>$$, $$G(z)$$ be that for $$<g_n>$$.

### Linear Combination

$$\alpha F(z) + \beta G(z):\ <\alpha f_n + \beta g_n> \tag{1}$$

### Shift Right

$$z^mG(z) = \sum_n g_nz^{n+m} = \sum_n g_{n-m}z^n:\ <0, \cdots, 0, g_0, g_1, \cdots> \tag{2}$$

### Shift Left

$$(G(z) - \sum_{0 \leq n \leq m-1}g_nz^n) / z^m = \sum_{n \geq m}g_nz^{n-m} = \sum_{n \geq 0}g_{n+m}z^n \tag{3}$$

> 注意 $$n \geq 0$$。

### Constant Multiple

$$G(cz):\ <c^ng_n> \tag{4}$$

### Differentiation

$$G'(z) = \sum_n (n+1)g_{n+1}z^n \tag{5}$$

$$zG'(z):\ <ng_n> \tag{6}$$

### Integration

$$\int_0^z G(t) dt = \sum_{n \geq 1}{1 \over n}g_{n-1}z^n \tag{7}$$

### Multiplication

$$F(z)G(z) = \sum_n\Big(\sum_k f_kg_{n-k}\Big)z^n = \sum_n h_nz^n \tag{8}$$

> $$<h_n>$$ 是 $$<f_n>$$ 和 $$<g_n>$$ 的 **convolution**。

令 $$F(z) = {1 \over 1-z} = \sum_n z^n$$，

$${1 \over 1-z}G(z) = \sum_n\Big(\sum_{k \leq n}g_k\Big)z^n \tag{9}$$

> $$(9)$$ 用來計算前綴和（cumulative sum）！

---

## More Generating Functions

$$\sum_n {c \choose n}z^n = (1+z)^c \tag{1}$$

> 當 $$n < 0$$，$${c \choose n} = 0。$$

$$\sum_n {c+n-1 \choose n}z^n = {1 \over (1-z)^c} \tag{2}$$

> [Negation](../Binomial-Coefficient/#negation)

$$\sum_{n \geq 1}{1 \over n}z^n = \ln{1 \over 1-z} \tag{3}$$

$$\sum_{n \geq 1}{(-1)^{n+1} \over n}z^n = \ln(1+z) \tag{4}$$

> [Integration](#integration)；小心邊界

$$\sum_{n \geq 0}{z^n \over n!} = e^z \tag{5}$$

$$\sum_{n \geq 0}{(-1)^n \over (2n+1)!}z^{2n+1} = \sin z \tag{6}$$

$$\sum_{n \geq 0}{(-1)^n \over (2n)!}z^{2n} = \cos z \tag{7}$$


見 [CMath] p.335, 351