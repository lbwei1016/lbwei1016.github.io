---
layout: page
title: Isometry
usemathjax: true
tag: Linear Algebra, Group Theory
---

**Table of Contents**
- [Isometric Transformation](#isometric-transformation)
- [Reference](#reference)

---

## Isometric Transformation

> 等距變換

> An **isometric transformation** (or **isometry**) is a **shape-preserving transformation**. The isometric transformations are **reflection**, **rotation**,  **translation** and combinations of them such as the *glide*, which is the combination of a translation and a reflection.

Define 

$$O(2, \mathbb{R}) = \{A \in GL_2(\mathbb{R}) | AA^T = I_2\},$$

which contains all $$2\times2$$ matrices of isometry. If $$\text{det}(A) = 1$$, $$A$$ is a rotation matrix; if $$\text{det}(A) = -1$$, $$A$$ is a reflection matrix. This way, we can show that the combination of rotation and reflection is still *reflection* since

$$\text{det}(MR) = \text{det}(M)\text{det}(R) = -1\times 1 = -1.$$

---

## Reference
- [nzmath](https://nzmaths.co.nz/category/glossary/isometric-transformation)