---
layout: post
title: Gradated Multiplication
date: 2025-08-29 15:09:00
description: A nifty generalization of multiplication.
tags: multiplication math
categories: math
# featured: true
giscus_comments: true
tikzjax: true
---

<!--
colors:
text: var(--global-text-color)
theme-color: var(--global-theme-color) -- *blue/red*
bg-text: var(--global-divider-color)
 -->

I'd like to write about an idea I had as an undergraduate which I'd recently came across again. I haven't seen anything like what I'm about to present here, but if anybody's seen anything similar please do let me know and I'd be happy to credit whoever came up with these ideas first. In this blog post I will present a "gradated" multiplication operator.

Consider the following set up, take two numbers $-a < 0 < b$ and graph them on a parabola $f(x) = x^2$ as shown below.

<div align="center">
<svg xmlns="http://www.w3.org/2000/svg" width="342.191" height="228.38" viewBox="-72 -72 256.643 171.285"><g stroke="var(--global-distill-app-color)" stroke-miterlimit="10" stroke-width=".4" transform="matrix(1 0 0 -1 56.052 13.373)"><clipPath id="pgf3b6195bb5dc63bf85ac019fba8d8c0becp1"><path d="M-128.322-85.643V85.643h256.644V-85.643ZM128.322 85.643"/></clipPath><g clip-path="url(#pgf3b6195bb5dc63bf85ac019fba8d8c0becp1)"><path fill="none" stroke="var(--global-divider-color)" d="M-128.037-85.358h256.074m-256.074 14.226h256.074m-256.074 14.227h256.074M-128.037-42.68h256.074m-256.074 14.226h256.074m-256.074 14.227h256.074M-128.037 0h256.074m-256.074 14.226h256.074m-256.074 14.227h256.074m-256.074 14.226h256.074m-256.074 14.226h256.074m-256.074 14.227h256.074m-256.074 14.226h256.074M-128.037-85.358V85.358m14.226-170.716V85.358m14.226-170.716V85.358m14.227-170.716V85.358m14.226-170.716V85.358m14.227-170.716V85.358M-42.68-85.358V85.358m14.226-170.716V85.358m14.227-170.716V85.358M0-85.358V85.358M14.226-85.358V85.358M28.453-85.358V85.358M42.679-85.358V85.358M56.905-85.358V85.358M71.132-85.358V85.358M85.358-85.358V85.358M99.585-85.358V85.358M113.81-85.358V85.358m14.226-170.716V85.358m0 0"/><path fill="none" d="M-127.577 0h255.154"/><path fill="none" stroke-linecap="round" stroke-linejoin="round" stroke-width=".32" d="M-126.377-1.6c-.1.6-1.2 1.5-1.5 1.6.3.1 1.4 1 1.5 1.6M126.377 1.6c.1-.6 1.2-1.5 1.5-1.6-.3-.1-1.4-1-1.5-1.6"/><path fill="none" d="M0-84.898V84.898"/><path fill="none" stroke-linecap="round" stroke-linejoin="round" stroke-width=".32" d="M1.6-83.698c-.6-.1-1.5-1.2-1.6-1.5-.1.3-1 1.4-1.6 1.5M-1.6 83.698c.6.1 1.5 1.2 1.6 1.5.1-.3 1-1.4 1.6-1.5"/><clipPath id="pgf3b6195bb5dc63bf85ac019fba8d8c0becp2"><path d="M-128.037-85.358V85.358h256.074V-85.358ZM128.037 85.358"/></clipPath><g clip-path="url(#pgf3b6195bb5dc63bf85ac019fba8d8c0becp2)"><path fill="none" stroke="#00f" stroke-width=".8" d="m-128.037 576.168 2.586-23.041 2.586-22.572 2.586-22.1 2.587-21.631 2.586-21.16 2.586-20.691 2.586-20.22 2.587-19.75 2.586-19.28 2.586-18.81 2.587-18.34 2.586-17.87 2.586-17.399 2.586-16.928 2.587-16.46 2.586-15.988 2.586-15.519 2.586-15.048 2.587-14.578 2.586-14.109 2.586-13.638 2.586-13.167 2.587-12.698 2.586-12.228 2.586-11.757 2.586-11.287 2.587-10.817 2.586-10.347 2.586-9.876 2.586-9.407 2.587-8.936 2.586-8.466 2.586-7.996 2.586-7.526 2.587-7.056 2.586-6.585 2.586-6.116 2.586-5.645 2.587-5.175 2.586-4.705 2.586-4.235 2.587-3.764 2.586-3.294 2.586-2.824 2.586-2.355 2.587-1.883 2.586-1.414 2.586-.943L-1.311.06 1.276.057l2.586.467 2.586.937 2.586 1.407 2.587 1.878 2.586 2.348 2.586 2.817L19.38 13.2l2.587 3.758 2.586 4.228 2.586 4.699 2.586 5.168 2.587 5.64 2.586 6.108 2.586 6.58 2.586 7.049 2.587 7.52 2.586 7.989 2.586 8.46 2.586 8.93 2.587 9.4 2.586 9.87 2.586 10.34 2.586 10.81 2.587 11.281 2.586 11.751 2.586 12.221 2.586 12.692 2.587 13.161 2.586 13.632 2.586 14.101 2.587 14.572 2.586 15.042 2.586 15.513 2.586 15.982 2.587 16.452 2.586 16.923 2.586 17.393 2.586 17.863 2.587 18.333 2.586 18.804 2.586 19.273 2.586 19.744 2.587 20.214 2.586 20.684 2.586 21.154 2.586 21.624 2.587 22.095 2.586 22.565 2.586 23.035"/><clipPath id="pgf3b6195bb5dc63bf85ac019fba8d8c0becp3"><path d="M-128.037-85.358V85.358h256.074V-85.358ZM128.037 85.358"/></clipPath><g clip-path="url(#pgf3b6195bb5dc63bf85ac019fba8d8c0becp3)"><path fill="none" stroke-width=".8" d="m-128.037 2.846 2.586.517 2.586.517 2.586.518 2.587.517 2.586.517 2.586.517 2.586.518 2.587.517 2.586.517 2.586.517 2.587.517 2.586.518 2.586.517 2.586.517 2.587.518 2.586.517 2.586.517 2.586.517 2.587.517 2.586.518 2.586.517 2.586.517 2.587.518 2.586.517 2.586.517 2.586.517 2.587.517 2.586.518 2.586.517 2.586.517 2.587.518 2.586.517 2.586.517 2.586.517 2.587.517 2.586.518 2.586.517 2.586.517 2.587.517 2.586.517 2.586.518 2.587.517 2.586.517 2.586.518 2.586.517 2.587.517 2.586.517 2.586.517 2.586.518 2.587.517 2.586.517 2.586.517 2.586.517 2.587.518 2.586.517 2.586.517 2.586.517 2.587.517 2.586.518 2.586.517 2.586.517 2.587.518 2.586.517 2.586.517 2.586.517 2.587.517 2.586.518 2.586.517 2.586.517 2.587.518 2.586.517 2.586.517 2.586.517 2.587.517 2.586.518 2.586.517 2.586.517 2.587.518 2.586.517 2.586.517 2.587.517 2.586.517 2.586.518 2.586.517 2.587.517 2.586.517 2.586.518 2.586.517 2.587.517 2.586.517 2.586.518 2.586.517 2.587.517 2.586.517 2.586.517 2.586.518 2.587.517 2.586.517 2.586.518"/></g></g></g></g></svg>
</div>
<br>

Connect the points $(-a, a^2)$ and $(b, b^2)$ to form a line which is of the form $y=mx+B$, then ask, what is the value of the y-intercept $B$? First let's determine the value of

$$m = \frac{y_2 - y_1}{x_2 - x_1} = \frac{b^2-a^2}{b-(-a)} = \frac{(b+a)(b-a)}{b+a} = b-a$$

Therefore,

$$y=(b-a)x+B$$

Let's plug in $(b, b^2)$, we get $$b^2 = (b-a)b + B$$, solving for $B$ we get

$$B = ab$$

So the y-intercept is the product of $ab$, neat! But how does this lead us to the notion of "gradated multiplication?" Let's consider the points which lie on the line between points $A$ and $B$, these points give us other values for $a \times b$, but with a bit of a twist. Consider the point $X$, since it lies to the left of the y-axis, it can be said to the value of a product which will "favor" $a$. This picture gives us an interpretation of $a^2$ as "the value of $a \times b$ which totally disregards b." So for every value between $(-a, b)$, we have a notion of multiplication, where $0 \in (-a, b)$ corresponds to "regular" multiplication. We can find the general value for any parameter $x \in (-a, b)$ as just the value of the line at $x$:

$$a \times_{x} b :=  (b-a)x + ab$$

Notice that in particular, $a \times_{0} b = (b-a)*0 + ab = ab$. In some sense this is totally all right, but instead of an interval [-a, b], it might be preferable to work with the interval [0, 1], so that if we want a product which is say, $30\%$ reliant on $a$, we plug in $p=.3$. There is an easy fix for this, namely, to find a map from the interval $[-a, b] \to [0, 1]$ with the following properties:

<div align="center">
$r(-a) = 0$
<br>
$r(b) = 1$
</div>

Which is achieved by the transformation $r(x) = \frac{x+a}{b+a}$. Of course, we really want $r^{-1}$, which is a rudimentary calculation yielding:

$$r^{-1}(p) = (b+a)p - a$$

Now, we can take any value $p \in [0, 1]$, and map it via $r^{-1}$ to $[a, b]$, then plug that value in to compute $a\times_p b := a \times_{r^{-1} (p)} b$, plugging in we get:

$$a \times_p b = (b-a)[(b+a)p - a] + ab = (b^2 - a^2)p - ab + a^2 + ab$$

Finally, after some more algebraic massaging we get the very nice answer of:

$$a \times_p b = b^2p + (1-p)a^2$$

What value of $p$ will recover regular multiplication? Unfortunately, it isn't $.5$, there is a choice for our function $r$ which would yield this result, but the real answer can be computed by setting $b^2p + (1-p)a^2 = ab$. Recall that we could retrieve the familiar multiplication operator upon setting $x=0$, to compute the corresponding value of p we should plug it into $r$, but $r(0) = \frac{a+0}{a+b}$, and indeed, the solution to this equation is $p = \frac{a}{a+b}$.

This yields some very natural questions, now that we have a gradated multiplication, can we get a gradated division operator? And after that, or perhaps before, what would gradated addition look like? The formula above would suggest:

$$a +_p b  \stackrel{?}{=} ap + (1-p)b$$

Setting $p = \frac{a}{a-b}$ recovers the typical addition operator, but I haven't thought through any nice geometric reason for why this definition is natural.

And after we've collected all of these ingredients, it would be quite natural to ask, can we then find a gradated derivative operator? Would it coincide with any of the current definitions? I'll tell you once I've made some progress.
