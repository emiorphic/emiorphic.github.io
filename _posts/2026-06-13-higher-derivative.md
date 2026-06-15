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
> **Definition 1:** Let $$D \subseteq \mathbb{R}$$ be an open set defining the domain of the function (so $$f:D \to \mathbb{R}$$). The derivative of $$f$$ evaluated at some point $$x \in D$$, denoted by $$f'(x)$$ or $$\dv{f}{x}$$, is given by the following limit:
> 
> $$
> \begin{equation} \label{eq:simplederiv}
> f'(x) = \lim_{h \to 0} \frac{f(x + h) - f(x)}{h}.
> \end{equation}
> $$
> 
> If at a point $$x$$ the limit exists, the function is said to be *differentiable* at that point.

(Note: In introductory calculus, the requirement for $$D$$ to be an "open set" is often glossed over. However, it is secretly essential! We need the domain to be open so that there is always a little bit of "wiggle room" around $$x$$. This ensures we can approach x from both the left and the right without accidentally stepping outside the domain where the function is undefined.)

Geometrically, $$f'(x)$$ represents the slope of the line tangent to the curve $$y = f(x)$$ at $$x$$. 

# Can We Go Further?
A natural question would be to ask: "what about higher dimensional functions?" Let us see what happens. First, we need to formally extend our domain $$D$$. 

If we have a function $$f:D \to \mathbb{R}^m$$ where the domain $$D \subseteq \mathbb{R}^n$$, we still require $$D$$ to be an open set. In $$n$$-dimensional space, this simply means that for any point $$\vb{x} \in D$$, there is enough "wiggle room" to draw an $$n$$-dimensional open ball (an $$\varepsilon$$-neighborhood) around $$\vb{x}$$ that is entirely contained within $$D$$.