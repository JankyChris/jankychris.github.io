---
layout: post
title: On Hilbert Spaces
date: 2024-02-02
description: Some simple functional analysis.
tags: math
categories: math
related_posts: false
---

## Inner Product Spaces

A real vector space $$X$$ is an **inner product space** if there exists a mapping $$\langle \cdot, \cdot \rangle : X \times X \to \mathbb{R}$$ such that

- $$\langle ax_1 + bx_2, y \rangle = a \langle x_1, y \rangle + b \langle x_2, y \rangle$$ for all $$x, y \in X$$ and $$a, b \in \mathbb{R}$$
- $$\langle x, y \rangle = \langle y, x \rangle $$ for all $$x, y \in X$$
- $$\langle x, x \rangle \geq 0$$ for all $$x \in X$$ (one has equality if and only if $$x = 0$$)

In this case we call $$\langle \cdot, \cdot \rangle$$ an **inner product**.

A real vector space $$X$$ is a **normed space** if there exists a mapping $$\Vert \cdot \Vert : X \to \mathbb{R}$$ such that

- $$\Vert ax \Vert = \vert a \vert \; \Vert x \Vert$$ for all $$x \in X$$ and $$a \in \mathbb{R}$$
- $$\Vert x \Vert \geq 0$$ for all $$x \in X$$ (one has equality if and only if $$x = 0$$)
- $$\Vert x + y \Vert \leq \Vert x \Vert + \Vert y \Vert$$ for all $$x, y \in X$$ *(triangle inequality)*

This map is called the **norm** on $$X$$. Normed spaces are a more general object than inner product spaces in the sense that every inner product space is a normed space with the **induced norm**

$$
\begin{align*}
\Vert \cdot \Vert \colon X &\to \mathbb{R}\\
x &\mapsto \Vert x \Vert = \sqrt{\langle x, x \rangle}.
\end{align*}
$$

The properties of the inner product immediately result in the first two conditions on the norm. In order to show that the induced norm satisfies the triangle inequality we first prove a famous result known as the **Cauchy-Schwarz inequality**.



**Cauchy-Schwarz Inequality**

If $$(X, \langle \cdot, \cdot \rangle)$$ is an inner product space, then

$$
\vert \langle x, y \rangle \vert \leq \Vert x \Vert \; \Vert y \Vert \text{ for all } x,y \in X.
$$