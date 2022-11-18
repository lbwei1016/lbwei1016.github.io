---
layout: page
title: Bayesian Inference
usemathjax: true
tag: Probability
time: 2022/11/18
---

**Table of Content**

---

## Introduction

假設現在有一訊號 $$S$$，經過介質 $$a$$ 減弱後，再經過 uniform 雜訊 $$W$$ 干擾，最終我們觀測到 $$X$$；以上過程可以以一方程式表示

$$
X=aS+W。
$$

假如介質 $$a$$ 是未知的，我們可以「人工」發送訊號 $$S$$，並藉由觀察到的 $$X$$ 來推論 $$a$$；這過程稱為 **model building**。

現在我們已經知道介質 $$a$$ 了，於是可以用剛剛得到 model 來推論我們感興趣的「未知」訊號 $$S$$；這稱為 **variable estimation**。
