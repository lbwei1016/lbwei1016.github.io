---
layout: page
title: Stirling Numbers
usemathjax: true
tag: Concrete Mathematics, Permutation
time: 2022/08/23
---

**Table of Content**
- [第一類 (cycle permutation)](#第一類-cycle-permutation)
- [第二類 (disjoint set)](#第二類-disjoint-set)
- [Operations](#operations)

---

## 第一類 (cycle permutation)
- $$\begin{bmatrix}n \\ m \end{bmatrix}$$
> $$\{1, 2, \cdots, n\}$$ 中取 $$m$$ 個 cycle 的 permutation 數量；例如 $$(1, 2, 3)(4, 5)$$（$$\begin{bmatrix}5\\2\end{bmatrix}$$ 之一）。

## 第二類 (disjoint set)
- $$\begin{Bmatrix}n \\ m\end{Bmatrix}$$
> $$\{1, 2, \cdots, n\}$$ 分為 $$m$$ 個 disjoint set 的方法數；例如 $$\{1\}, \{2, 3\}, \{4\}$$ （$$\begin{Bmatrix}4 \\ 3\end{Bmatrix}$$ 之一）。

---

## Operations

$$\begin{Bmatrix} n\\m\end{Bmatrix} = m\begin{Bmatrix} n-1\\m\end{Bmatrix} + \begin{Bmatrix} n-1\\m-1\end{Bmatrix} \tag{1}$$

$$\begin{Bmatrix} n\\m\end{Bmatrix} = \begin{bmatrix} -m\\-n\end{bmatrix} \tag{2}$$

