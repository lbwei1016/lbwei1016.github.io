---
layout: page
title: Classical Statistics
usemathjax: true
tag: Probability, Statistics
time: 2022/12/27
---

**Table of Content**


---

## Motivation

未知是**常數**，而非隨機變數；$$p_X(x; \theta)$$。

---

## Estimator

Let $$\theta$$ be the unknown value of interest, and let $$\widehat \Theta_n$$ be an estimator. If 

$$
E[\widehat \Theta_n] = \theta,
$$

then we say $$\widehat \Theta_n$$ is **unbiased**; if by the [Weak Law of Large Number](../D-WLLN),

$$
\widehat \Theta_n \to \theta,
$$

then we say $$\widehat \Theta_n$$ is **consistent**.

> 當 $$\widehat \Theta_n$$ 是 sample mean，上述兩性質都符合！

> Here, **bias** represents $$E[\widehat \Theta_n-\theta]$$.

---

## Confidence Intervals (CIs)

### Definition (CI)
> An $$1-\alpha$$ **confidence interval** is an interval $$[\widehat\Theta_n^{-}, \widehat\Theta_n^{+}]$$, such twidehat for all $$\theta$$,
>
> $$
> P(\widehat\Theta_n^{-} \le \theta \le \widehat\Theta_n^{+}) \ge 1-\alpha
> $$

### Remark

$$\widehat\Theta^{-}$$ 和 $$\widehat\Theta^{+}$$ 都是 r.v.，不能將他們替換成常數，如 $$0.12, 0.25$$，否則沒有隨機性何來機率？

Confidence interval 的意義是：根據 $$n$$ 次觀測，我們得到兩隨機變數，$$\widehat\Theta_n^{-}$$ 與 $$\widehat\Theta_n^{+}$$；而實際值 $$\theta$$ 落在信賴區間 $$[\widehat\Theta_n^{-}, \widehat\Theta_n^{+}]$$，也就是 confidence interval 之中的機率是 $$1-\alpha$$。

### CI estimation

By [CLT](../E-clt)，we can obtain

$$
P\Big({\widehat\Theta_n  \theta \over \sigma/\sqrt{n} } \le 1.96\Big) \approx 0.95;
$$

after repharsing, we have

$$
P\Big(\widehat\Theta_n - {1.96\sigma\over\sqrt{n}} \le \theta \le \widehat\Theta_n + {1.96\sigma\over\sqrt{n}} \Big) \approx 0.95.
$$

If the variance $$\sigma^2 = E[(X_i - \theta^2)] $$ is unknown, we can approximate it by sample mean, according to the [WLLN](../D-WLLN), i.e.

$$
{1\over n}\sum^n_{i=1}(X_i-\theta)^2 \to E[(X_i - \theta^2)] = \sigma^2.
$$

However, $$\theta$$ is also unknown. To approximate it, we use our estimator:

$$
{1\over n}\sum^n_{i=1}(X_i-\widehat\Theta_n)^2 \to \sigma^2,
$$

by the fact that $$\widehat\Theta_n \to \theta$$ when $$n$$ is large. 

#### Remark

$$
Z = {1\over n-1}\sum^n_{i=1}(X_i-\widehat\Theta_n)^2
$$

is an **unbiased** random variable of $$\sigma^2$$. Below is the proof.

$$
\begin{align*}
  &E\Big[\sum^n_{i=1}(X_i-\widehat\Theta_n)^2\Big] \\
=\ &\sum^n_{i=1}E\Big[(X_i-\widehat\Theta_n)^2\Big] \\
=\ &{1\over n}E\Big[\big((X_2+\cdots+X_n\big) - (n-1)X_1)^2\Big] \\
=\ &{1\over n}\Big[(n-1)E(X_1^2) - (n-1)(n-2)E(X_1)^2 + (n-1)^2E(X_1^2) - 2(n-1)^2 E(X_1)^2\Big] \\
=\ &(n-1)\sigma^2. 
\end{align*}
$$

Divide it by $$(n-1)$$ would yield the result. ◼

---

## Maximum Likelihood Estimation

$$
\hat\theta_{ML} = \arg \max_\theta p_X(x; \theta).
$$