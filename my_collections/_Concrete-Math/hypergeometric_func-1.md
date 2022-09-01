---
layout: page
title: Hypergeometric Functions I
usemathjax: true
tag: Concrete Mathematics, Hypergeometric
time: 2022/08/30
---

**Table of Content**
- [Definitions](#definitions)
- [Prerequisites](#prerequisites)
  - [Factorial Function](#factorial-function)
  - [Gamma Function](#gamma-function)
  - [Factorial Powers](#factorial-powers)
- [概要](#概要)
- [Identities](#identities)
  - [(Gaussain)](#gaussain)
  - [Kummer's formula](#kummers-formula)
  - [Dixon's formula](#dixons-formula)
  - [Saalschütz's identity](#saalschützs-identity)
  - [Euler's Identity](#eulers-identity)
- [**Term Ratio**](#term-ratio)
- [Degenerate](#degenerate)

---

## Definitions

$$F(a_1, \cdots, a_m; b_1, \cdots, b_n; z) = \sum_{k \geq 0} {a_1^{\bar k}, \cdots a_m^{\bar k} \over b_1^{\bar k}, \cdots b_n^{\bar k}} {z^k \over k!}$$

> 這是 hypergeometric series；有兩行的表示法，但我不知道怎麼用 *MathJax* 表示

> $$a_i$$ 叫 *upper parameter*、$$b_i$$ 叫 *lower parameter*、$$z$$ 叫 *argument*

> 參數基本上只要 $$b > 0$$ 就好（避免 divide by zero），沒有其他限制；底下再會討論 *degenerate* 的情況

> $$\mathcal{R}_a$$ 是 $$a \in \mathbb{C}$$ 的實部

---

## Prerequisites

> 為了讓 hypergeometric function 的參數可以是任意複數（而非只是整數）的 *generalization*

### Factorial Function

> Defined for all $$z \in \mathbb{C}$$

$${1 \over z!} = \lim_{n \to \infty}{n+z \choose n}n^{-z} \tag{1}$$

$$z! = \int^{\infty}_0 t^ze^{-t}dt,\ \mathcal{R}_z > -1 \tag{2}$$

> 同樣的，$$z! = z(z-1)!$$

### Gamma Function

$$\Gamma(z+1) = z! \tag{1}$$

$$(-z)!\Gamma(z) = {\pi \over \sin\pi z} \tag{2}$$

> 當 $$z$$ 是負的，$$(2)$$ 就派上用場

### Factorial Powers

$$z^{\underline w} = {z! \over (z-w)!}$$

$$z^{\bar w} = {\Gamma(z+w) \over \Gamma(z)}$$

> 極限情況見 [CMath] p.211

---

## 概要

*Hypergeometric function*，超幾何函數。許多 infinite series 都能以這樣的形式表現，於是可以利用 hypergeometric function 的眾多性質，系統性的操作這些 series（包括在 [Binomial Coefficient](../Binomial-Coefficient) 見到的 series）；以下舉些例子：

$$F(1; 1; z) = \sum_{k \geq 0} {z^k \over k!} = e^z$$

$$F(-n, 1; 1; 1) = \sum_k {(-n)^{\bar k} 1^{\bar k} \over 1^{\bar k}} {z^k \over k!} = \sum_k {n \choose k}(-1)^k.$$

某些常見的形式有特殊的名字，像是 *confluent hypergeometric series*：

$$F(a; b; z) = \sum_{k \geq 0}{a^{\bar k} \over b^{\bar k}}{z^k \over k!} = M(a, b, z)$$

還有 *Gaussian hypergeometric*：

$$F(a, b; c; z) = \sum_{k \geq 0}{a^{\bar k}b^{\bar k}z^k \over c^{\bar k}k!} \tag{1}$$

$$F(a, b; c; 1) = {\Gamma(c-a-b)\Gamma(c) \over \Gamma(c-a)\Gamma(c-b)},\ b \leq 0 \tag{2}$$

$$F(a, -n; c; 1) = {(c-a)^{\bar n} \over c^{\bar n}} = {(a-c)^{\underline{n}} \over (-c)^{\underline{n}}}. \tag{3}$$

> $$(3)$$ 涵蓋了 [Vandermonde’s Convolution 和他的所有變體](../Binomial-Coefficient/#vandermondes-convolution)；這就是 *hypergeometric function* 的強大之處

> 這裡不討論 series 的歛散，詳見 [CMath] p.206。

---

## Identities

### (Gaussain)

$$F(a, -n; c; 1) = {(c-a)^{\bar n} \over c^{\bar n}} = {(a-c)^{\underline{n}} \over (-c)^{\underline{n}}}. \tag{1}$$

### Kummer's formula

$$F(a, b; 1+b-a; -1) = {(b/2)! \over b!}(b-a)^{\underline{b/2}} \tag{2}$$

### Dixon's formula

$$
F(a, b, c; 1+c-a, 1+c-b; 1) \\
= {(c/2)! \over c!}{(c-a)^{\underline{c/2}}(c-b)^{\underline{c/2}} \over (c-a-b)^{\underline{c/2}}},\ \mathcal{R}_a + \mathcal{R}_b < 1 + \mathcal{R}_c/2 \tag{3} 
$$

### Saalschütz's identity

$$F(a, b, -n; c, a+b-c-n+1; 1) = {(c-a)^{\bar n}(c-b)^{\bar n} \over c^{\bar n}(c-a-b)^{\bar n}} = {(a-c)^{\underline{n}}(b-c)^{\underline{n}} \over (-c)^{\underline{n}}(a+b-c)^{\underline{n}}} \tag{4}$$

> $$(4)$$ 可看作是 $$(1)$$ 的擴充版

### Euler's Identity

$$F(a, b; c; z) = (1-z)^{c-a-b}F(c-a, c-b; c; z) \tag{5}$$

---

## **Term Ratio**

$$F(a_1, \cdots, a_m; b_1, \cdots, b_n; z) = \sum_{k \geq 0}t_k,\ t_k = {a_1^{\bar k}, \cdots a_m^{\bar k} \over b_1^{\bar k}, \cdots b_n^{\bar k}} {z^k \over k!}$$

所以

$${t_{k+1} \over t_k} = {(k+a_1)\cdots(k+a_m)z \over (k+b_1)\cdots(k+b_n)(k+1)}$$

*"This is a rational function of $$k$$."*，也就是說，分子分母都是 $$k$$ 的 polynomial。

> 注意分母的 $$(k+1)$$，如果沒有要補上；分子的 $$z$$ 則是任何沒有 $$k$$ 的**常數**

這是將**任一** series 轉換成 hypergeometric series 的**關鍵想法**（前提是該 series 本來就有潛力成為 hypergeometric series）：**我們只需要求出 *term ratio*，再對應 $$a_i, b_i, z$$ 即可！**

---

## Degenerate

當 lower parameter $$b < 0$$，hypergeometric function 理應是沒有定義的，但如果我們好好處理如此「退化」情形，有機會可以正確地求值。

例如：

$$\sum_{k \leq m}{m+k \choose k}2^{-k} = 2^m \iff \sum_{k \geq 0}{2m-k \choose m-k}2^k = 2^{2m}$$

利用上述 *term ratio* 求出 hypergeometrc function：

$${2m \choose m}F(1, -m; -2m; 2) = 2^{2m}$$

但是，lower parameter $$-2m$$ 是負的，造成整個 function undefined！幸好，「從非退化點逼近」可以幫助我們解決問題！

先看簡單的例子：

$${-1 \choose -1} = 0 = \lim_{\epsilon \to 0}{-1+\epsilon \choose -1} = 1 \tag{1}$$

但是

$$\lim_{\epsilon \to 0}{-1+\epsilon \choose -1+\epsilon} = 1 \tag{2}$$

> Why $$(2) = 1$$? 試用 [generalized factorial function](#factorial-function) 展開

> $$\epsilon$$ 是為了跳開 $$0$$，像是 $$(-1)^{\bar 3} = 0$$ 但 $$(-1 + \epsilon)^{\bar 3} \not = 0$$

這例子顯示，針對同一函數的不同逼近方法（$$\epsilon$$ 擺放位置）會帶來不同的值，要小心！

那該如何在我們待解決的問題中放上正確的 $$\epsilon$$？lower parameter 是一定要的，upper parameter 呢？

先看最初的 series，發現邊界條件是 $$k \leq m$$，也就是對於所有 $$ k > m$$，$$F = 0$$。但如果 upper parameter 變成 $$-m + \epsilon$$，則 $$F$$ 永遠都不為 $$0$$！（$$1 + \epsilon$$ 則是沒意義）；所以候選正確形式為：

$${2m \choose m}\lim_{\epsilon \to 0}F(1, -m; -2m+\epsilon; 2)$$

檢查：當 $$k > m$$，$$F$$ 的 term（含極限，經過化簡）是：

$$\lim_{\epsilon \to 0}{0 \over \epsilon} = 0$$

正確！最終版就是：

$${2m \choose m}\lim_{\epsilon \to 0}F(1, -m; -2m+\epsilon; 2) = 2^{2m},\ m \in \mathbb{Z}^+ \tag*{$\blacksquare$}$$