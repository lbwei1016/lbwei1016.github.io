---
layout: page
title: (LU) LDU Factorization
usemathjax: true
tag: Linear Algebra
---

> equivalent to *Gaussian Elimination*

## LU Factorization
$$A=LU$$, where $$L$$ is *lower triangular*, $$U$$ is *upper triangular* (Row echelon form)<br>
(Assume $$A$$ is properly permuted, i.e. all pivots are *non-zero*.)

$$\Pi E_{ij}A = U,$$

where $$E_{ij}$$ are Elimination matrices; hence $$L = (\Pi E_{ij})^{-1}$$.
> $$E_{ij}$$: use $$i^{th}$$ row to eliminate $$j^{th} $$ row for all $$i>j$$.

於是 $$L$$ 包含了 *Gaussian Elim.* 的過程資訊，而 $$U$$ 為 *Gaussian Elim.* 的結果。

---

## LDU Factorization
Let $$U_0 = DU$$, where $$D$$ is a *diagonal matrix*.

$$A = LDU$$, now both $$L$$ and $$U$$ are *unit trnagular matrix*.

### Theorem
> If A is factorizable, then the $$LDU$$ factorization is unique.

*Proof hint:* Lower and upper triangular matrices are totally different.

---

## Calculation
We know that $$L = (\Pi E_{ij})^{-1}$$, and here is a trick for calculating $$L$$. 

For instance, $$L = E_{21}^{-1}E_{31}^{-1}E_{32}^{-1}$$, which can be shown to be equal to $$E_{21}^{-1} + E_{31}^{-1} + E_{32}^{-1} - 2I$$; that is:

$$L = E_{21}^{-1} + E_{31}^{-1} + E_{32}^{-1} - 2I$$

*Proof:* cont.

乘法變成加法！想個例子試試？