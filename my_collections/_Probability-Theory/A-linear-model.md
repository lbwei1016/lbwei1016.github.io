---
layout: page
title: Linear Model
usemathjax: true
tag: Probability
time: 2022/11/23
---

**Table of Content**
- [Recognizing normal PDFs](#recognizing-normal-pdfs)
- [Linear models](#linear-models)
  - [Single observation](#single-observation)
  - [Multiple observations](#multiple-observations)
    - [The mean square error](#the-mean-square-error)
  - [Multiple parameters](#multiple-parameters)
- [Misc](#misc)
- [Reference](#reference)

---

## Recognizing normal PDFs

若

$$
f_X(x) = c\cdot e^{-(\alpha x^2+\beta x+\gamma)},\ \alpha>0，
$$

則 

$$
X\sim N(-\beta/2\alpha, 1/2\alpha)。
$$

其中原理只是簡單的變數對應而已。值得注意是，$$e^{-(\alpha x^2+\beta x+\gamma)}$$ 在經過整理後會變成 $$e^d\cdot e^{-\alpha(x+\beta/2\alpha)^2}$$，而我們不必擔心 $$c\cdot e^d$$ 是否等於 $$1/\sqrt{2\pi}\sigma$$，因為既然 $$f_X(x)$$ 身為 PDF，不論經過如何的變數處理，她依舊是 PDF。

---

## Linear models
### Single observation

設 $$\Theta, W\sim N(0,1)$$，且兩者獨立，則

$$
f_{X\vert\Theta}(x\vert \theta) \rightarrow X = \theta + W \sim N(\theta, 1)。
$$

經過 [Bayesian Inference](../9-Bayesian-infer) 運算後，可以發現 **$$f_{\Theta\vert X}(\theta\vert x)$$ is normal**，也就是說，

$$
\hat{\theta}_{MAP} = \hat{\theta}_{LMS} = E[\Theta\vert X=x]，
$$

因為 **distribution 的最高點就在 mean**。

### Multiple observations

$$
X_1 = \Theta + W_1 \\
\vdots \\
X_n = \Theta + W_n
$$

這裡 $$\Theta \sim N(x_0, \sigma_0^2)$$、$$W \sim N(0, \sigma_i^2)$$，而 $$X$$ 是 *normal vector*：

$$
f_{X\vert \Theta}(x\vert \theta) = f_{X_1,\cdots,X_n\vert \Theta}(x_1,\cdots,x_n\vert \theta)。
$$

在 $$\Theta=\theta_i$$ 之下，$$X_i=\theta_i + W_i$$；因為 $$W_i$$ 間彼此獨立，所以 $$X_i$$ 之間亦同。因此上述 joint PMF 可以拆成

$$
f_{X\vert \Theta}(x\vert \theta) = \prod_{i=1}^nf_{X_i\vert \Theta}(x_i\vert \theta)。
$$

再經過運算和[係數比較](#recognizing-normal-pdfs) ，可以得到

$$
\hat{\theta}_{MAP} = \hat{\theta}_{LMS} = E[\Theta\vert X=x] = {\sum_{i=0}^n{x_i\over \sigma_i^2} \over \sum_{i=0}^n{1\over \sigma_i^2}}.
$$

> $$\hat{\theta}$$ 可以看成是 *the weighted sum of $$x$$*。

#### The mean square error

回想 $$\hat{\Theta}=g(X), \hat{\theta} = g(x)$$，於是

$$
\begin{align*}
E\Big[(\Theta- \hat{\Theta})^2\vert X=x\Big] &= E\Big[(\Theta- g(X))^2\vert X=x\Big] \\
&= E\Big[(\Theta- g(x))^2\vert X=x\Big] \\
&= E\Big[(\Theta- \hat{\theta})^2\vert X=x\Big] \\
&= E\Big[(\Theta- E[\Theta\vert X=x])^2\vert X=x\Big] \\
&= var(\Theta\vert X=x) \\
&= 1/\sum_{i=0}^n{1\over \sigma_i^2}，
\end{align*}
$$

其中最後一個等式由[係數比較](#recognizing-normal-pdfs)得到。再兩邊取期望值：

$$
E\Big[(\Theta- \hat{\Theta})^2\Big] = 1/\sum_{i=0}^n{1\over \sigma_i^2}。
$$

### Multiple parameters

$$
X_i = \Theta_0 + \Theta_1t_i + \Theta_2t_i^2 + W_i
$$

> Solve linear equations to obtain MAP estimate (the equations comes from partial differential).

---

## Misc

- Bayesian confidence interval

---

## Reference
- [MIT OCW](https://ocw.mit.edu/courses/res-6-012-introduction-to-probability-spring-2018/pages/part-ii-inference-limit-theorems/)
