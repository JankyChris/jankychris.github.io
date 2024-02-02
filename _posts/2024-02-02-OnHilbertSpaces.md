---
layout: post
title: On Hilbert Spaces
date: 2024-02-02
description: Some simple functional analysis.
tags: math
categories: math
related_posts: false
---

A real vector space \\(X\\) is an **inner product space** if there exists a mapping \\(\langle \cdot, \cdot \rangle : X \times X \to \mathbb{R}\\) satisfying
- \\(\langle ax_1 + bx_2, y \rangle = a \langle x_1, y \rangle + b \langle x_2, y \rangle\\) for all \\(x, y \in X\\) and \\(a, b \in \mathbb{R}\\)
- \\(\langle x, y \rangle = \langle y, x \rangle \\) for all \\(x, y \in X\\)
- \\(\langle x, x \rangle \geq 0\\) for all \\(x \in X\\) (one has equality if and only if \\(x = 0\\))

In this case we call \\(\langle \cdot, \cdot \rangle\\) an **inner product**.