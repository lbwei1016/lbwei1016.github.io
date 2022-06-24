---
layout: page
title: Solving Linear Equations
usemathjax: true
tag: Linear Algebra
--- 

> $$A\boldsymbol{x} = \boldsymbol{b}$$
>
> e.g. $$A = \begin{bmatrix}1&-2\\3&2\end{bmatrix}$$ (coeffient matrix), $$\boldsymbol{x} = \begin{bmatrix}x_1\\x_2\end{bmatrix}$$ (variable vector), $$\boldsymbol{b} = \begin{bmatrix}1\\11\end{bmatrix}$$ 
>
> If a linear equation system is *consistent*: has solution；*inconsistent*: no solution

* row picture

> the solution is the intersection(s) of lines, planes, etc
>
> (to visualize: x-y plane)

* column picture

> Find the ***linear combination*** of ***column vectors*** is to find the solution.
>
> (to visualize: *vector space*)
>
> ($$x\begin{bmatrix}1\\3\end{bmatrix} + y\begin{bmatrix}-2\\2\end{bmatrix} = \begin{bmatrix}1\\11\end{bmatrix}$$)
>
> <img src="D:\大學課程\大一\線代\2D_vectorspace.jpg" style="zoom:33%;" />

 * benefit
    * For a given $$A$$, the structure of the problem is fixed for all $$\boldsymbol{b}$$ 

## Gaussian Elimination

> Elementary Row Operations:
>
> 1. Row exchange (interchange)
> 2. Row reduction (row addition)
> 3. Scaling
* augmented matrix
  * do *elementary row operation* to let $$A$$(coeffient matrix) become **upper triangular form**
    * then the whole *augmented matrix* becomes ***row echelon form*** 

### Row Echelon Form (REF)

#### Define REF

1. All *zero rows* should be at the bottom.

2. Each *pivot* (leading coefficient, or say leading entry) of a non-zero row should always be strictly at the right of the pivot of the row above.

   > leading entry(coefficient): the first non-zero entry of a row

   e.g. $$\begin{bmatrix}11&2&3&4\\0&1&2&5\\0&0&7&9\end{bmatrix}$$

## Jordan Elimination

### Reduced Row Echelon Form (RREF)

#### Steps to obtain REF or RREF

1. Determine:  

> *pivot column*: the leftmost non-zero column
>
> *pivot position*: the top most position (the first row) in a pivot column

2. In the pivot column, bring any non-zero entry which is *not ignored* into pivot position. (row exchange)

3. Change each entry below pivot position into zero. (row reduction)

4. *Ignore* the row containing the pivot position (for further operations), and repeat step 1-4 on the submatrix that remains if there is a non-zero row that is ***not*** ignored.

   > the above 4 steps makes for REF
   >
   > *w/* represents *with*；*w/o* represents *without*

5. Scale the pivot to make them 1, and change the entries above the pivot into 0s. (backwards: 從右方的 column 開始)

6. If step 5 was performed using the first row, stop. Otherwise, repeat step 5 on the preceding row.

> the above 6 steps makes for RREF

#### Define RREF

1. The matrix is in REF

2. If a column contains the pivot of some row, then **all the other** entries of that column are 0.

3. The pivot of each non-zero row is 1.

   e.g. $$\begin{bmatrix}1&2&0&0&4\\0& 0&1&0&5\\0&0&0&1&9\end{bmatrix}$$ ($$x_1, x_3, x_4$$ are *basic variables*, while $$x_2$$ is a *free variable*)
