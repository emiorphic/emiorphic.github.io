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
> **Definition 1:** Let $$D \subseteq \mathbb{R}$$ be an open set defining the domain of the function $$f$$ (so $$f:D \to \mathbb{R}$$). The derivative of $$f$$ evaluated at some point $$x \in D$$, denoted by $$f'(x)$$ or $$\dv{f}{x}$$, is given by the following limit:
> 
> $$
> \begin{equation} \label{eq:simplederiv}
> f'(x) \coloneqq \lim_{h \to 0} \frac{f(x + h) - f(x)}{h}.
> \end{equation}
> $$
> 
> If at a point $$x$$ the limit exists, the function is said to be *differentiable* at that point.

(Note: In introductory calculus, the requirement for $$D$$ to be an "open set" is often glossed over. However, it is secretly essential! We need the domain to be open so that there is always a little bit of "wiggle room" around $$x$$. This ensures we can approach $$x$$ from both the left and the right without accidentally stepping outside the domain where the function is undefined.)

Geometrically, $$f'(x)$$ represents the slope of the line tangent to the curve $$y = f(x)$$ at $$x$$. 

# Can We Go Further?
A natural question would be to ask: "what about higher dimensional functions?" Let us see what happens. First, we need to formally extend our domain $$D$$. 

If we have a function $$\vb{f}:D \to \mathbb{R}^m$$ where the domain $$D \subseteq \mathbb{R}^n$$, we still require $$D$$ to be an open set. In $$n$$-dimensional space, this simply means that for any point $$\vb{x} \in D$$, there is enough "wiggle room" to draw an $$n$$-dimensional open ball (an $$\varepsilon$$-neighborhood) around $$\vb{x}$$ that is entirely contained within $$D$$.

With all of that in mind, we may proceed. Given a function $$\vb{f}:D \to \mathbb{R}^m$$ where $$D \subseteq \mathbb{R}^n$$, can we extend $$\eqref{eq:simplederiv}$$ so that we have a definition of differentiability?

$$
\begin{equation}
\lim_{\vb{h} \to \vb{0}} \frac{\vb{f}(\vb{x} + \vb{h}) - \vb{f}(\vb{x})}{\vb{h}}.
\end{equation}
$$

Even a kindergartener would realize that this is nonsensical. Barring the fact that $$\vb{f}(\vb{x}) \in \mathbb{R}^m$$ but $$\vb{h} \in \mathbb{R}^n$$ (because $$\vb{x} \in \mathbb{R}^n$$), dividing a vector with another vector is not something you can do. Thus, we need a different strategy.

Looking back at $$\eqref{eq:simplederiv}$$, we can perform a change of variable:

$$
\begin{align}
f'(x) &= \lim_{h \to 0} \frac{f(x + h) - f(x)}{h}\\
\Longrightarrow f'(t) &= \lim_{x \to t} \frac{f(x) - f(t)}{x - t}.
\end{align}
$$

If that equality holds, then the following should also hold:

$$
\begin{equation}
\lim_{x \to t} \left(\frac{f(x) - f(t)}{x - t} - f'(t)\right) = 0.
\end{equation}
$$

Now, combine the terms over a common denominator:

$$
\begin{equation} \label{eq:wow!}
\lim_{x \to t} \left(\frac{f(x) - [f(t) + f'(t)(x - t)]}{x - t}\right) = 0.
\end{equation}
$$

Remember the geometric interpretation of $$f'(x)$$? Mathematically, the following equation

$$
y = f(t) + f'(t)(x - t)
$$

represents the line tangent to the curve $$y = f(x)$$ at $$x = t$$. When plotted and zoomed in, the curve and the line will look almost indistinguishable; the line *locally approximates* the curve. How well does the line locally approximates the curve? We can measure that by subtracting both curves to obtain the error, which is what the numerator in $$\eqref{eq:wow!}$$ is. Let $$E(x) = f(x) - [f(t) + f'(t)(x - t)]$$, then the limit becomes

$$
\begin{equation} \label{eq:WOW!}
\lim_{x \to t} \frac{E(x)}{x - t} = 0.
\end{equation}
$$

Before we continue, I would like to introduce a crucial tool from asymptotic analysis: little-o notation. First, define the following set:

$$
o(g(x)) \coloneqq \left\{f(x) \, \middle| \, \lim_{x \to a} \frac{f(x)}{g(x)} = 0\right\}.
$$

Then, $$f(x)$$ is said to be little-o of $$g(x)$$ as $$x \to a$$ if $$f(x) \in o(g(x))$$. It is customary (albeit dubious) to write $$f(x) = o(g(x))$$ instead. With that in mind, we can write the limit $$\eqref{eq:WOW!}$$ as

$$
\begin{equation}
E(x) = o(x - t) \quad \Longrightarrow \quad f(x) = f(t) + f'(t)(x - t) + o(x - t), \quad x \to t.
\end{equation}
$$

Thus, we have arrived at another way of defining differentiability, motivated by the result above. It is equivalent to Definition 1, and the proof is left as an exercise for the reader.
> **Definition 2:** Let $$D \subseteq \mathbb{R}$$ be an open set defining the domain of the function $$f$$ (so $$f:D \to \mathbb{R}$$). $$f$$ is differentiable at $$x = t$$ if and only if there exists constants $$a, b$$ such that
> $$
> \begin{equation} \label{eq:newder}
> f(x) = a + b(x - t) + o(x - t).
> \end{equation}
> $$
> Moreover, if this does hold, then necessarily $$a = f(t)$$ and $$b = f'(t)$$.

The idea that a function is differentiable if and only if a line locally approximates the function generalizes pretty neatly into higher dimensions. 