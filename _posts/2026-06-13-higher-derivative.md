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
> **Definition 1:** Let $$D \subseteq \mathbb{R}$$ be the domain where the function $$f$$ is defined (so $$f:D \to \mathbb{R}$$). The derivative of $$f$$ evaluated at some point $$x \in D$$, denoted by $$f'(x)$$ or $$\dv{f}{x}$$, is given by the following limit:
> 
> $$
> \begin{equation} \label{eq:simplederiv}
> f'(x) = \lim_{h \to 0} \frac{f(x + h) - f(x)}{h}.
> \end{equation}
> $$
> 
> If at a point $$x$$ the limit exists, the function is said to be *differentiable* at that point.

Geometrically, $$f'(x)$$ represents the slope of the line tangent to the curve $$y = f(x)$$ at $$x$$. 

# Can We Go Further?
A natural question would be to ask: "what about higher dimensional functions?" Let us see what happens. 

To generalize this, we first need to ensure that the limit can be approached from *any* direction without stepping outside our domain. Therefore, we will restrict our domain $$D \subseteq \mathbb{R}^n$$ to be an open set. This simply means that for any point $$\vb{x} \in D$$, there is enough "wiggle room" around $$\vb{x}$$ (an $$\varepsilon$$-neighborhood) that is also entirely contained within $$D$$.