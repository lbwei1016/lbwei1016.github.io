---
layout: page
title: Stirling Numbers
usemathjax: true
tag: Concrete Mathematics, Special Numbers
time: 2022/08/23
---

**Table of Content**
- [Definition](#definition)
  - [第一類 (cycle)](#第一類-cycle)
  - [第二類 (subset)](#第二類-subset)
- [Identities](#identities)
  - [邊界](#邊界)
  - [Recurrrence](#recurrrence)
  - [互換](#互換)
  - [Sums](#sums)
  - [Converting between powers](#converting-between-powers)
  - [Inversion formula](#inversion-formula)
- [Reference](#reference)

---

## Definition

### 第一類 (cycle)
- $$\begin{bmatrix}n \\ m \end{bmatrix}$$
> 在 $$n$$ 物中取 $$m$$ 個 cycle 的數量；例如 $$[1, 2, 3][4, 5]$$（$$\begin{bmatrix}5\\2\end{bmatrix}$$ 之一）。

> 念作 *n cycle k*；中括號聯想到 ***cycle***

> trademark sequence: $$6, 11, 6, 1$$

> 若 $$k < 0,\ n \geq 0$$，則定義為 $$0$$

---

### 第二類 (subset)
- $$\begin{Bmatrix}n \\ m\end{Bmatrix}$$
> 將 $$\{1, 2, \cdots, n\}$$ 分為 $$m$$ 個 non-empty subset 的方法數；例如 $$\{1\}, \{2, 3\}, \{4\}$$ （$$\begin{Bmatrix}4 \\ 3\end{Bmatrix}$$ 之一）。

> 念作 *n subset k*；大括號聯想到 ***set***

> trademark sequence: $$1, 7, 6, 1$$

> 若 $$k < 0,\ n \geq 0$$，則定義為 $$0$$

---

## Identities

### 邊界

$$\begin{bmatrix}n \\ 0 \end{bmatrix} = 0,\ \begin{bmatrix}0 \\ 0 \end{bmatrix} = 1;\ \begin{bmatrix}n \\ k \end{bmatrix} = 0,\ n < k$$

$$\begin{Bmatrix}n \\ 0 \end{Bmatrix} = 0,\ \begin{Bmatrix}0 \\ 0 \end{Bmatrix} = 1;\ \begin{Bmatrix}n \\ k \end{Bmatrix} = 0,\ n < k$$

$$\begin{bmatrix}n \\ n\end{bmatrix} = \begin{Bmatrix}n \\ n\end{Bmatrix} = 1;\ \begin{bmatrix}n \\ n-1\end{bmatrix} = \begin{Bmatrix}n \\ n-1\end{Bmatrix} = {n \choose 2}$$

$$\begin{bmatrix}n \\ 1 \end{bmatrix} = (n-1)!\ ;\ \begin{Bmatrix}n \\ 2 \end{Bmatrix} = 2^{n-1}-1;\ \begin{bmatrix}n+1 \\ 2 \end{bmatrix} = n!H_n$$

### Recurrrence

$$\begin{Bmatrix} n\\k\end{Bmatrix} = k\begin{Bmatrix} n-1\\k\end{Bmatrix} + \begin{Bmatrix} n-1\\k-1\end{Bmatrix},\ n \in \mathbb{Z}^+$$

$$\begin{bmatrix} n\\k\end{bmatrix} = (n-1)\begin{bmatrix} n-1\\k\end{bmatrix} + \begin{bmatrix} n-1\\k-1\end{bmatrix},\ n \in \mathbb{Z}^+$$

### 互換

$$\begin{Bmatrix} n\\m\end{Bmatrix} = \begin{bmatrix} -m\\-n\end{bmatrix}$$

### Sums

$$\sum_{k=0}^n\begin{bmatrix}
    n \\ k
\end{bmatrix} = n!\ ,\ n \in \mathbb{N}$$

### Converting between powers

$$x^n = \sum_k\begin{Bmatrix}n \\ k\end{Bmatrix}x^{\underline k} = \sum_k\begin{Bmatrix}n \\ k\end{Bmatrix}(-1)^{n-k}x^{\bar k},\ n \in \mathbb{N}$$

$$x^{\bar n} = \sum_k\begin{bmatrix}n \\ k\end{bmatrix}x^k,\ n \in \mathbb{N}$$

$$x^{\underline{k}} = \sum_k\begin{bmatrix}n \\ k\end{bmatrix}(-1)^{n-k}x^k,\ n \in \mathbb{N}$$

> Use [this identity](../Finite-Calculus/#basics).（有負號的）

### Inversion formula

$$\sum_k\begin{Bmatrix}n \\ k\end{Bmatrix}\begin{bmatrix}k \\ m\end{bmatrix}(-1)^{n-k} = \sum_k\begin{bmatrix}n \\ k\end{bmatrix}\begin{Bmatrix}k \\ m\end{Bmatrix}(-1)^{n-k} = [m = n] \tag{1}$$

$$g(n) = \sum_k\begin{Bmatrix}n \\ k\end{Bmatrix}(-1)^kf(k) \iff f(n) = \sum_k\begin{bmatrix}n \\ k\end{bmatrix}(-1)^kg(k) \tag{2}$$

> 將 [Converting between powers](#converting-between-powers) 的公式互相代入可以證明 $$(1)$$，然後 $$(1)$$ 可以證明 $$(2)$$

---

## Reference
- [CMath] (p.264), Concrete Mathematics: A Foundation for Computer Science, by Ronald Graham, Donald Knuth, and Oren Patashni