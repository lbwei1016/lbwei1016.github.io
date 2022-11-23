---
layout: page
title: LMS Revisted
usemathjax: true
tag: Probability
time: 2022/11/23
---

**Table of Content**


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

### Performance

The expected performance, once we have a measurement

$$
E\Big[(\Theta-E[\Theta\vert X=x])^2\vert X=x \Big] = var(\Theta\vert X=x).
$$

To make everything abstract, with [law of iterated expectations](5-more-on-conditioning/#law-of-iterated-expectations), we have

$$
E\Big[(\Theta-E[\Theta\vert X])^2 \Big] = E\Big[var(\Theta\vert X)\Big].
$$