---
layout: page
title: More on Conditioning
usemathjax: true
tag: Conditional Probability
time: 2022/10/15
---

**Table of Content**
- [Continuous Stuff](#continuous-stuff)
  - [Coditional CDF](#coditional-cdf)
- [Conditional Expectation and Variance](#conditional-expectation-and-variance)
  - [Problem](#problem)

---

> 見 [Conditioning](../3-Conditioning)。

## Continuous Stuff

$$
f_{X \vert Y}(x \vert y) = {f_{X,Y}(x,y) \over f_Y(y)}, \\
P(X\in A \vert Y=y) = \int_A f_{X\vert Y}(x \vert y)dx. $$

### Coditional CDF

$$
F_{X|Y}(x|y) = P(X\le x|Y=y) = \int_{-\infty}^x f_{X|Y}(t|y)dt, \\

f_{X|Y}(x|y) = {\partial F_{X|Y}(x|y) \over \partial x}.
$$

> 注意是 under $$Y=y$$！

但是，在 continous r.v. 中，$$P(Y=y)$$ 不是應該要等於 $$0$$ 嗎？的確，$$P(Y=y) = 0$$，不過這裡我們計算的是 r.v. $$X$$，也就是說，我們關注的是**在 $$Y=y$$ 的情況下，$$\forall X \le x$$ 的機率**！也因為這個考量，$$F_{X\vert Y}(x\vert y)$$ 才不寫成 $$P(X\le x, Y=y)/P(Y=y)$$。

---

## Conditional Expectation and Variance

### Problem
> A rat in a maze has only two paths to go. If the rat goes right, it will return to the starting point after $$3$$ minutes. If the rat goes left, there is a $$2\over 3$$ chance of returning to the starting point after $$5$$ minutes, and a $$1\over 3$$ chance of exiting the maze after $$2$$ minutes. Find the average time that the rat is in the maze if the probability of the rat going left and right is equal.

**Solution**

Let $$T$$ be the time that the rat is in the maze and 

$$
X = \begin{cases}
    0, &\text{goes right}, \\
    1, &\text{goes left}.
\end{cases}
$$

Then

$$
P(X=0) = P(X=1) = {1\over 2}, \\
E(T|X=0) = 3 + E(T), \\
E(T|X=1) = {2\over 3}(5 + E(T)) + {1\over 3}\cdot 2.
$$

Thus we have

$$
E[E(T|X)] = {1\over 2}(3+E(T)) + {1\over 2}({2\over 3}(5 + E(T)) + {1\over 3}\cdot 2) = E(T), \\
\therefore E(T) = 21.
$$