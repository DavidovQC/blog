---
layout: post
title: 1+1+1+... (part 1)
date: 2025-08-26 15:09:00
description: The first part in a long series.
tags: surreal-numbers ordinals games math
categories: math
# featured: true
giscus_comments: true
tikzjax: true
---

I'd like to begin a series addressing the age-old school-boy question, namely,

<center>What is $1+1+1+...\ =\ ?$</center>
<br>
I've found that most people, even mathematically-inclined folk, are contented with the answer "$\infty$" -- and so was I, until I learned about [ordinal](https://en.wikipedia.org/wiki/Ordinal_number) and [surreal](https://en.wikipedia.org/wiki/Surreal_number) numbers -- these are classes of numbers which contain all of the regular counting numbers $\mathbb{N} = \\{ 0, 1, 2, 3, 4,... \\}$, as well as more exotic elements, some of which we will meet today. When I learned about them in high school, I thought these number systems might help us to extend sums like these, after all, I had seen how infinite sums such as:

$$\frac{1}{2}+\frac{1}{4}+\frac{1}{8}+...\ = 1$$

Had been conquered by clever proofs like the one below:

<div align="center">

<svg xmlns="http://www.w3.org/2000/svg" width="159.336" height="159.336" viewBox="-72 -72 119.502 119.502"><g stroke="var(--global-text-color)" stroke-miterlimit="10" stroke-width=".4" transform="matrix(1 0 0 -1 -69.425 44.386)"><clipPath id="pgf0bf26a868e4745e5a87670567580a52fcp1"><path d="M-2.845-2.845v119.501h119.501V-2.845Zm119.501 119.501"/></clipPath><g clip-path="url(#pgf0bf26a868e4745e5a87670567580a52fcp1)"><path fill="none" stroke="var(--global-theme-color)" d="M0 0h113.811M0 7.113h113.811M0 14.226h113.811M0 21.34h113.811M0 28.453h113.811M0 35.566h113.811M0 42.679h113.811M0 49.792h113.811M0 56.905h113.811M0 64.02h113.811M0 71.132h113.811M0 78.245h113.811M0 85.358h113.811M0 92.471h113.811M0 99.584h113.811M0 106.698h113.811M0 113.81h113.811M0 0v113.811M7.113 0v113.811M14.226 0v113.811M21.34 0v113.811M28.453 0v113.811M35.566 0v113.811M42.679 0v113.811M49.792 0v113.811M56.905 0v113.811M64.02 0v113.811M71.132 0v113.811M78.245 0v113.811M85.358 0v113.811M92.471 0v113.811M99.584 0v113.811M106.698 0v113.811M113.81 0v113.811m0 0"/><path fill="none" stroke-width=".8" d="M0 0v113.811h113.811V0H0M56.905 0v113.811M56.905 56.905h56.906M85.358 56.905V0M85.358 28.453h28.453M99.585 28.453V0M99.585 14.226h14.226M106.698 7.113h7.113M106.698 0v14.226"/></g></g></svg>

</div>
<div style="max-width: 359.336px; margin: 0 auto;">

<sub>A unit square is cut in half, the right half is then cut into another half so that it is $\frac{1}{4}$th the area of the original, and so on ad-infinitum, the resulting pieces can then be arranged to make the original square.</sub>

</div>
<br>
So why couldn't the notion of an infinite sum be extended even further to include any arbitrary sequence? In this series I would like to catalog all of the approaches which I've seen for answering this specific question -- yes, surprisingly, there are different answers depending on the field of mathematics you choose to study. I'll begin with the most natural place, which is the study of Set Theory and in particular the theory of Ordinal numbers. Upon my presentation, it may well seem like the theory we explore will be able to answer this question, but by the end I'll introduce some problems with this perspective.

<h3>Set Theory</h3>

Set theory refers to the current foundations of mathematics. At one point, the foundations undergirding mathematics were Geometry, in particular Euclidean Geometry, but a series of revelations and crises, as well as some remarkable results by one Georg Cantor, set the stage for the modern foundations we have today, these are a collection of axioms known as ZFC Set Theory. ZFC stands for Zermelo, Frankel, and Choice, the first two were leading pioneers in the foundations of set theory, and Choice refers to an axiom of Choice. There are advocates for competing foundations, namely Category Theory and Homotopy Type Theory (HoTT). Before we can answer the question above, we ought to first answer even more basic questions, such as, what is meant by "$1$," what is meant by "$+$?"
<br>

<div style="text-align: center;">
<h2>Child: But why is it so?</h2>
<h3>Adult: $\textbf{Answer}_1$ - Child: But why?</h3>
<h4>Adult: $\textbf{Answer}_2$ - Child: But why?</h4>
<h6>Adult: $\textbf{Answer}_3$ - Child: But why?</h6>
<center>
<small>Adult: $\textbf{Answer}_4$ - Child: But why?</small>
</center>
<sub>Adult: $\textbf{Answer}_5$ - Child: But why?</sub>
<h1>.</h1>
<h2>.</h2>
<h6>.</h6>
</div>
