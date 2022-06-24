---
layout: page
title: Matrix
usemathjax: true
tag: Linear Algebra
---

## Properties

* $$A (BC) = (AB) C$$: Associative Law (結合)
* $$AB \neq BA$$: Communitative Law (交換)
* $$A (B+C) = Ab + AC$$；$$(A+B) C = AB + AC$$: Distributitive Law (分配)

## Matrix: with Gaussian-Jordan Elimination

* use vector-matrix product to represent *row reduction(or adding)* in Elimination

  > **matrix-vector product:**
  >
  > * 如果是 matrix-**column**_vector product，結果就是 the linear combination of **columns** of the matrix
  >   * $$A_{m\times n}\boldsymbol{v_{n\times 1}} = \boldsymbol{b_{m\times 1}}$$ (column vector 在右)
  > * 若為 matrix-row_vector product，結果是 the linear combination of **rows** of the matrix
  >   * $$\boldsymbol{v_{1\times m}A_{m\times n}} = \boldsymbol{b_{1\times n}}$$ (row vector 在左)
  > * vector entries are the coefficients
  >
  > 上述可以推廣至 **matrix multiplication**

### Elucidation

> Matrix 的每一 row 皆為一 linear equation，利用 matrix-row vector product 來表示某一種列運算 (the linear combination of **rows**)；因為列運算只包含**加、乘(scalar)**，符合 linear combination 的定義。

### Summary

> Gaussian Elimination of *any* matrix can be expressed as multiplications of matrices using only **elimination** and **permutation** matrices.

* Elimination matrix: $$E_{ij}$$ for *row deduction* 

  * Reduce row $$i$$ with row $$j$$ 

* Permutation matrix: $$P_{ij}$$ for *row exchange* 

  * Exchange row $$i$$ and row $$j$$ (in identity matrix $$I$$)

    >$$P_{ij} \times P_{ij} = I$$<br>
    >e.g. $$P_{21} = \begin{bmatrix}0&1&0\\1&0&0\\0&0&1\end{bmatrix}$$ 

##  Inverse

### Definition

> $$A$$ is ***invertible*** if there exists a matrix $$B$$ s.t. $$AB = BA = I$$, and $$B$$ is the ***inverse matrix of*** $$A$$ ($$A^{-1}$$).
>
> Note: Both *right*($$AB=I$$)and *left*($$BA=I$$)inverse must exist. 

### Theorem

> Invertible matrix must be a *square matrix*. (Both *left inverse* and *right inverse* exists)

### Gaussain-Jordan Elimination for Finding Inverse Matrix

## LU, LDU Factorization(Decomposition)

## Transpose

> For matrix $$A$$, denote $$A^T$$ as the *transpose* of $$A$$, where the columns of $$A^T$$ are the rows of $$A$$. 

### Symmetric 

> If $$A$$ is symmetric, $$A = A^T$$, i.e. $$a_{ij} = a_{ji}$$.

> Notes for *Inverse*, *Gaussain-Jordan Elimination for Finding Inverse Matrix*, *LU, LDU Factorization(Decomposition)*, *Transpose*, and *Symmetric* are attached below.
