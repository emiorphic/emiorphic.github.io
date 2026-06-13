---
layout: post
title: "Derivatives in Higher Dimensions"
comments: false
description: ""
keywords: ""
math: true
---

# Notations
Scalar quantities (elements of $$\mathbb{R}$$) are written normally, whereas vector quantities (elements of $$\mathbb{R}^2$$ and above) are written in upright boldface (e.g. $$\vb{x}$$). Also, matrices are written in Sans-Serif (e.g. $$\mathsf{M}$$)


# Introductions
In high school, the introduction of what a derivative of a function is usually goes like this:
> **Definition 1** Let $$D \subseteq \mathbb{R}$$ be the domain where the function $$f$$ is defined (also, $$f \in \mathbb{R}$$). The derivative of $$f$$ evaluated at some point $$x \in D$$, denoted by $$f'(x)$$ or $$\dv{f}{x}$$, is given by the following limit:
> 
> $$
> \begin{equation} \label{eq:simplederiv}
> f'(x) = \lim_{h \to 0} \frac{f(x + h) - f(x)}{h}.
> \end{equation}
> $$

Intuitively, the derivative of a function at a given point represents the 