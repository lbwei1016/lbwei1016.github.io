---
layout: page
title: Weak Law of Large Numbers
usemathjax: true
tag: Probability
time: 2022/11/29
---

**Table of Content**
- [Some Inequalities](#some-inequalities)
  - [Markov inequality](#markov-inequality)
  - [Chebyshev inequality](#chebyshev-inequality)
    - [Remark](#remark)
  - [Example](#example)
- [Weak Law of Large Numbers (WLLN)](#weak-law-of-large-numbers-wlln)
- [Convergence](#convergence)
  - [Definition (convergence in probability)](#definition-convergence-in-probability)
  - [Properties](#properties)
  - [Reamrk](#reamrk)
  - [Exercise](#exercise)
- [More Inequalities](#more-inequalities)
  - [Jensen's inequality](#jensens-inequality)
  - [Hoeffiding's inequality](#hoeffidings-inequality)
- [Reference](#reference)

---

## Some Inequalities

### Markov inequality
> If $$X \ge 0$$ and $$a>0$$, then 
> 
> $$P(X\ge a)\le {E[X] \over a}.$$

**Proof**

$$
E[X] = \int_0^\infty xf_X(x)dx \ge \int_a^\infty xf_X(x)dx \ge \int_a^\infty af_X(x)dx = aP(X\ge a). ◼
$$

> *If $$X\ge 0$$ and $$E[X]$$ is small, then $$X$$ is unlikely to be very large.*

### Chebyshev inequality
> For a r.v. $$X$$ with finite mean $$\mu$$ and variance $$\sigma^2$$, we have
>
> $$
> P\big(\vert X-\mu\vert \ge c\big) \le {\sigma^2\over c^2}.
> $$

**Proof**

$$
P\big(\vert X-\mu\vert \ge c \big) = P\big((X-\mu)^2 \ge c^2 \big) \le {E[(X-\mu)^2] \over c^2} = {\sigma^2\over c^2}, 
$$

with the help of the Markov inequality. ◼

#### Remark

When $$X$$ is known to take values in a range $$[a, b]$$, we claim that **$$\sigma^2 \le (b-a)^2/4$$**. We can use this bound when $$\sigma^2$$ is unknown.

The equality $$\sigma^2 = (b-a)^2/4$$ is satisfied when $$X$$ only takes two extreme values $$a$$ and $$b$$, with equal probability $$1/2$$.

### Example

Let $$X$$ be an exponential r.v. with parameter $$\lambda=1$$; we have $$E[X] = {1\over \lambda} = 1$$ and $$var(X)={1\over \lambda^2} = 1$$. By the Markov inequality, 

$$
P(X\ge a) \le {1\over a},
$$

and by the Chebyshev inequality

$$
P(X\ge a ) = P(X-1 \ge a-1) \le P(\vert X-1\vert \ge a-1) \le {1\over (a-1)^2} \approx {1\over a^2}.
$$

We can see that the latter has a tighter bound.

> 其實 $$P(X\ge a) = e^{-\lambda a} = e^{-a}$$！（見 [Continous Random Variables](../4-continous-rv/#exponential-random-variable)。）

---

## Weak Law of Large Numbers (WLLN)

Let $$X_1,\cdots,X_n$$ be *identical independently distributed* r.v.s with finite mean $$\mu$$ and variance $$\sigma^2$$. Then we define the **sample mean** as

$$
M_n = {X_1+\cdots+X_n\over n},
$$

which is a *random variable*. Further, we have

$$
E[M_n] = {E[{X_1+\cdots+X_n}]\over n} = {n\mu\over n} = \mu, \\
var(M_n) = {var(X_1+\cdots+X_n)\over n^2} = {n\sigma^2\over n^2} = {\sigma^2\over n}.
$$

By the Chebyshev inequality, we have

$$
P\big(\vert M_n-\mu\vert \ge \epsilon \big) \le {var(M_n)\over \epsilon^2} = {\sigma^2\over n\epsilon^2}.
$$

Now we can state the **WLLN**:

>For $$\epsilon > 0$$, $$P\big(\vert M_n-\mu\vert \ge \epsilon \big) \rightarrow 0$$ as $$n\rightarrow \infty$$.

> sample mean 趨近真正的 mean！

Assume there is an event $$A$$ with $$p=P(A)$$. Let $$X_i$$ be the indicator of the evnet $$A$$, i.e., $$X_i=1$$ if $$A$$ occurs, otherwise $$X_i=0$$; the mean of $$X_i$$ equals to $$p$$. Then the **sample mean** $$M_n$$ now becomes the **empirical frequency** of the event $$A$$, since $$M_n$$ counts how many times that $$A$$ happened on average. By **WLLN**, we can see that $$P\big(\vert M_n-p\vert \ge \epsilon \big) \to 0$$ as $$n\to \infty$$, which means that **probability can be regarded as frequency** when experiments are conducted for a large number of times.

By the way, in this case we can show that 

$$
P\big(\vert M_n-p\vert \ge \epsilon \big) \le {p(1-p)\over n\epsilon^2} \le {1\over 4n\epsilon^2},
$$

since $$p(1-p) \le 1/4$$. 

---

## Convergence
### Definition (convergence in probability)
> A sequence of r.v.s $$Y_n$$ **converges in probability** to a number $$a$$ if for any $$\epsilon > 0 $$, 
>
> $$\lim_{n\to\infty} P\big(\vert Y_n-a\vert \ge \epsilon \big)=0.$$
>
> Note that $$Y_n$$s need not be independent. 

> $$Y_n$$ 的 PDF/PMF 最終凝聚在 $$a$$；$$Y_n\to a$$。

### Properties

Suppose $$X_n\to a$$ and $$Y_n\to b$$ in probability. Then 

$$
X_n+Y_n \to a+b.
$$

And if $$g$$ is continuous, we have

$$
g(X_n) = g(a).
$$

However, $$E[X_n]$$ **need not** converge to $$a$$.

> 因為 $$E[X_n]$$ 容易讓大的值壓過小的機率，而跑到無限去了；$$X_n$$ 的收斂只要機率夠小就好。

### Reamrk

- 要知道 $$X_n$$ 收斂到哪裡，就是先猜然後驗證；注意要考量到 $$P(X_n) = 0$$ 的地方。

- $$M_n$$ converges to $$\mu$$.

### Exercise

> Let $$X_1, X_2\cdots$$ be independent r.v.s that are uniformly distributed over $$[-1, 1]$$. Show that the sequence $$Y_1, Y_2, \cdots$$ converges in probability to some limit.

> From Introduction to Probability (bertsekas, 2nd, 2008), problem 5.5.

1. $$Y_n = (X_n)^n$$,
2. $$Y_n = X_1\cdots X_n$$,
3. $$Y_n = \text{max}(X_1, \cdots, X_n)$$.

**Solution**

**1.**

First guess that $$Y_n$$ converges to $$0$$. For all $$\epsilon \in (0, 1)$$, we have

$$
\begin{align*}
\mathbf{P}\big(\vert Y_n\vert\ge \epsilon \big) &= \mathbf{P}\big(\vert X_n\vert^n \ge \epsilon \big) \\
&= \mathbf{P}\big(X_n\ge \epsilon^{1/n} \big) + \mathbf{P}\big(X_n\le -\epsilon^{1/n} \big) \\
&= {1\over 2}\big[(1-\epsilon^{1/n}) + (-\epsilon^{1/n}-(-1)) \big] \\
&= 1 - \epsilon^{1/n},
\end{align*}
$$

which converges to $$0$$.

**2.**

Since all $$X_i$$ are independent, we have 

$$
E[Y_n] = E[X_1]\cdots E[X_n] = 0.
$$

Also

$$
var(Y_n) = E[Y_n^2] = E[X_1^2]\cdots E[X_n^2] = var(X_1)^n = ({4\over 12})^n,
$$

and hence $$var(Y_n)\to 0$$. Then by [Chebyshev's inequality](#chebyshev-inequality), we have

$$
\mathbf{P}(\vert Y_n-0\vert \ge \epsilon) \le ({4\over 12})^n \cdot {1\over \epsilon^2}, 
$$

and thus $$Y_n$$ converges to $$0$$.

**3.**

First guess that $$Y_n$$ converges to $$1$$. Then

$$
\begin{align*}
\mathbf{P}\big(\vert\text{max}(X_1, \cdots, X_n)-1\vert \ge \epsilon\big) &= \mathbf{P}\big(1-\text{max}(X_1, \cdots, X_n) \ge \epsilon\big) \\
&= \mathbf{P}\big(\text{max}(X_1, \cdots, X_n) \le 1-\epsilon\big) \\
&= \prod_{i=1}^n \mathbf{P}(X_i\le 1-\epsilon) \\
&= \Big(\int_{-1}^{1-\epsilon}{1\over 2}dx\Big)^n \\
&= (1-\epsilon/2)^n,
\end{align*}
$$

which converges to $$0$$. ◼

---

## More Inequalities
### Jensen's inequality
> If $$g$$ is **convex**, then $$g(E[X])\le E[g(X)]$$. On the other hand, if $$g$$ is **concave**, then $$g(E[X])\ge E[g(X)]$$. 

**Proof**

If $$g$$ is convex, then by the definition of convexity, we have

$$
g(x) \ge g(c) + g'(c)(x-c),
$$

for all $$c$$ such that $$g'(c)$$ is defined. We now substitute $$E[X]$$ for $$c$$, and take the expectation of both sides, yielding

$$
E[g(X)] \ge g(E[X]).
$$

This is what we want. The proof is similar for the concave case. ◼

### Hoeffiding's inequality
> 待補。


---

## Reference
- [MIT OCW](https://ocw.mit.edu/courses/res-6-012-introduction-to-probability-spring-2018/pages/part-ii-inference-limit-theorems/)
