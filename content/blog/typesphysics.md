
+++
title = "The generalist argument: on physics and programming with types"
date = "2022-01-22"
tags = [
    "functional-programming",
    "physics",
]
+++


How can learning physics help you become a better programmer ? Some ways with which you might be familiar are:

1. Animations: The idea of Spring or Fling based [animations](https://developer.android.com/training/animation/overview#physics-based).

1. Colours: Specifying colours in the RGB format, as is done in CSS or Android is an extension of Newton’s famous experiment of splitting white light into its constituents.

I recently discovered something new, and I want to talk about that in this article.

From physics, you might be familiar with the idea of [dimensional analysis](https://en.wikipedia.org/wiki/Dimensional_analysis). People have tried to use dimensional analysis as a *guide* to arrive at actual physical formulae. For an example of how you can do this for the height reached by an object thrown up in the air, see this interesting [article](https://www.compadre.org/nexusph/course/Example_Creating_equations_using_dimensional_analysis).

Recently, I came across a similar idea in functional programming — that you can **use the signature of a function as a guide to its implementation.**

For example, let’s say you have the following signature (in the Scala programming language):

<iframe src="https://medium.com/media/dee32a36224b738f9ed0493de65cbca9" frameborder=0></iframe>

This is a function with two arguments:

    1. f: A => B 
    f is a function which knows how to transform an argument of type A into an argument of type B

    2. a: A
    a variable of type A

It turns out there is only one program we can write which uses f and a to produce something of type B . Can you figure out what this implementation should be (check the bottom of this page) ? Notice how similar this is to using the constraints of their units to combine *velocity*, *acceleration*, and *mass *to arrive at *length *(See the example in the article linked above).

If you have familiarity with doing dimensional analysis from your high school days, you can use the same intuition to become a better programer in a typed language. I think this is a good example of how acquiring diverse skills can help you in unexpected ways. Just like how [taking a calligraphy course helped Steve Jobs](https://www.inc.com/rohini-venkatraman/how-steve-jobs-and-mark-zuckerberg-came-up-with-th.html#:~:text=Steve%20Jobs%20audited%20a%20calligraphy,looking%20back%2010%20years%20later.).

Credits:
1. [https://www.compadre.org/nexusph/course/Example_Creating_equations_using_dimensional_analysis](https://www.compadre.org/nexusph/course/Example_Creating_equations_using_dimensional_analysis)
2. For more examples of using signature types to guide implementation, check out the book[ *Functional Programming in Scala](https://www.manning.com/books/functional-programming-in-scala), Chapter 2 *
3. [https://www.inc.com/rohini-venkatraman/how-steve-jobs-and-mark-zuckerberg-came-up-with-th.html#:~:text=Steve%20Jobs%20audited%20a%20calligraphy,looking%20back%2010%20years%20later.](https://www.inc.com/rohini-venkatraman/how-steve-jobs-and-mark-zuckerberg-came-up-with-th.html#:~:text=Steve%20Jobs%20audited%20a%20calligraphy,looking%20back%2010%20years%20later.)

Implementation of myFunction :

def myFunction( f: A => B, a:A ) : B = f(a)
