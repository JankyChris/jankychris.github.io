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

Proposition: **Cauchy-Schwarz Inequality**

_If $$(X, \langle \cdot, \cdot \rangle)$$ is an inner product space, then_

$$
\vert \langle x, y \rangle \vert \leq \Vert x \Vert \; \Vert y \Vert \text{ for all } x,y \in X.
$$

*Proof:*

_Let $$x, y \in X$$ and $$a \in \mathbb{R}$$. For $$x = y = 0$$ the inequality holds trivially. Suppose $$x \neq 0 \neq y$$. Then_

$$
0 \leq \langle x + ay, x + ay \rangle = \Vert x \Vert^2 + 2a \langle x,y \rangle + a^2 \Vert y \Vert^2.
$$

_Observe that the right hand side of the above equation can be interpreted as a polynomial of degree 2 in $$a$$ and thus_

$$
\begin{align*}
    D \leq 0 &\iff 4 \vert \langle x, y \rangle \vert^2 - 4 \Vert x \Vert^2 \Vert y \Vert^2 \leq 0\\
    &\iff \vert \langle x, y \rangle \vert^2 \leq \Vert x \Vert^2 \Vert y \Vert^2,
\end{align*}
$$

_where $$D$$ denotes the discriminant of the polynomial._
_If $$\exists t \in \mathbb{R}$$ with $$y = tx$$ then $$D = 0$$ and we obtain equality._ $$\square$$



Now the triangle inequality is a direct consequence of the Cauchy-Schwarz inequality, as the following shows:

$$
\begin{align*}
    \Vert x+y \Vert^2 &= \langle x+y, x+y \rangle\\
    &= \Vert x \Vert^2 + \Vert y \Vert^2 + 2 \langle x,y \rangle\\
    &\leq \Vert x \Vert^2 + \Vert y \Vert^2 + 2 \vert \langle x,y \rangle \vert\\
    &\leq \Vert x \Vert^2 + \Vert y \Vert^2 + 2 \Vert x \Vert \Vert y \Vert\\
    &= ( \Vert x \Vert + \Vert y \Vert)^2 \text{ for all } x, y \in X.
\end{align*}
$$

We will further restrict our space to so-called **complete** normed spaces.

Definition: **Cauchy sequence**

_A sequence $$(x_k)_{k=1}^\infty$$ of elements of a normed space $$(X, \Vert \cdot \Vert)$$ is called a **Cauchy sequence** if_

$$
\forall \varepsilon > 0 \exists N \in \mathbb{B} : m, n \geq N \implies \Vert x_m - x_n \Vert < \varepsilon.
$$

Definition: **Complete space**

_A normed space $$(X, \Vert \cdot \Vert)$$ is **complete** if all Cauchy sequences in $$X$$ converge to an element in $$X$$._

Definition: **Banach space**

_A coomplete normed space $$(X, \Vert \cdot \Vert)$$ is called a **Banach space**._

Definition: **Hilbert space**

_An inner product space $$(H, \langle \cdot, \cdot \rangle)$$ which is complete w. r. t. the induced norm $$\Vert \cdot \Vert = \sqrt{\langle \cdot, \cdot \rangle}$$ is called **Hilbert space**._