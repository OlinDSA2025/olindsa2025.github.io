---
title: "Day 1: Course Intro and Welcome to DSA"
toc_sticky: true
---

## Course Structure and Major Topics

The goal of this course is for you to learn how to frame problems formally and ultimately select appropriate data structures and algorithms to solve them.  We'll get more into what we mean by framing problems later (there is an example later today), but for now I want to focus on the sorts of problems we will be tackling and the algorithmic strategies we will be using to solve them.

### Data Structures

* Data structures as supports for algorithms.  Ultimately, data structures are useful to solve certain problems.  There are a number of properties we might care about when we select a data structure.  Can we brainstorm some as a class?
* We'll be learning about basic linked data structures (linked lists, stacks, queues), data structures to represent graphs, and tree-based data structures (e.g., binary search trees or heaps).

### Algorithmic Design Patterns

While each algorithm must be tuned to the particular problem being solved, there are general algorithm types that we will encounter (e.g., some algorithms work by breaking a larger problem into smaller, some use the greedy method, others are based on backtracking or graph search).

### Analyzing Algorithms

We want to develop ways to talk about the computational and spatial complexity of algorithms.  We can look at these factors from both theoretical and empirical frameworks.  We'll mostly be focusing what's known was worst case, asymptotic analysis in this course (a lot of jargon I know).

### Specific Algorithms

Of course we will learn about specific algorithms.  We'll see algorithms from graph theory, string matching, sorting, matrix multiplication, and many more.

### Algorithmic Deep Dive

You'll be able to customize the course material by taking a deep dive into a new algorithm or algorithms topic that we didn't cover in the mainline class.

### Implementing and Testing

In order to solidify your understanding of the material and improve your ability as a coder, we will be implementing many of our algorithms.  We'll focus on creating unit tests as a way to create more maintainable and correct code.

## Algorithms in the World

Choose a category of algorithms from the list below (or make up your own).   Try to choose ones that you are less familiar with (or maybe start with a familiar one and then choose one less so).  For each category:

* Come up with a basic definition of what sorts of problems the algorithm is designed to solve.
* List the sorts of metrics that an algorithm designer might care about when creating an algorithm of this type.
* List at least two examples of how algorithms of this type are used in society (applications).

The list of general algorithm classes is below.
* Data Compression (lossless or lossy)
* Collaborative Filtering (e.g., as used in recommender systems)
* Encryption
* Routing (e.g., of Internet traffic or for navigation instructions)
* [Task Assignment](https://en.wikipedia.org/wiki/Assignment_problem)
* Sorting
* Matrix Multiplication
* Fourier Analysis
* (come up with your own.... there are so many!)


> Bonus question: list all of the algorithms that you and your team have interacted with since you got up this morning.

## Peak Finding

> Credit to MIT Open Courseware 6.006 for this problem

Suppose we have a list of numbers represented as a sequence $$a_1, \ldots, a_n$$ with $$n \geq 2$$.  For any element that isn't either the first or the last element of this sequence, we say that element $$i$$ is a peak if and only if $$a_i \geq  a_{i-1}~\mbox{and}~a_i \geq a_{i+1}$$.  For the elements at the ends of the sequence, we say that $$a_1$$ is a peak if and only $$a_1 \geq a_2$$ and $$a_n$$ is a peak if and only if $$a_n \geq a_{n-1}$$.


With some folks around, you answer the following questions:

1. Get a feel for the condition written above.  Draw a few test cases.  When does a peak exist?  When does it not?
2. Come up with a very simple algorithm to return the position, $$i$$, of a peak in a list of numbers (provided one exists).  How many elements do you have to check to determine if you have a peak?
3. See if you can create an algorithm to find a peak faster than your first algorithm.  What techniques might be able to speed things up.  Make an argument that your algorithm is correct and see if you can start to understand how you might prove this more formally.
4. If we changed the condition of a peak to the definition below, would your algorithm in question 3 still work?

> Definition 2: For any element that isn't either the first or the last element of this sequence, we say that element $$i$$ is a peak if and only if $$a_i > a_{i-1}~\mbox{and}~a_i > a_{i+1}$$.  For the elements at the ends of the sequence, we say that $$a_1$$ is a peak if and only $$a_1 > a_2$$ and $$a_n$$ is a peak if and only if $$a_n < a_{n-1}$$.

## Turning in your work

Please fill out [the Canvas survey](https://olin.instructure.com/courses/761/quizzes/2094) to complete your assignment for today.  These surveys are not intended to be heavy weight.
