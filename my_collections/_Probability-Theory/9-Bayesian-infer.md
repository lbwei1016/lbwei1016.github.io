---
layout: page
title: Bayesian Inference
usemathjax: true
tag: Probability
time: 2022/11/18
---

**Table of Content**
- [Introduction](#introduction)
- [Bayesian Inference](#bayesian-inference)
  - [Framework](#framework)
  - [MAP (Maximum a posteriori probability)](#map-maximum-a-posteriori-probability)
  - [LMS (Least Mean Squares)](#lms-least-mean-squares)
- [Beta Distribution](#beta-distribution)
  - [Properties](#properties)
    - [Integration (beta function)](#integration-beta-function)
    - [Remark](#remark)
- [Reference](#reference)

---

## Introduction

假設現在有一訊號 $$S$$，經過介質 $$a$$ 減弱後，再經過 uniform 雜訊 $$W$$ 干擾，最終我們觀測到 $$X$$；以上過程可以以一方程式表示

$$
X=aS+W。
$$

假如介質 $$a$$ 是未知的，我們可以「人工」發送訊號 $$S$$，並藉由觀察到的 $$X$$ 來推論 $$a$$；這過程稱為 **model building**。

現在我們已經知道介質 $$a$$ 了，於是可以用剛剛得到 model 來推論我們感興趣的「未知」訊號 $$S$$；這稱為 **variable estimation**。

除了 **estimation** 之外，還有另一類 inference 稱為 **hypothesis testing**：未知變量有數種（有限個）可能的值，目標是最小化錯誤的抉擇。

---

## Bayesian Inference
### Framework

首先將我們感興趣的未知變量視為一隨機變數 $$\Theta$$（假設離散）；我們可以**任意地**決定其分布，即 *prior distribution* $$p_\Theta$$。

然後透過觀察，我們可以獲取一些資訊 $$X$$；因為 $$\Theta$$ 和 $$X$$ 相伴發生，所以我們可以得知 $$p_{X,\Theta}$$。又因為已經事先決定 prior distribution $$p_\Theta$$，因此 $$p_{X\vert\Theta}$$ 也是已知的資訊。

接著使用我們熟悉的 [Bayes' rule](../5-more-on-conditioning/#bayes-rule-revisted) 來獲得

$$
p_{\Theta\vert X}(\theta\vert X=x)，
$$

而這就是當我們觀察到 $$X=x$$ 時，對 $$\Theta=\theta$$ 的「信仰」。

> 關於 prior distribution 的問題，見[這裡](https://fukamilab.github.io/BIO202/05-B-Bayesian-priors.html)和[那裡](https://github.com/stan-dev/stan/wiki/Prior-Choice-Recommendations)。

有了這新資訊，我們就可以引入新方法：**MAP** 和 **LMS**。進入主題之前，先定義符號：

$$
\hat{\theta}=g(x) \text{: estimate}, \\
\hat{\Theta}=g(X) \text{: estimator}. 
$$

### MAP (Maximum a posteriori probability)

> Find a $$\theta$$ such that $$p_{\Theta\vert X}(\theta\vert x)$$ is maximized. Then the *estimator* $$\hat{\theta}$$ is equal to such $$\theta$$. 

> 即最小化錯誤。


### LMS (Least Mean Squares)

> $$\hat{\theta} = E\big[\Theta\vert X=x\big] $$.

> 上面是 *conditional mean*。見 [LMS revisted](../B-LMS-revisted) 。

藉由 **MAP**，我們可以得到最小的 *conditional prob. of error*

$$
P(\hat{\theta} \not = \Theta \vert X=x)，
$$

並更進一步得到最小的 *overall prob. of error*

$$
\begin{align*}
P(\hat{\Theta}\not = \Theta) &= \sum_x P(\hat{\Theta}\not = \Theta \vert X=x)p_X(x) \\
&= \sum_\theta P(\hat{\Theta}\not = \Theta \vert \Theta=\theta)p_\Theta(\theta)
\end{align*}
$$

也就是說，在 **hypothesis testing** 下，**MAP** 總是可以得到**最佳** estimate。至於 **LMS** 留待另外一篇再來說明。

> **MAP**: 觀察到 $$X=x$$ 後，猜 $$\Theta=\hat\theta_{MAP}$$ 是最佳的。

---

## Beta Distribution

Let $$X \sim \mathcal{Be}(\alpha, \beta) $$. Then 

$$
f_X(x) = {1\over B(\alpha, \beta)}x^{\alpha-1}(1-x)^{\beta-1},
$$

where $$B(\alpha, \beta)$$ is the [Beta function](https://en.wikipedia.org/wiki/Beta_function).

### Properties
#### Integration (beta function)
> $$\int_0^1x^\alpha x^{\beta}dx = {\alpha!\beta!\over (\alpha+\beta+1)!}, \alpha,\beta\ge 0.$$

**Proof** (flawed)

$$
\begin{align*}
\int_0^1x^\alpha(1-x)^\beta dx &= \int_0^1x^\alpha \sum_{k=0}^\beta {\beta\choose k}(-1)^{\beta-k}x^k dx \\
&= \int_0^1\sum_{k=0}^\beta {\beta\choose k}(-1)^{\beta-k}x^{\alpha+k} dx\\
\end{align*}
$$

Since 

$$
\lim_{\beta\to\infty} \sum_{k=0}^\beta {\beta\choose k}(-1)^{\beta-k}x^k = \lim_{\beta\to\infty}(1-x)^\beta =0,\ x \in [0, 1],
$$

the integral and the summation can interchange by [the dominated convergence theorem](https://math.stackexchange.com/q/3056731). Thus, we have

$$
\begin{align*}
\int_0^1\sum_{k=0}^\beta {\beta\choose k}(-1)^{\beta-k}x^{\alpha+k} dx &= \sum_{k=0}^\beta{\beta\choose k}(-1)^{\beta-k}\int_0^1 x^{\alpha+k}dx. \\
&= \sum_{k=0}^\beta{\beta\choose k}(-1)^{\beta-k}{1\over \alpha+1+k} \\
\end{align*}
$$

Reconginzing this [pattern](../../Concrete-Math/Binomial-Coefficient/#difference), we let $$f(x) = 1/(\alpha+1+x)$$, and we have

$$
\sum_{k=0}^\beta{\beta\choose k}(-1)^{\beta-k}{1\over \alpha+1+k} = \Delta^\beta f(0).
$$

After some observation, we derive that 

$$
\Delta^nf(x) = {(-1)^nn!\over (\alpha+n+1)^\underline{n+1}}.
$$

Therefore, our integral becomes

$$
\begin{align*}
\int_0^1x^\alpha (1-x)^\beta dx &= {(-1)^\beta \beta!\over (\alpha+\beta+1)^\underline{\beta+1}} \\
&= {(-1)^\beta \alpha! \beta!\over (\alpha+\beta+1)!},
\end{align*}
$$

which is a little bit weird since $$(-1)^\beta$$ shouldn't be there: Our integral is expected to be positive, for all $$\beta$$. This is the **flaw** mentioned. ◼

#### Remark

The proof above should be scrutinized. Besides the above URLs, the sites below deserve taking a look:

- [the dominated convergence theorem](https://en.wikipedia.org/wiki/Dominated_convergence_theorem)
- [integral and summation interchange](https://math.stackexchange.com/questions/2237279/integral-of-alternating-series)

---

## Reference
- [MIT OCW](https://ocw.mit.edu/courses/res-6-012-introduction-to-probability-spring-2018/pages/part-ii-inference-limit-theorems/)