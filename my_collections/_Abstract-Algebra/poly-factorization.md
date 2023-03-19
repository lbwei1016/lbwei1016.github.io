---
layout: page
title: Polynomial Factorization
usemathjax: true
tag: Abstract Algebra, Polynomial, Field
time: 2022/11/24
---

**Table of Content**
- [Gauss's Lemma](#gausss-lemma)
  - [Definition (content)](#definition-content)
    - [Theorem (product of primitive)](#theorem-product-of-primitive)
  - [Theorem (Gauss's Lemma)](#theorem-gausss-lemma)
  - [Corollary (irreducible)](#corollary-irreducible)
  - [Corollary (zero format)](#corollary-zero-format)
- [Factorization Modulo a Prime](#factorization-modulo-a-prime)
  - [Lemma (reduction modulo a number)](#lemma-reduction-modulo-a-number)
  - [Theorem (irreducible or not)](#theorem-irreducible-or-not)
  - [Theorem (Eisenstein criterion)](#theorem-eisenstein-criterion)
  - [Remark](#remark)
  - [Corollary (p-th cyclotomic polynomial)](#corollary-p-th-cyclotomic-polynomial)
    - [Remark](#remark-1)
  - [More on cyclotomic polynomials](#more-on-cyclotomic-polynomials)
    - [Facts](#facts)
- [Unique Factorization](#unique-factorization)
  - [Basics](#basics)
    - [Definition (divisor)](#definition-divisor)
    - [Lemma (irreducible)](#lemma-irreducible)
    - [Definition (common divisor)](#definition-common-divisor)
    - [Definition (gcd)](#definition-gcd)
    - [Theorem (Euclidean algorithm)](#theorem-euclidean-algorithm)
  - [Irreducible polynomials](#irreducible-polynomials)
    - [Theorem (like prime)](#theorem-like-prime)
    - [Theorem (unique factorization)](#theorem-unique-factorization)
    - [Theorem (irreducibility and square)](#theorem-irreducibility-and-square)
- [Ring of Residue Classes](#ring-of-residue-classes)
  - [Definition (ring of residue classes)](#definition-ring-of-residue-classes)
  - [Theorem (irreducible and field)](#theorem-irreducible-and-field)
  - [Example](#example)
  - [Remark](#remark-2)
  - [Question ($$x^4+1$$)](#question-x41)
- [Reference](#reference)

---

## Gauss's Lemma

### Definition (content)
> For an **integer** polynomial $$f(x) = a_nx^n+\cdots+a_0$$, we define the content of $$f(x)$$ to be $$\gcd(a_0,\cdots,a_n)$$, denoted by $$\text{Con}(f)$$.

> When $$\text{Con}(f) = 1$$, $$f(x)$$ is called **primitive**.

#### Theorem (product of primitive)
> If $$f(x)$$ and $$g(x)$$ are primitive, so is $$f(x)g(x)$$.

**Proof**

Suppose not, let $$p$$ be a prime factor of $$\text{Con}(fg)$$. Then every coefficient of $$f(x)g(x)$$  must be congruent to zero modulo $$p$$. In other words, $$\bar{f}(x)\bar{g}(x)$$ is equal to zero in $$\mathbb{Z}_p[x]$$. 

On the other hand, since $$\text{Con}(f) = \text{Con}(g) = 1$$, there are some coefficients of $$f(x)$$ and $$g(x)$$ not divided by $$p$$. In other words, $$\bar{f}(x)$$ and $$\bar{g}(x)$$ are both not equal to zero in $$\mathbb{Z}_p[x]$$. Therefore, $$\bar{f}(x)$$ and $$\bar{g}(x)$$ are zero divisors of $$\mathbb{Z}_p[x]$$, which is a contradiction, since the polynomial ring over an integral domain is still an integral domain. ◼

### Theorem (Gauss's Lemma)
> Let $$f(x)$$ be a nonzero **primitive** integer polynomial. If $$f(x) = g(x)h(x) $$ for some $$g(x)$$ and $$h(x)$$ in $$\mathbb{Q}[x]$$, then there exist some $$a\in \mathbb{Q}^\times$$ such that $$\tilde{g}(x)=ag(x) $$ and $$\tilde{h}(x) = a^{-1}h(x) $$ are integer polynomials. Especially, $$f(x)$$ can be **factorized over $$\mathbb{Z}[x]$$** as a product of $$\tilde{g}(x)$$ and $$\tilde{h}(x)$$.

> 只要把 $$f(x)$$ 的係數的公因數提出來，$$f(x)$$ 就變成 primitive 了。

**Proof**

Suppose $$f(x)=g(x)h(x)$$. Let $$a$$ and $$b$$ be the rational numbers such that $$\tilde{g}(x)=ag(x)$$ and $$\tilde{h}(x)=bh(x)$$ are primitive integer polynomials. It remains to show that $$ab=1$$. Write $$ab=r/s$$, where $$r$$ and $$s$$ are coprime integers. Then

$$
f(x) = {1\over a}\tilde{g}(x)\cdot {1\over b}\tilde{h}(x) = {s\over r}\tilde{g}(x)\tilde{h}(x).
$$

Since $$\tilde{g}(x)$$ and $$\tilde{h}(x)$$ are primitive, $$\tilde{g}(x)\tilde{h}(x)$$ is also primitive. Therefore, 

$$
r = \text{Con}(rf(x)) = \text{Con}(s\tilde{g}(x)\tilde{h}(x)) = s,
$$

which means $$ab=1$$. ◼

### Corollary (irreducible)
> A primitive integer polynomial is irreducible over $$\mathbb{Q}[x]$$ iff it is irreducible over $$\mathbb{Z}[x]$$.

> 從有理數縮減至整數！

### Corollary (zero format)
> For $$f(x) = a_nx^n+\cdots+a_0 \in \mathbb{Z}[x]$$, the zeros of $$f(x)$$ are of the form $$b/c$$ with $$b\vert a_0$$ and $$c\vert a_n$$.

--- 

## Factorization Modulo a Prime
### Lemma (reduction modulo a number)
> Let $$m>1$$ be a positive integer. Define $$\phi_m: \mathbb{Z}[x]\to \mathbb{Z}_m[x]$$ by 
>
> $$
> \phi_m(a_nx^n + \cdots + a_0) = \bar{a_n}x^n+\cdots+\bar{a_0}.
> $$
>
> Then $$\phi_m$$ is a ring homomorphism, called **reduction modulo $$m$$**.

### Theorem (irreducible or not)
> If $$\bar{f}(x)$$ is irreducible over $$\mathbb{Z}_p$$, then $$f(x)$$ is irreducible over $$\mathbb{Q}$$. However, even if $$\bar{f}(x)$$ is reducible over $$\mathbb{Z}_p$$, $$f(x)$$ may still be **irreducible** over $$\mathbb{Q}$$.

### Theorem (Eisenstein criterion)
> For a polynomial $$f(x) = a_nx^n+\cdots+a_0\in \mathbb{Z}[x]$$. Suppose there exists a prime $$p$$ such that
>
> - $$a_n \not \equiv 0 \text{ mod } p$$;
> - $$a_i \equiv 0 \text { mod } p,\ \forall 0\le i <n$$;
> - $$a_0 \not \equiv 0\text { mod } p^2$$.
>
> Then $$f(x)$$ is irreducible over $$\mathbb{Q}$$.

存在一個 $$p$$ 就夠了。雖然這個方法可以方便建構 irreducible polynomials，但是只能驗證特定的 polynomial。

> 注意 $$a_0 \not\equiv 0 \pmod{p^2}$$ 但 $$a_0 \equiv 0 \pmod p$$！

**Example**

$$x^2-2$$ is irreducible over $$\mathbb{Q}$$ by the Eisenstein criterion for $$p=2$$. This show that $$\sqrt{2}$$ is an *irrational* number.

**Proof**

Proof by contradiction, along with Gauss's Lemma.

### Remark

Over a finite field, verifying a given polynomial is irreducible or not is easy, but there is no general method to construct an irreducible polynomial of given degree.

Over $$\mathbb{Q}$$, construct (with Eisenstein criterion) is easier than verifying.

### Corollary (p-th cyclotomic polynomial)
> Let $$p$$ be a prime, Then the polynomial
>
> $$
> \Phi_p(x)=x^{p-1}+\cdots+x_1+1 = {x^p - 1\over x-1}
> $$
>
> is **irreducible** over $$\mathbb{Q}$$.

#### Remark

- $$\Phi_p(x)$$ is called the **p-th cyclotomic polynomial**.

- Let $$\zeta=e^{2\pi i\over p}$$, then $$\zeta^p = e^{2\pi i} = 1$$, which means that $$\zeta$$ is a zero of $$x^p-1$$. Moreover, $$\zeta,\zeta^2,\cdots,\zeta^p $$ are distinct zeros of $$x^p-1$$. Hence,

$$
x^p-1 = \prod^p_{k=1}(x-\zeta^k).
$$

**Proof**

A polynomial $$f(x) \in \mathbb{F}[x]$$ is irreducible over $$\mathbb{F}$$ iff $$f(x+1)$$ is irreducible over $$\mathbb{F}$$. Thus, it suffices to prove that $$\Phi_p(x+1)$$ is irreducible over $$\mathbb{Q}$$.

We have 

$$
\Phi_p(x+1) = {(x+1)^p-1\over x},
$$

where

$$
(x+1)^p-1 = x^p + {p\choose 1}x^{p-1}+\cdots+px.
$$

Hence, 

$$
\Phi_p(x+1) = x^{p-1} + {p\choose 1}x^{p-2}+\cdots+p.
$$

By [Eisenstein criterion](#theorem-eisenstein-criterion), $$\Phi_p(x)$$ is irreducible over $$\mathbb{Q}$$. ◼

> $$f(x+1)$$ 平移！

### More on cyclotomic polynomials
> 中文稱為分圓多項式。

In general, **$$n$$-th cyclotomic polynomial** is defined to be

$$
\Phi_p(x) = \prod_{0\le k\le n-1 \\ \gcd(k,n)=1}(x-\zeta^k_n) = \prod_{\ \ \ \ a\in\mathbb{C}^\times \\ \text{ord}(a) = n} (x-a)
$$

where $$\zeta_n = e^{2\pi i\over n}$$. For example, we have

$$
\begin{align*}
  \Phi_1(x) &= x - \zeta_1 = x-1 \\
  \Phi_2(x) &= x - \zeta_2 = x+1 \\
  \Phi_3(x) &= (x-\zeta_3)(x-\zeta^2_3) = x^2+x+1 \\
  \Phi_4(x) &= (x-\zeta_4)(x-\zeta^3_4) = x^2+1 \\
\end{align*}
$$

Observe that 

$$
x^n-1 = \prod_{a\in\mathbb{C}^\times \\ a^n=1} (x-a) = \prod_{d\vert n}\prod_{a\in\mathbb{C}^\times \\ a^d=1}(x-a) = \prod_{d\vert n}\Phi_d(x).
$$

> 如果 $$a^d=1$$，$$a^n=(a^d)^{n/d}$$ 也會等於 $$1$$。

Therefore, we can compute $$\Phi_n$$ **inductively**; for instance we have

$$
\begin{align*}
\Phi_{10}(x) &= {x^{10}-1 \over \Phi_1(x)\Phi_2(x)\Phi_5(x)} \\
&= {x^{10}-1 \over (x-1)(x+1)(x^4+x^3+x^2+x+1)} \\
&= x^4-x^3+x^2-x+1.
\end{align*}
$$

> 如果 $$n$$ 是質數，可以直接列出其 $$p$$-th cyclotomic polynomial；如果 $$n$$ 是合數，就用上述方法遞迴求出，省去計算 $$\zeta$$。

Furthermore, we can show that $$\Phi_n(x)$$ is always a polynomial with **integer coefficients** for all $$n$$. We will argue by strong induction.

**Proof**

For $$n=1$$, we have $$\Phi_1(x)=x-1\in \mathbb{Z}[x]$$. Suppose that for all $$n\le m$$, $$\Phi_n(x)\in \mathbb{Z}[x]$$. Then for $$n=m+1$$, if $$m+1$$ is a prime, we are done by the definition of $$p$$-th cyclotomic polynomial. If not, by the above observation, we have

$$
\begin{align*}
f(x) = x^{m+1}-1 = \prod_{d\vert {m+1}}\Phi_d(x) &= \prod_{d\vert {(m+1)} \\ d\not= m+1}\Phi_d(x)\cdot \Phi_{m+1}(x) \\
&= g(x)\cdot\Phi_{m+1}(x).
\end{align*}
$$

By induction hypothesis, $$g(x)$$ is an integer polynomial, which means that $$\Phi_{m+1}(x)\in \mathbb{Q}[x]$$. Then by Gauss's Lemma, there exist some $$a\in \mathbb{Q}^\times$$ such that $$ag(x)$$ and $$a^{-1}\Phi_{m+1}(x)$$ are both integr polynomials. However, since $$g(x)$$ is already an integer polynomial and its leading coefficient is $$1$$, $$a$$ must be an integer. If $$\Phi_{m+1}(x)$$ is an integer polynomial after divided by $$a$$, it must also be one before being divided. Thus $$\Phi_{m+1}(x) \in \mathbb{Z}[x]$$. ◼

> 其實 $$g(x)$$ 是 *primitive*。

#### Facts

By the way, we know that

$$
\langle \zeta_n \rangle \cong \mathbb{Z}_n,
$$

and 

$$
\langle \zeta_n^k \rangle \cong \langle \zeta_n \rangle \iff \gcd(k,n)=1.
$$

> 見 [cyclic subgroups](../Cyclic-Subgroups)。

---

## Unique Factorization
### Basics
#### Definition (divisor)
> Let the set of divisors of $$f(x)$$ to be 
>
> $$
> D(f) = \{h(x)\in \mathbb{F}[x]: h(x)\vert f(x) \}.
> $$

#### Lemma (irreducible)
> When $$f(x)$$ is irreducible, then $$D(f) = \mathbb{F}^\times \cup \mathbb{F}^\times f(x)$$.

#### Definition (common divisor)
> Let set of common divisors of $$f$$ and $$g$$ be
>
> $$
> CD(f,g)=D(f)\cap D(g),
> $$
>
> which always contains $$\mathbb{F}^\times$$.

#### Definition (gcd)
> A polynomial $$h_0(x)$$ is called a **gcd** of $$f(x)$$ and $$g(x)$$ if 
>
> - $$h_0(x)\in CD(f,g)$$ and 
> - $$\deg h_0(x) \ge \deg h(x),\ \forall h(x)\in CD(f,g)$$.
>
> We say **gcd** is **unique up to units**.

> 因為 units 就是 non-zero constants $$c$$，而乘不乘 $$c$$ 都無所謂。

#### Theorem (Euclidean algorithm)
> For a **gcd** $$h(x)$$ of $$f(x)$$ and $$g(x)$$ (both are non-zero) in $$\mathbb{F}[x]$$, there exists $$a(x)$$ and $$b(x)$$ in $$\mathbb{F}[x]$$ such that 
>
> $$
> a(x)f(x) + b(x)g(x) = h(x).
> $$

### Irreducible polynomials
#### Theorem (like prime)
> Let $$p(x)$$ be an *irreducible* polynomial in $$\mathbb{F}[x]$$. If $$p(x)\vert r(x)s(x) $$ for $$r(x),s(x) \in \mathbb{F}[x]$$, then **$$p(x)\vert r(x)$$ or $$p(x)\vert s(x)$$ in $$\mathbb{F}[x]$$**.

**Proof**

Use [Euclidean algorithm](#theorem-euclidean-algorithm) to prove this. Or use the concept of [prime ideals](../more-on-ideals/#theorem-irreducible-prime).

#### Theorem (unique factorization)
> *Every nonconstant polynomial* $$f(x) \in \mathbb{F}[x]$$ can be factored in $$\mathbb{F}[x]$$ into a **product of irreducible polynomials**. The factorization is *unique upto order and units*.

> *upto order* 代表交換 factor 的順序後還是同一種。

> 這是 The Fundamental Theorem of Arithmetic 的推廣！

**Proof**

- Existence

By induction on degree.

- Uniqueness

Assum that $$f(x) = p_1(x)\cdots p_r(x) = q_1(x)\cdots q_s(x)$$, i.e. there are two factorizations of $$f(x)$$ into a product of irreducible polynomials. 

By [this theorem](#theorem-like-prime), $$p_1(x)$$ divides one of $$q_i(x)$$. After rearranging the indices, we assume that $$p_1(x)\vert q_1(x)$$. Since $$q_1(x)$$ is irreducible, it can be written as

$$
q_1(x) = u_1p_1(x),
$$

where $$u_1$$ is a constant in $$\mathbb{F}[x]$$. Then we have

$$
p_1(x)\cdots p_r(x) = (u_1p_1(x))q_2(x)\cdots q_s(x).
$$

Canceling $$p_1(x)$$, we get $$p_2(x)\cdots p_r(x) = u_1q_2(x)\cdots q_s(x)$$. Repeating the above procedure, we can eventually obtain that the two factorizations are exactly equal. ◼

#### Theorem (irreducibility and square)
> Let $$F=\Bbb Z_p(\alpha) $$, where $$\alpha$$ is a zero of $$f(x) = x^2+ax+b$$ in $$\overline{\Bbb Z}_p$$, and $$p$$ is a prime. Then $$f(x^2) = x^4+ax^2+b$$ is reducible over $$\Bbb Z_p$$ iff $$\alpha$$ is a square in $$F$$.

**Proof**

If $$\alpha$$ is a square in $$F$$, then for $$\beta^2=\alpha$$, $$\beta \in F$$. Suppose for contradiction that $$f(x^2)$$ is irreducible over $$\Bbb Z_p$$. Since $$f(\alpha) = 0$$, $$f(\beta^2) = \beta^4 + a\beta^2 + b = 0$$, which implies that $$\deg(\beta, \Bbb Z_p) = 4$$. However, since $$\beta \in F$$ and $$\deg(\alpha, \Bbb Z_p)$$ is only $$2$$, we have a contradiction. Therefore, $$f(x^2)$$ is reducible.

Now if $$\alpha$$ is not a square in $$F$$, then for $$\beta^2=\alpha$$, $$\beta \not\in F$$. Suppose for contradiction that $$f(x^2)$$ is reducible over $$\Bbb Z_p$$. Again, $$f(\beta^2) = 0$$ and since $$f(x^2)$$ is reducible, $$\beta$$ is also a zero of some quadratic polynomial over $$\Bbb Z_p$$, say $$x^2+cx+d$$. Then,

$$
\begin{align*}
&\beta^2 = \alpha = -c\beta-d, \\
\implies &\beta = (-c)^{-1}(\alpha + d) \in F,  
\end{align*}
$$

which is a contradiction. Therefore $$f(x^2)$$ must be irreducible. ◼

---

## Ring of Residue Classes
### Definition (ring of residue classes)

Let $$f(x)$$ be a non-constant polynomial in $$\mathbb{F}[x]$$ where $$\mathbb{F}$$ is a field. For $$g(x),h(x)\in \mathbb{F}[x]$$, we say $$g(x)$$ and $$h(x)$$ are in the same residue class modulo $$f(x)$$, denoted by

$$
g(x)\equiv h(x) \text{ mod }  f(x),
$$

if $$f(x)$$ divides $$g(x)-h(x)$$. This defines a **eqivalence relation**. Denote the residue class of $$g(x)$$ by $$\overline{g(x)}$$, which is equal to

$$
g(x) + f(x)\mathbb{F}[x].
$$

Then we have the well-defined binary operation on the residue classes:

$$
\overline{g(x)} + \overline{h(x)} := \overline{g(x)+h(x)}; \\
\overline{g(x)} \cdot \overline{h(x)} := \overline{g(x)\cdot h(x)}. \\
$$

Under the two binary operations, the residue classes modulo $$f(x)$$ forms a **ring**, denoted by **$$\mathbb{F}[x]/f\mathbb{F}[x]$$**, which is always a **commutative ring** with **unity**.

> $$\mathbb{F}[x]/f\mathbb{F}[x]$$ 是所有除以 $$f(x)$$ 的**餘式**的集合。

### Theorem (irreducible and field)
> A polynomial $$f(x)$$ is **irreducible** over $$\mathbb{F}[x]$$ iff $$\mathbb{F}[x]/f\mathbb{F}[x]$$ is a **field**.

有點像是：

> An integer $$p>1$$ is prime iff $$\mathbb{Z}_p^\times \cong \mathbb{Z}_{p-1}$$

**Proof**

$$(\Rightarrow)$$:

- Suppose $$\mathbb{F}[x]$$ iff $$\mathbb{F}[x]/f\mathbb{F}[x]$$ is a field. 
- Suppose $$f(x) = g(x)h(x)$$.
- no zero divisor

$$(\Leftarrow)$$:

- Suppose $$f(x)$$ is irreducible.
- Find the inverse for everyone.
- [Euclidean algorithm](#theorem-euclidean-algorithm)

### Example

In $$\mathbb{Z}_2[x]$$, let $$f(x) = x^2 + x + 1$$. Since $$f(0) = f(1) = 1$$, $$f(x)$$ is irreducible. Then by the above theorem, we have

$$
\mathbb{Z}_2[x]\Big/f\mathbb{Z}_2[x] = \{\bar 0, \bar 1, \bar x, \overline{x+1}  \} = F_4,
$$

which is a field with four elements.

As an additive group, $$F_4 \cong \mathbb{Z}_2 \times \mathbb{Z}_2$$. As a multiplicative group, $$F_4 \cong \langle \bar x \rangle \cong \mathbb{Z}_3$$.

> $${\bar x}^2 = \overline{x^2} = \overline{-x-1} = \overline{x+1}$$. (In $$\mathbb{Z}_2$$, $$-1 = 1$$.)

### Remark

Suppose $$\deg{f}(x) = n$$. We have

$$
\Big\vert \mathbb{Z}_p[x] \big/ f\mathbb{Z}_p[x]\Big\vert = p^n.
$$

This is because all the elements in $$\mathbb{Z}_p[x] \big/ f\mathbb{Z}_p[x]$$ must be of the form:

$$
a_{n-1}x^{n-1}+\cdots+a_0,
$$

where $$a_i \in \mathbb{Z}_p$$. Hence there are $$p$$ choices for each $$a_i$$.

### Question ($$x^4+1$$)

**Q1:**

> Is $$x^4 + 1$$ reducible over $$\mathbb{Q}[x]$$?

**A1:**

No, just use [Eisenstein criterion](#theorem-eisenstein-criterion) for $$p=2$$.

**Q2:**

> Is $$x^4+1$$ reducible over $$\mathbb{Z}_p[x]$$ for all primes $$p$$?

**A2:**

Yes. Suppose 

$$
\begin{align*}
f(x) = x^4+1 &= (x^2+ax+b)(x^2+cx+d) \\
&= x^4 + (a+c)x^3 + (ac+b+d)x^2 + (ad+bc)x + bd.
\end{align*}
$$ 

Then we have

$$
\begin{cases}
  a \equiv -c, \\
  ac + b + d \equiv 0, \\
  ad + bc \equiv 0,\\
  b = d^{-1}.
\end{cases}
$$

If $$a\equiv c \equiv 0$$, $$d+d^{-1}\equiv 0$$, which means that $$d^2 \equiv -1$$. If not, we have $$d\equiv d^{-1}$$, which implies $$d\equiv \pm 1$$, and thus $$a^2\equiv \mp 2$$. To sum up, $$f(x)$$ is reducible over $$\mathbb{Z}_p[x]$$ if at least one of $$-2, -1$$ and $$2$$ is a [quadratic residue modulo $$p$$](https://brilliant.org/wiki/quadratic-residues/).

If $$d^2 \equiv -1$$, we have 

$$
\begin{align*}
  x^4 + 1 = x^4 - d^2 = (x^2+d)(x^2-d).
\end{align*}
$$

If $$a^2 \equiv 2$$, we have

$$
x^4+1 = (x^2+1)^2 - (ax)^2 = (x^2-ax+1)(x^2+ax+1).
$$

If neither $$-1$$ nor $$2$$ is a quadratic residue, then their product $$-2$$ must be one, since 

$$
\Big({ab\over p} \Big) = \Big({a\over p} \Big)\Big({b\over p} \Big).
$$

Thus $$f(x)$$ must be reducible over $$\mathbb{Z}_p[x]$$ for all primes $$p$$. ◼

> $$(-1)(-1) = 1$$. See **Legendre symbol**.

---

## Reference

- [Quadratic Residue](https://brilliant.org/wiki/quadratic-residues/)
- [Legendre Symbol](https://brilliant.org/wiki/legendre-symbol/)
- [Law of Quadratic Reciprocity](https://brilliant.org/wiki/law-of-quadratic-reciprocity/)
- [StackExchange](https://math.stackexchange.com/questions/77155/irreducible-polynomial-which-is-reducible-modulo-every-prime)