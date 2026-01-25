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

Set theory refers to the current foundations of mathematics. At one point, the foundations undergirding mathematics were Geometry, in particular Euclidean Geometry, but a series of revelations and crises, as well as some remarkable results by one Georg Cantor, set the stage for the modern foundations we have today, these are a collection of axioms known as ZFC Set Theory. ZFC stands for Zermelo, Frankel, and Choice, the first two were leading pioneers in the foundations of set theory, and Choice refers to an axiom of Choice. There are advocates for competing foundations, namely Category Theory and Homotopy Type Theory (HoTT). Before we can answer the question above, we ought to first answer even more basic questions, such as, what is meant by "$1$," what is meant by "$+$?" Before we can do that, we need to discuss Axioms.

<br>
If you have small children, or were once an inquisitive child yourself, you know that, inevitably, they discover that you can ask "why?" ad infinitum in response to any answer you give. This sequence of questions, though potentially infinite, is always cut off at some finite stage, usually by an adult that's lost his patience, exclaiming, "BECAUSE I SAID SO!"
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
<h3>BECAUSE I SAID SO!</h3>
</div>
<br>
And so it is much the same in mathematics, for every result one can ask, "but why is this so?" - until we meet an axiom. An axiom is an assumption, something which is asserted to be true without proof. It is should be "obvious" or "intuitive" to some degree. ZFC Set theory is a collection of axioms, it is *the* collection of axioms in some sense, because all of mathematics is done with these assumptions. We won't get into what these axioms are, that would be a whole series of its own, but I feel compelled to mention that this is the system mathematicians have adopted. We're going to adopt a "naive" version of set theory, for our purposes it'll suffice, at least for now.

<div style="text-align: center;">
<h2>$Q_n$? : $Ans_n$.</h2>
<h3>$Q_{n-1}$? : $Ans_{n-1}$.</h3>
<h4>$Q_{n-2}$? : $Ans_{n-2}$.</h4>
<h6>$Q_{n-3}$? : $Ans_{n-3}$.</h6>
<h1>.</h1>
<h2>.</h2>
<h6>.</h6>
<h3>$Q_0$? : $Ans_0 \in Axioms$</h3>
</div>

<h3>What is a number?</h3>

We'll now construct the natural numbers. To a set theorist, everything is a set, and that includes numbers. First, $0 = \varnothing = \{ \}$, that is, $0$ is the empty set. It would be an insult to call any other the empty set, so he can have it. From there, we proceed in stages.

<div align="center">
$$0 = \{\}$$

$$1 = \{0\} = \{\{\}\}$$

$$2 = \{0,1\} = \{\{\}, \{\{\}\}\}$$

$$3 = \{0,1,2\} = \{\{\}, \{\{\}\}, \{\{\}, \{\{\}\}\}\}$$

$$4 = \{0,1,2,3\} = \{\{\}, \{\{\}\}, \{\{\}, \{\{\}\}\}, \{\{\}, \{\{\}\}, \{\{\}, \{\{\}\}\}\}\}$$

$$...$$

</div>

And on and on it goes. For any natural number $n$, we have $$n = \{ n-1, n-2, \ldots, 3, 2, 1, 0 \}$$. In general, if you are at stage $n$, say, you can get to $n^{+} = n+1$ by taking

<div align="center">
$$n^{+} = n+1 = \{n\} \cup n = \{n\} \cup \{n-1, n-2,... 3, 2, 1, 0\} = \{n, n-1, n-2,..., 2, 1, 0\}$$
</div>

This operation is called the "successor" function, and with it, we can now define addition.

<h3>What is addition?</h3>

We'll write $+(a, b)$ in place of $a+b$, but they should signify the same thing to you. You'll see why this choice is made in a moment. Here is the definition, we'll go through an example to make it clear, because when you first see it it looks quite baroque.

<div align="center">
\[
\begin{cases}
a, & \text{if } b = 0, \\[6pt]
+(a,c)^{+}, & \text{if } b = c^{+}, \\[6pt] 
\end{cases}
\]

</div>

<h6>Example: computing 3 + 2</h6>
We compute $+(3,2)$ using the recursive definition of addition:

Since $2 \neq 0$, we apply the second case:

<div align="center">
$+(3,2) = ( +(3,1) )^+$
</div>

Again, since 1 ≠ 0:

<div align="center">
$+(3,1) = ( +(3,0) )^+$
</div>
Now we reach the base case:
<div align="center">
$+(3,0) = 3$
</div>
Substituting back step by step, we obtain:
<div align="center">
$$+(3,1) = 3^+ = 4$$

$$+(3,2) = 4^+ = 5$$

</div>
Therefore, we get the happy result, $3 + 2 = 5$. Aren't you glad you've read this blog?

<h3>1+1+1+...?</h3>
There is no good read to stop our procedure for generating numbers at any finite stage, in fact, we can form the familiar collection:

<div align="center">
$$\{0, 1, 2, 3,... \} = \mathbb{N} = \omega$$
</div>

And then take its successor:

<div align="center">
$$\omega^{+} = \{\omega\} \cup \omega = \{0, 1, 2, 3,..., \omega \} = \mathbb{N} = \omega+1$$
</div>

These numbers, and indeed the infinitude of numbers which come afterwards, ($\omega+2, 2 * \omega, \omega^{2}, \omega^{3}, \omega^{\omega}, $ etc...) form a collection known as the *ordinal numbers\*, which are an extension of the natural numbers $\mathbb{N}$ with similar properties, such as that you can add, multiple, exponentiate, and so on with these numbers and still stay within the class. One can check that $+(\omega, 1) = \omega+1$ as one would expect, but, consider the interesting sum: $+(1, \omega)$. How can we go about computing this sum? $\omega$ is not the sucessor of any number, (there is no $\omega-1$ in the ordinals, just as there is no $0-1$ in $\mathbb{N}$) and it is not $0$, so it doesn't fit within either of our two cases. What we must do is extend our definition as follows:
<br>

<div align="center">
\[
+(a,b) =
\begin{cases}
a, & \text{if } b = 0, \\[6pt]
+(a,c)^{+}, & \text{if } b = c^{+}, \\[6pt]
\displaystyle sup[\cup_{x<b} +(a,c)], & \text{if } b \text{ is a limit ordinal}.
\end{cases}
\]

</div>

Here, a limit ordinal is an ordinal like $\omega$ in that it is not the successor of any ordinal. With this definition in hand, we see that

<div align="center">
$$+(1, \omega) = sup[\cup_{x<\omega}(+1, x)] = \omega$$.
</div>

That isn't a typo. $1+\omega = \omega \neq \omega+1$. That's quite a surprising result! In light of all this, it might feel like the following should be true:

<div align="center">
$$1+1+1... = \omega$$
</div>

There are some problems with this. For starters, we haven't quite defined what it means to take an "infinite sum" with the ordinals. We can take a finite number of sums, as many as we please, but we have yet to define how we would go about taking an infinte sum. Supposing we did have a working definition of infinite sums, and given what we have just shown above, we can derive some nice properties, for instance the equality:

<div align="center">
$$1+(1+1+1...) =1 + \omega = 1 + 1 + 1 +... = \omega$$
</div>

But,

<div align="center">
$$(1+1+1...) + 1 =\omega +1$$
</div>

So in some sense, infinite addition should not commute with finite addition. This might look promising, and gives us some intuition for the result above. In the next post, I'll talk about some attempts to define this infinite addition operation, and we'll learn about multiplication in the ordinal numbers.
