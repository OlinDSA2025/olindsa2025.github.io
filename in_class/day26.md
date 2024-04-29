---
title: "Day 26: Last Regular Class!"
toc_sticky: true
---

## Getting Ready for the Final Event

The main part of the final event is presenting your final projects.  Make sure to consult [the final project assignment page](../assignments/assignment_09.md) for information on the length of the presentation and intended format.  It is my hope that these presentations will summarize not only what you did, but give folks some insight into the algorithm you learned about.

## P versus NP

I had talked about doing some brief discussions on algorithms during the project work period.  I wanted to take this last class to talk about probably the most famous problem in computer science P versus NP (this is also one of [the Millenium Prize problems](https://en.wikipedia.org/wiki/P_versus_NP_problem)).  I'm guessing this is a problem that many folks have heard a bit about (possibly a lot about).  Let's end the semester with establishing a little bit of common knowledge regarding P and NP.

Before we start define P versus NP, we need to talk about what we mean by each of these classes.  First, what is P?  We can think of P as a set comprising various decision problems.  A decision problem is a special case of an algorithm where we are deciding something interest (i.e., the output is a 0 or 1).  We haven't dealt with too many of these problems this semester, but many of the problems we've studies thus far can be cast as decision problems.

P is the set of all decision problems such that there is an algorithm to solve them in $\Theta(n^k)$ where $n$ is the size of the input and $k$ is some finite number.  That is to say, there is an algorithm that runs in polynomial time to solve the decision problem.

NP is the set of all decision problems  such that there is an algorithm to **verify** a proposed solution in $\Theta(n^k)$ where $n$ is the size of the input and $k$ is some finite number.  That is to say, there is an algorithm that runs in polynomial time to verify a candidate solution to the decision problem.

To get a handle on NP problems, let's consider the knapsack problem.  Given a bunch of weighted items, $w_1, w_2, \ldots, w_n$ determine whether there is a partition of these items into two knapsacks such that the weight of the two knapsacks is identical.  If we were given a possible solution to this problem, we could easily verify if it was true or not (how?).

The knapsack problem is part of a set of problems called the NP-Complete problems.  These are problems that are known to be at least as hard as any of the problems in NP.  We show that they are at least as hard using the idea of a reduction.

Right now it is unknown whether the two sets P and NP are the same.  Here are two possibilities.

![A diagram showing two possible scenarios for P and NP](https://upload.wikimedia.org/wikipedia/commons/a/a0/P_np_np-complete_np-hard.svg)

Proving whether P is equal to NP has not been easy.  There have been many [papers published that purport to address the question](https://www.win.tue.nl/~wscor/woeginger/P-versus-NP.htm), but none are widely accepted in the field.  I've even heard that some journals have limits on how many papers per year someone can submit on the question of P versus NP.

## Final push on projects

Let's do it.