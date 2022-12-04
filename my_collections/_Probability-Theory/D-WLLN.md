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
  - [Example](#example)
- [Weak Law of Large Numbers (WLLN)](#weak-law-of-large-numbers-wlln)
- [Convergence](#convergence)
  - [Definition (convergence in probability)](#definition-convergence-in-probability)
  - [Properties](#properties)
  - [Reamrk](#reamrk)
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

Assume there is an event $$A$$ with $$p=P(A)$$. Let $$X_i$$ be the indicator of the evnet $$A$$, i.e., $$X_i=1$$ if $$A$$ occurs, otherwise $$X_i=0$$; the mean of $$X_i$$ equals to $$p$$. Then the **sample mean** $$M_n$$ now becomes the **empirical frequency** of the event $$A$$, since $$M_n$$ counts how many times that $$A$$ happened on average. By **WLLN**, we can see that $$P\big(\vert M_n-p\vert \ge \epsilon \big) \rightarrow 0$$ as $$n\rightarrow \infty$$, which means that **probability can be regarded as frequency** when experiments are conducted for a large number of times.

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
E[g(X)] \le g(E[X]).
$$

This is what we want. The proof is similar for the concave case. ◼

### Hoeffiding's inequality
> 待補。


---

## Reference
- [MIT OCW](https://ocw.mit.edu/courses/res-6-012-introduction-to-probability-spring-2018/pages/part-ii-inference-limit-theorems/)
