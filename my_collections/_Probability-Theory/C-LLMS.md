---
layout: page
title: Linear LMS
usemathjax: true
tag: Probability
time: 2022/11/29
---

**Table of Content**
- [Motivation](#motivation)
- [Solve the LLMS problem](#solve-the-llms-problem)
  - [**Remark**](#remark)
  - [Exercise](#exercise)
- [Different Data Represnetations](#different-data-represnetations)
- [Reference](#reference)

---

## Motivation

因為 **LMS** 可能不好解，所以用 **LLMS** 找近似最佳解。

---

## Solve the LLMS problem

> $$\Theta$$ 是 prior、$$X$$ 是 observation。 

我們的 estimator 是線性的，即 $$\hat \Theta = aX+b$$。所以要最小化的目標是 $$ E\big[(\Theta-aX-b)^2 \big]$$。

假設 $$a$$ 已知，我們可以將 $$\Theta-aX$$ 視為一全新的 r.v. $$Y$$；使 $$E\big[(Y-b)^2 \big]$$ [最小化的 $$b$$ 正是 $$E[Y]$$](../B-LMS-revisited/#mean-squared-error-mse) 。於是 $$b = E[\Theta - aX]$$。

現在只剩下一個變數要處理了！我們要最小化的目標變成

$$
\begin{align*}
E\big[(\Theta-aX-E[\Theta-aX])^2 \big] &= var(\Theta-aX) \\
&= var(\Theta) + a^2var(X) - 2a\cdot cov(\Theta, X)。
\end{align*}
$$

這是 $$a$$ 的二次函數；因為 $$var(X)$$ 恆正（設非零），所以對此微分可以得到最小值所在，也就是

$$
a = {cov(\Theta, X)\over var(X)}。
$$

總結以上，

$$
\begin{align*}
\hat \Theta_L &= aX+b \\
&= E[\Theta] + {cov(\Theta, X)\over var(X)}(X-E[X]) \\
&= E[\Theta] + \rho{\sigma_{\Theta}\over \sigma_X}(X-E[X])。
\end{align*}
$$

### **Remark**

相較於 LMS 的 $$\hat \Theta = E[\Theta\vert X]$$，$$\hat \Theta_L$$ 只和 **means, variances**, and **covariance** 有關，代表我們不需要知道全部有關 $$\Theta$$ 和 $$X$$ 的 distribution 資訊。這是很好的性質！

> 也就是說，對於兩組隨機變數 $$\Theta_1, X_1$$ 和 $$\Theta_2, X_2$$，只要兩兩對應的 **mean, variance**, and **covariance** 都相等，則 $$\hat \Theta_{L, 1} = \hat \Theta_{L, 2}$$！$$\Theta_1, X_1, \Theta_2, X_2$$ 是什麼 distribution 不重要！

關於 performance，

$$
E\big[(\hat\Theta_L - \Theta)^2 \big] = (1-\rho^2)var(\Theta)。
$$

可以先假設 $$E[\Theta]=E[X]=0$$，再將等式左邊依定義展開，即可得到等式右邊。由此可見，$$\rho$$ 在 **LLMS** 中扮演重要的角色：不僅影響 estimator，也牽動著誤差。

### Exercise

> [MIT OCW](https://ocw.mit.edu/courses/res-6-012-introduction-to-probability-spring-2018/resources/llms-for-inferring-the-parameter-of-a-coin/).

---

## Different Data Represnetations

In LMS, $$E[\Theta\vert X]$$ is the same as $$E[\Theta\vert X^3]$$.

> I suspect that once $$g(X)$$ is *one-to-one and onto*, $$E[\Theta\vert X] = E[\Theta\vert g(X)]$$, but it is **not** proved yet.

However, in LLMS, estimator $$\hat \Theta=aX+b$$ is different from estimator $$\hat \Theta=aX^3+b$$. Which is the better one? That depends on the problem we are solving.

Moreover, we can even consider $$\hat \Theta=a_1X+a_2X^2+a_3X^3+b$$. Although the functions of $$X$$ appeared are not necessarily *linear*, the **coefficients are linear**, and that's pretty enough. After all, when dealing with LLMS, we solve *a system of linear equations* of the **coefficients**, not $$X$$s. To generalize, we can apply the methodology of LLMS for estimators of the form:

$$
\hat \Theta_L = b + \sum_{i=1}^na_ig_i(X),
$$

where $$g_i(X)$$ can be any well-defined function.

> 越複雜的 estimator 越難計算，但或許效果比較好，視問題而定。

---

## Reference
- [MIT OCW](https://ocw.mit.edu/courses/res-6-012-introduction-to-probability-spring-2018/pages/part-ii-inference-limit-theorems/)