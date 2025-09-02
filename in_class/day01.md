---
title: "Day 1: Course Intro and Welcome to DSA"
toc_sticky: true
---

## Course Structure and Major Topics

> Time: 2:50pm-3:05pm

The goal of this course is for you to learn how to frame problems using the language of computation and select appropriate data structures and algorithms to solve them.  We'll get more into what we mean by framing problems later (there is an example later today), but for now I want to focus on the sorts of problems we will be tackling and the algorithmic strategies we will be using to solve them.

### Data Structures

* Data structures as supports for algorithms.  Ultimately, data structures are useful to solve certain problems.  There are a number of properties we might care about when we select a data structure.  Can we brainstorm some as a class?
* We'll be learning about basic linked data structures (linked lists, stacks, queues), data structures to represent graphs and trees (e.g., binary search trees or heaps), and data structures that use hashing to index and retrieve data.

### Algorithmic Design Patterns

While each algorithm must be tuned to the particular problem being solved, there are general algorithm types that we will encounter (e.g., some algorithms work by breaking a larger problem into smaller instances, some use a greedy approach, others are based on backtracking or graph search).

### Analyzing Algorithms

We want to develop ways to talk about the computational and spatial complexity of algorithms.  We can look at these factors with both theoretical (e.g., doing some analysis to understand how long the code might run for based on the problem size) and empirical tools (e.g., measuring the actual time it takes an algorithm to run on a computer).

### Specific Algorithms

Of course, we will learn about specific algorithms.  We'll see algorithms from graph theory, string matching, bioinformatics, sorting, matrix multiplication, backtracking, and artificial intelligence.

### Algorithmic Deep Dive

You'll be able to customize the course by taking a deep dive into a new algorithm or algorithms topic that we did not cover in the class.

### Implementation and Testing

In order to solidify your understanding of the material and improve your ability as a developer, we will be implementing many of our algorithms and data structures.  We'll focus on creating unit tests as a way to create more maintainable and correct code.

## Algorithms in the World

> Time: 3:05pm-3:30pm

Choose a category of algorithms from the list below (or make up your own). You are not supposed to know all (or any) of these already!  I encourage you to choose ones you don't know about and do some research!  Alternatively, maybe warm up with one you are more familiar with and then choose one less so.  For each category you choose to look into:

* Come up with a basic definition of what types of problems that the algorithm can solve.
* List the metrics that an algorithm designer might care about when creating an algorithm of this type.
* List at least two examples of how algorithms of this type are used in the world (applications).

Some examples of algorithms are listed below.
* Data Compression (lossless or lossy)
* Collaborative filtering (e.g., as used in recommender systems)
* Encryption
* Routing (e.g., of Internet traffic or for navigation instructions)
* [Task Assignment](https://en.wikipedia.org/wiki/Assignment_problem)
* Sorting
* Matrix Multiplication
* Fourier Analysis
* Semantic search
* (come up with your own.... there are so many!)

> Bonus question: list all the algorithms that you and your team have interacted with since you got up this morning.

## Discussion of Learning Strategies and Oral Quizzes

> Time: 3:30pm-3:50pm

Next, I want to discuss two interrelated issues.  The first is how you can work in a way that best supports your learning this semester.  The second is how I provide an assessment structure that provides you with useful feedback as to how well you are meeting these goals.

While there are many aspects of assessment in this course, for now I want to focus on something new I'm trying this semester.  Twice this semester, I will meet with each of you for an oral quiz (each quiz is worth 10% of your grade).  My hope is that this structure will give you a better measurement of your progress over the semester.  Part of my decision is also based on mitigating what I feel are ways in which AI-based coding assistants might hinder learning (e.g., if they are used as answer generators rather than coaches).  I'm not ready to nail down the full design of these quizzes, but here are some preliminary thoughts.


| *Activity* | *What's Being Assessed* |
| You are given a problem to solve. As you work towards a solution, you show / discuss your thought process. | Your ability to select appropriate data structures and algorithms to solve a novel problem. |
| You are asked to explain a section of code from one of your submitted assignments. | Your ability to internalize and be able to verbalize to others the coding choices you made. |
| You are asked to give a whiteboard talk explaining one of the class concepts. | Your fluency with the concepts in the course, your ability to distill down the important bits, and your ability to communicate clearly about course concepts. |
| You are given an implementation of a particular algorithm and you must work through whether the code is correct. If it is not correct, you may suggest corrections. | Your ability to comprehend code that you didn't write and assess its correctness. |

With some folks around you, please discuss the following.
1. What are some learning strategies that have worked particularly well for you in the past?  Do you think they will work well in this course?
2. Will you use AI-based coding assistants in this course?  How will you use them to ensure you are getting the knowledge you'd like from the course?
3. In reaction to the table above, what other activities would be useful to include in an oral quiz and what skill would they be assessing?

## Having Some Fun With Algorithms

> 3:50pm - 4:20pm

Choose one of the problems below to work through with a group of people sitting near you.  If you finish one problem, move onto the other.  The goal here is not for you to be able to jump right to the answer, but instead, I encourage you to break down the problem and discuss it with those around you.

### Peak Finding

> Credit to MIT Open Courseware 6.006 for this problem

Suppose we have a list of numbers represented as a sequence $a_1, \ldots, a_n$ with $n \geq 2$.  For any element that isn't either the first or the last element of this sequence, we say that element $i$ is a peak if and only if $a_i \geq  a_{i-1}~\text{and}~a_i \geq a_{i+1}$.  For the elements at the ends of the sequence, we say that $a_1$ is a peak if and only $a_1 \geq a_2$ and $a_n$ is a peak if and only if $a_n \geq a_{n-1}$.


With some folks around, you answer the following questions:

<ol>
<li>Unpack the notation.  Write out a simple test case and label the values with the appropriate notation (e.g., write a list of numbers and draw an arrow to the first that says $a_1$, to the second that says $a_2$, etc.</li>
<li>Get a feel for the condition written above.  Draw a few test cases.  When does a peak exist?  When does it not?</li>
<li>Come up with a very simple algorithm to return the position, $i$, of a peak in a list of numbers (provided one exists).  How many elements do you have to check to determine if you have a peak?</li>
<li>See if you can create an algorithm to find a peak faster than your first algorithm.  What techniques might be able to speed things up.  Make an argument that your algorithm is correct and see if you can start to understand how you might prove this more formally.

<br/>
<button onclick="HideShowElement(&quot;HideShow1&quot;)">Show / Hide Hint 1</button>
<div id="HideShow1" style="display:none">
You should think about breaking the problem down into simpler instances.
</div>

<br/>
<button onclick="HideShowElement(&quot;HideShow2&quot;)">Show / Hide Hint 2</button>
<div id="HideShow2" style="display:none">
Think recursively.  What test can you perform that would allow you to recurse on a sequence half as large as the one you started with?
</div></li>
<li>If we changed the condition of a peak to the definition below, would your algorithm in question 3 still work?</li>
</ol>

> Definition 2: For any element that isn't either the first or the last element of this sequence, we say that element $i$ is a peak if and only if $a_i > a_{i-1}~\text{and}~a_i > a_{i+1}$.  For the elements at the ends of the sequence, we say that $a_1$ is a peak if and only $a_1 > a_2$ and $a_n$ is a peak if and only if $a_n < a_{n-1}$.

### Optimal Roadtripping

You are planning a road trip of $N$ miles.  Your electric car has a range of $M$ miles.  There are charging stations located at mile $a_1, a_2, a_3, \ldots, a_k$ (as measured from the start of the route).  Determine a procedure to figure out the minimum number of recharges you have to make in order to complete the road trip.

<button onclick="HideShowElement(&quot;HideShow3&quot;)">Show / Hide Hint 1</button>
<div id="HideShow3" style="display:none">
Start by thinking about the first decision you have to make (where to make your first recharging stop).  Is there a best place to stop?
</div>

<button onclick="HideShowElement(&quot;HideShow4&quot;)">Show / Hide Hint 2</button>
<div id="HideShow4" style="display:none">
Assuming that you recharge completely each time you choose to stop, does it ever make sense to stop at an earlier charging station than you could have reached?
</div>

## Orientation to Assignment 1

> 4:20pm - 4:25pm

Let me show you [the first assignment](/assignments/assignment_01) (due next Thursday).

## Turning in your work

> 4:25pm - 4:30pm

Please fill out [the Canvas survey](https://olin.instructure.com/courses/940/quizzes/2577) to complete your assignment for today.  These surveys are not intended to be heavy -weight.
