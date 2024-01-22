---
title: "Day 2: Programming in Kotlin"
toc_sticky: true
---

## Algorithm Design Patterns Whirlwind Tour

We're going to take a few classes to get a feel for the various algorithmic design patterns we will meet this semester.  During class 1, we met the design pattern *divide and conquer*.  Today, we'll be learning about greedy algorithms.

> Suppose you have a budget of $$N$$ dollars to purchase flour and that flour can be purchased on day $$i$$ for $$x_i$$ dollars per pound.  Determine the maximum pounds of flour you can purchase with your budget.  Is your algorithm a greedy algorithm?

> Determine a greedy algorithm for making change for $$N$$ cents using quarters, dimes, nickels, and pennies.  Does your greedy algorithm use the fewest coins possible (make an intuitive argument, no proof necessary)?
 
> If the US began minting a 20-cent coin, would a greedy algorithm still solve the optimal change-making problem?

## O() and Friends

$$f(x) = O(g(x))$$ if there exists a positive real number $$M$$ and a real number $$x_0$$ such that,
$$
\begin{align}
|f(x)| \leq M g(x)~~\mbox{for all}~~x \geq x_0
\end{align}
$$

$$f(x) = \Omega(g(x))$$ if there exists a positive real number $$M$$ and a real number $$x_0$$ such that,

$$
\begin{align}
|f(x)| \geq M g(x)~~\mbox{for all}~~x \geq x_0
\end{align}
$$

We say that $$f(x) = \Theta(g(x))$$ if $$f(x) = O(g(x))$$ and $$f(x) = \Omega(g(x))$$.

Here is a handy figure from "Introduction to Algorithms" by Cormen, Leiserson, Rivest, and Stein.

![This figure shows a grahical depiction of O(g(n)) (left), Omega(g(n)) (center), and Theta(g(n)) (right)](../images/bigoandfriends.png)

With your group, explain how the formal definitions (given earlier) relate to these pictures.

### Practice Problems

1. Show that $$n = O(n^2)$$
2. Show that $$n^2 \neq O(n)$$.
3. Show that any polynomial is $$O(2^n)$$
4. Show that $$3^n = \Omega(2^n)$$

This problem is from former Olin Professor Allen Downey's Think Python second edition.   In this context, order of growth can be understood to mean $$\Theta$$.  I made one modification to part 3 of the exercise.

* What is the order of growth of $$n^3 + n^2$$? What about $$1000000 n^3 + n^2$$? What about $$n^3 + 1000000 n^2$$?
* What is the order of growth of $$(n^2 + n)(n + 1)$$?
* If $$f$$ is in $$O(g)$$ and $$g$$ is a continuously increasing functions that grows infinitely large as $$n \rightarrow \infty$$, what can we say about $$af+b$$, where $$a$$ and $$b$$ are constants?
* If $$f_1$$ and $$f_2$$ are in $$O(g)$$, what can we say about $$f_1 + f_2$$?
* If $$f_1$$ is in $$O(g)$$ and $$f_2$$ is in $$O(h)$$, what can we say about $$f_1 + f_2$$?
* If $$f_1$$ is in $$O(g)$$ and $$f_2$$ is $$O(h)$$, what can we say about $$f_1 \times f_2$$?

## Kotlin versus Python

I wanted to take a few minutes to discuss the ways that Kotlin compares with a language that we all know: Python.

Key differences:
* Execution Model: Interpreted (Python) versus Compiled (Kotlin)
* Type System: Dynamic typing (Python) versus Static Typing (Kotlin)
* Interoperability: call C/C++ code (Python) versus calling Java (Kotlin)
* External dependencies: pip / Anaconda / ... (Python) versus Gradle (Kotlin)
* Syntax: indentation to show code nesting (Python) versus Curly braces (Kotlin)

## Work on Kotlin Basics

We'll take some time to work on the assignment.  This will give us a chance to discuss Kotlin, figure out bugs with your environment, etc.  We can do some knowledge sharing amongst the class (interesting resources or other things you found).
