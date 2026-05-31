---
layout: post
title: The eml Calculator (or, "The Two Button Calculator")
date: 2026-05-30 15:09:00
description: Building a scientific calculator that can perform any computation using just 2 buttons
tags: math calculator CAD designs
categories: math
# featured: true
giscus_comments: true
tikzjax: true
---

Excuse me, could I interest you in some good news? Oh, hm? No, no, I'm not talking about that, that's _old_ news. Why ever aren't you interested in hearing me out? _"No news is good news"_ you say? Well it certainly feels that way, seems like nowadays, _No_ news is _good_ news! But I think if you'll read further along you won't come to regret it.

Let's start with a question: what is the meaning of the word genius? I hear it used often, dare I say, I hear it _overused_ often. But strangely I have never heard the word defined. To say nothing of persons, my definition is as follows: an idea is _genius_ if it is simple, interesting, and novel. It is easy to have an idea which fits one criteria, fitting two is quite rare but doable, but to have all three is miraculous.

Recently, a paper was written up and posted on the arXiv: [All elementary functions from a single operator](https://arxiv.org/pdf/2603.21852) by Andrzej Odrzywolek, and I think it fits this definition of genius perfectly. A special operation is defined,

$$eml(x, y) := e^{x} - ln(y)$$

Just as $+$ and $-$, and $\div$ and $\times$ are operations which take two values (e.g, $x+y$) and return a single value, so too is $eml$, it takes two numbers, and returns a single number. The name "$eml$" comes from its definition, "{**E**}xponential {**M**}inus {**L**}ogarithm"

What's amazing about this function is that you can use it to retrieve all of the operations I just mentioned, along with all of the other functions you'd find on a scientific calculator, so $e^{x}$ and $ln(x)$, along with $sin(x)$, $cos(x)$, and $tan(x)$ are all retrievable if you cleverly compose the $eml$ function with itself. What's more, you can perform _any_ computation that you can perform on a scientific calculator using _just_ $eml$ and the number $1$. That's right! You don't even need every other digit. Below you'll find some code I whipped up in R that retrieves some of these functions, $e^x,\ ln(x)$ and $id(x)$.
<br>
<br>

```R
eml <- function(x, y){
  exp(x) - log(y)
}

exp_from_eml <- function(z){
    eml(z,1)
}

ln_from_eml <- function(z){
    eml(1, eml(eml(1, z), 1))
}

x_from_eml <- function(z){
    eml(1, eml(eml(1, eml(z, 1)), 1))
}
```

<br>

Note that you have to do some work just if you want to get the original number you start with unmodified, so in the above example:

$$eml(1, eml(eml(1, eml(3, 1)), 1)) = 3$$

Addition is defined as:

```R
plus_from_eml <- function(x, y){
    eml(eml(1, eml(eml(1, x), 1)),  eml(eml(eml(1, eml(eml(1, eml(1, eml(eml(1, 1), 1))), 1)),  eml(y, 1)), 1))
}
```

That's really quite something!

In their Principia Mathematica, philosophers Alfred North Whitehead and Bertrand Russell set out to prove all of mathematics could be derived from logic. It took them $379$ pages to prove $1+1=2$, they prefaced the theorem with the now legendary words "The following result is sometimes useful."

In their spirit, let us rephrase - the following result is sometimes useful:

$$eml(eml(1,eml(eml(1,1),1)),eml(eml(eml(1,eml(eml(1,eml(1,eml(eml(1,1),1))),1)),eml(1,1)),1)) = 2$$

You can find definitions for subtraction, division, exponentiation, etc, written in R, along with the above expression, at the end of this article.

## The eml Calculator

Seeing the title of the paper I immediately thought of making a scientific calculator, and indeed Odrzywolek hints at just such an application himself. That's what this blogpost is really about showcasing. I wanted to make a calculator with just two buttons, but I was afraid my skills were too novice for such a venture. Nonetheless I tried to learn Fusion 360, and to my surprise it was a much easier experience than I expected.

<br>

{% include figure.liquid loading="eager" path="assets/img/eml_calculator_1.png" class="img-fluid rounded z-depth-1" %}

<div class="caption">
    A 3 button calculator, <em>not</em> a gameboy advanced.
</div>

The first design decision I made was to use the longest LCD I could find, and I settled on a [40x2 LCD display](https://www.buydisplay.com/low-cost-4002-40x2-charcter-lcd-display-module-blue-white-color) -- I thought it would be useful, since as you can see from the discussion we had above, even the most elementary computations are comically long. Of course this doesn't help the situation much, but I think it makes the calculator look distinct.

The other design decision, born out of unfortunate necessity, is that there are actually $3$ buttons, one for $eml(x, y)$, one for the digit $1$, and one as the _enter_ key.

The calculator software runs on the arduino nano, I would like to eventually design my own PCB, and I think I will after this first prototype is finished. There's a saying I came across that I quite like, "first you should make it exist, and then you can perfect it." What remains for now is to actually 3D print, assemble, and solder everything together.

# Conclusion

So, why do I call this paper good news? Because this paper is genius. It is novel, simple, and interesting. The result of the paper is not as exciting as the lessons it teaches, first: _Mathematics is not over yet!_ - these ideas are still out there, somewhere, waiting to be found! And that brings me to the second point: genius ideas, because they are simple, typically don't require very much work. You can read the paper for yourself, the programming and analysis involved is very impressive but not prohibitively difficult or obtuse. The brilliance was in _asking the question_ of whether we could collapse all of our fundamental operations into one such operation.

To sum up: _It only takes one brilliant question to come up with a delightful breakthrough._

<!-- I hope you will consider that in these potentially difficult times. If it is true today, it will always be true: small people can still do big things. -->

# Extra Code

Below are some other functions produced using just the $eml$ operator:

```R
minus_from_eml <- function(x, y){
   eml(eml(1, eml(eml(1, x), 1)),  eml(y, 1))
}

neg_from_eml <- function(z){
    eml(eml(1, eml(eml(1, eml(1, eml(eml(1, 1), 1))), 1)),  eml(z, 1))
}

plus_from_eml <- function(x, y){
    eml(eml(1, eml(eml(1, x), 1)),  eml(eml(eml(1, eml(eml(1, eml(1, eml(eml(1, 1), 1))), 1)),  eml(y, 1)), 1))
}

recip_from_eml <- function(z){
    eml(eml(eml(1, eml(eml(1, eml(1, eml(eml(1, 1), 1))), 1)),  eml(eml(1, eml(eml(1, z), 1)), 1)), 1)
}

times_from_eml <- function(x, y){
    eml(eml(eml(1, eml(eml(1, eml(1, eml(eml(1, x),1))), 1)),  eml(eml(eml(1, eml(eml(1, eml(1, eml(eml(1, 1), 1))), 1)),  eml(eml(1, eml(eml(1, y), 1)), 1)), 1)), 1)
}

exponent_from_eml <- function(x, y){
   eml(eml(eml(eml(1, eml(eml(1, eml(1, eml(eml(1, eml(1, eml(eml(1, x), 1))), 1))), 1)),  eml(eml(eml(1, eml(eml(1, eml(1, eml(eml(1, 1), 1))), 1)),  eml(eml(1, eml(eml(1, y), 1)), 1)), 1)), 1), 1)
}

# The following result is sometimes useful:
eml(eml(1,eml(eml(1,1),1)),eml(eml(eml(1,eml(eml(1,eml(1,eml(eml(1,1),1))),1)),eml(1,1)),1))

```
