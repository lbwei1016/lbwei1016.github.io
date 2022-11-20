---
layout: page
title: Fields of Quotients
usemathjax: true
tag: Abstract Algebra, Ring, Field
time: 2022/11/19
---

**Table of Content**
- [Motivation](#motivation)
- [Definition (field of fractions) (field of quotients)](#definition-field-of-fractions-field-of-quotients)
  - [Lemma (defining operations on $$F$$)](#lemma-defining-operations-on-f)
  - [Proof ($$F$$ is a field)](#proof-f-is-a-field)
  - [Remark](#remark)
    - [Definition (subdomain)](#definition-subdomain)

---

## Motivation

An integral domain is not necessarily a field, but how can we *make* it a field? To make an integral domain a field, we need to add the **inverses $$1/a$$** and also add elements of the form **$$b/a$$**, into the set.

---

## Definition (field of fractions) (field of quotients)

First define a set

$$
S = \{(a,b):a,b\in D, b\not =0\},
$$

where $$D$$ is an integral domain and $$(a,b)\in S$$ is regarded as a formal fraction $$a/b$$. Then define a relation $$\sim$$ on $$S$$ by 

$$
(a,b)\sim (c,d) \iff ad=bc,
$$

which is an equivalence relation. Let $$a/b$$ denote the equivalence calss containing $$(a,b)$$, ant let 

$$
F = \{a/b: (a,b)\in S\}
$$

be the set of **all equivalence classes**. We now define addition and multiplication on $$F$$, and then show that $$F$$ **becomes a field** under these operations.

### Lemma (defining operations on $$F$$)
>
>For $$(a/b, c/d)$$ in $$F\times F$$, the assignments
>
>$$
>+:(a/b,c/d)\mapsto(ad+bc)/bd
>$$
>
>and 
>
>$$
>\times:(a/b,c/d)\mapsto ac/bd
>$$
>
>are well-defined functions from $$F\times F\to F$$.

There are two approaches to show an opeartion is well-defined, and below we only prove $$+$$ is well-defined; $$\times$$ can be proved in a similar way.

**Approach $$\rm I$$** (elements in two sums are equivalent)

We are going to show that if $$(a_1, b_1)\sim(a_2,b_2)$$ and $$(c_1, d_1)\sim(c_2, d_2)$$, then

$$
(a_1d_1+b_1c_1, b_1d_1) \sim (a_2d_2+b_2c_2, b_2,d_2).
$$

> $$(a_1d_1+b_1c_1, b_1d_1) \in (a_1d_1+b_1c_1)/b_1d_1$$.

We have

$$
\begin{align*}
(a_1d_1+b_1c_1)b_2d_2 &= (a_1b_2)d_1d_2 + (c_1d_2)b_1b_2 \\
&= (a_2b_1)d_1d_2 + (c_2d_1)b_1b_2 \\
&= (a_2d_2 + c_2b_2)b_1d_1.
\end{align*}
$$

Thus $$(a_1d_1+b_1c_1, b_1d_1) \sim (a_2d_2+b_2c_2, b_2,d_2)$$ and $$+:F\times F\to F$$ is well-defined. ◼

> 回頭看看 $$\sim$$ 在 $$S$$ 上的定義！

**Approach $$\rm II$$** (two sums are equal)

We now are to show that if $$(a_1, b_1)\sim(a_2,b_2)$$ and $$(c_1, d_1)\sim(c_2, d_2)$$, then

$$
a_1/b_1 + c_1/d_1 = a_2/b_2 + c_2/d_2.
$$

We have

$$
\begin{align*}
a_1/b_1 + c_1/d_1 &= (a_1d_1 + b_1c_1)/b_1d_1 \\
&= b_2d_2(a_1d_1 + b_1c_1)/b_2d_2b_1d_1 \\
&= [(a_1b_2)d_1d_2 + (c_1d_2)b_1b_2] / b_1b_2d_1d_2 \\
&= [(a_2b_1)d_1d_2 + (c_2d_1)b_1b_2] / b_1b_2d_1d_2 \\
&= (a_2d_2 + b_2c_2)/b_2d_2 \\
&= a_2/b_2 + c_2/d_2.
\end{align*}
$$

Thus the well-definedness of $$+$$ is proved. ◼

> 可用 $$\mathbb{Z}_n$$ 上的運算做類比，比較容易思考！

> 在這個例子中，Approach $$\rm I$$ 比較方便。

Next we should prove that $$\langle F,+,\times\rangle$$ is indeed a field.

### Proof ($$F$$ is a field)

By definition, $$D$$ is an integral domain, which is a **communtative ring without zero divisors**. We can then observe that $$F$$ also satisfies all the properties of an integral domain. Thus the remaining task for us is to show that every element in $$F$$ is a **unit**:

For all $$a/b \in F$$, there exist $$b/a \in F$$ such that 

$$
a/b \times b/a = ab/ab = 1_D/1_D = 1_F \in F.
$$

Thus every element in $$F$$ is a unit, and we have proved that $$F$$ is a field. ◼

### Remark

#### Definition (subdomain)
> A **subdomain** of $$(R,+,\circ)$$ is a subset $$S$$ of $$R$$ such that $$(S,+_S,\circ_S)$$ is an **integral domain**.

The set $$D' = \{a/1:a\in D \}$$ is a subdomain of $$F$$, which is **canonically isomorphic to $$D$$**.

For **every integral domain** $$D$$, there exists a field containing a subdomain isomorphic to $$D$$. Furthermore, if a field $$K$$ contains $$D$$, then it contains a **subfield isomorphic to $$F$$** defined earlier. Thus, $$F$$ can be regarded as the **smallest field containing $$D$$**.