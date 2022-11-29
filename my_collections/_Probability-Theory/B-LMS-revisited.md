---
layout: page
title: LMS Revisited
usemathjax: true
tag: Probability
time: 2022/11/23
---

**Table of Content**
- [Mean Squared Error (MSE)](#mean-squared-error-mse)
  - [**Remark**](#remark)
  - [Performance](#performance)
- [LMS Properties](#lms-properties)

---

## Mean Squared Error (MSE)

$$
E\Big[(\Theta-\hat{\theta})^2\Big] = E[\Theta^2] - 2E[\Theta]\hat{\theta} + \hat{\theta}^2
$$

To minimize it,

$$
{d\over d\hat{\theta}}E\Big[(\Theta-\hat{\theta})^2\Big] = -2E[\Theta]+2\hat{\theta} = 0, \\
\hat{\theta} = E[\Theta].
$$

Hence, we see that the **optimal** mean squared error is

$$
E\Big[(\Theta-E[\Theta])^2 \Big] = var(\Theta).
$$

Similarly, $$E[\Theta\vert X=x]$$ minimizes $$E\Big[(\Theta-\hat{\theta})^2\vert X=x \Big]$$. With the [law of iterated expectations](5-more-on-conditioning/#law-of-iterated-expectations), we can show that

$$
\hat{\Theta} = E[\Theta\vert X] \text{ minimizes } E\Big[(\Theta-g(X))^2 \Big],
$$

over all estimators $$\hat{\Theta}=g(X)$$.

### **Remark**

因為 $$E[\Theta\vert X]$$ 可以使誤差最小，所以它是最佳的 **estimator**。而最佳的 **estimate** 則是 $$E[\Theta\vert X=x]$$，也就是任意 $$x$$ 下 $$\Theta$$ 的平均值。

在二維平面上的話，$$\hat \theta_{LMS}$$ 是每一個 $$X=x$$ 與 $$\Theta$$ 的圖形相交的直線的「重心」，而 $$\hat \Theta_{LMS}$$ 則是把所有重心連起來的直（曲）線！

### Performance

The expected performance, once we have a measurement

$$
E\Big[(\Theta-E[\Theta\vert X=x])^2\vert X=x \Big] = var(\Theta\vert X=x).
$$

To make everything abstract, with [law of iterated expectations](5-more-on-conditioning/#law-of-iterated-expectations), we have

> 這裡計算的是誤差平方的平均有多大。

$$
E\Big[(\Theta-E[\Theta\vert X])^2 \Big] = E\Big[var(\Theta\vert X)\Big].
$$

---

## LMS Properties

Let the estimator $$\hat{\Theta}=E[\Theta\vert X]$$, and the error $$\tilde \Theta=\hat{\Theta}-\Theta$$. We have 

$$
\begin{align*}
&E[\tilde{\Theta}\vert X=x]=0, \tag{1}\\
&cov(\tilde{\Theta}, \hat{\Theta}) = 0, \tag{2} \\
&var(\Theta) = var(\hat{\Theta}) + var(\tilde{\Theta}). \tag{3}
\end{align*}
$$

> 這樣的方法可以用來證明 [law of total variance](../5-more-on-conditioning/#law-of-total-variance)。