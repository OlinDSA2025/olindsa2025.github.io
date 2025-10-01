---
title: "Day 9: More Sorting and More Divide and Conquer"
toc_sticky: true
published: true
---
Last class we saw heap sort, merge sort, and selection sort, but there are quite a few more to learn about. Today we'll learn a few more sorting algorithms, but we'll also formally introduce the master theorem as a generalizable way to find $\Theta$ for divide and conquer algorithms.

## Master Theorem

A generalizable recipe for analyzing recursive algorithms like this is the [master theorem](https://en.wikipedia.org/wiki/Master_theorem_(analysis_of_algorithms)).

Let's see if we can apply this to determining the complexity of merge sort from last class.  Before applying the master theorem, we need to make sure we are comfortable with the idea of a recurrence relation.  A recurrence relation relates the runtime of an algorithm on input of size $n$ (denoted as $T(n)$) to the runtime of the algorithm on smaller problem sizes (less than $n$).  For example, in the case of merge sort we can write the following recurrence relation.

> $T(n) = 2 T(\frac{n}{2}) + n$
{: .notice--warning}

Let's make sure we understand this exactly.  The term on the left is the runtime of sorting $n$ items with merge sort.  The runtime is based on two parts.  The first part is the recursive piece, which consists of merge sorting two lists of size $\frac{n}{2}$.  The second part is the work needed to reassemble the sorted lists back into an overall sorted list (the merge step), which takes time $n$.

The master theorem provides a recipe for us to solve this recurrence relation (meaning determine a function $T(n)$ that satisfies the equation).  The master theorem solves recurrence relations of the following form.

> $T(n) = a T(\frac{n}{b}) + f(n)$
{: .notice--warning}

You should see that in our case (of merge sort), $a=2$, $b=2$, and $f(n) = n$.
In order to apply the master theorem, we compute a value called $c_{crit} = \log_{b}{a}$.  Plugging in $a=2$ and $b=2$, we get $c_{crit} = \log_2{2} = 1$.

Now, we have to determine which of the three cases of the master theorem apply.  Let's make sure we remember what our old friend $O$, $\Omega$, and $O$ mean.  I'll state these definitions somewhat loosely, trusting you to go back to the original definitions for the exact meanings.
* $f(n) = O(g(n))$ means that $g(n)$ bounds $f(n)$ from above for large $n$.
* $f(n) = \Omega(g(n))$ means that $g(n)$ bounds $f(n)$ from below for large $n$.
* $f(n) = \Theta(g(n))$ means that $g(n)$ bounds $f(n)$ from both above and below (meaning $f(n) = O(g(n))$ and $f(n) = \Omega(g(n))$).

Okay, so here are the three cases of the master theorem.  I'll list the condition, state if merge sort meets it, and if it does, show the runtime.

Case 1: $n = O(n^c)$ for some $c < 1$.  **Nope can't be true.  If $c$ is less than 1 it grows more slowly than $n$ and cannot be bound it from above.**

Case 2: $n = \Theta(n (\log n)^k)$ for some $k \geq 0$.  **Yes!  If we set $k=0$ then the $\log$ drops out and we are left with $n = \Theta(n)$, which is true.**

Case 3: $n = \Omega(n^c)$ for some $c > 1$.  **Nope.  If we set $c$ bigger than 1 it will grow faster than $n$ and won't bound $n$ from below.**

Okay, so case 2 is the winner.  The runtime as dictated by case 2 is $T(n) = \Theta(n^{c_{crit}} (\log n)^{k+1}) = \Theta(n \log n)$ (since $c_{crit} = 1$ and $k = 0$).

> **Exercise 1:** Reanalyze binary search using the master theorem.  Hint: first find a recurrence relation, and then try to find the case that matches.
{: .notice--success}


> **Exercise 2:** Choose a few problems from the homework and do them together.
{: .notice--success}

## Quick Sort

[Quick Sort](https://en.wikipedia.org/wiki/Quicksort) is one of the most commonly used sorting algorithms.

There are quite a few ways to implement Quick Sort, but the general idea is the following:
* For an unsorted list, choose an element of the list as your pivot value, $p$.
* Iterate through the elements of your list ($x_1, x_2, \ldots, x_n$), swapping as needed, until the pivot element is located at index $i$ and $x_j < x_i$ if $j < i$ and $a_j \geq a_i$ if $j \geq i$.
* Sort range of elements that are before the pivot in the list and those after the pivot recursively.

Let's look at the [algorithm visualization](https://visualgo.net/en/sorting) (you can choose quick or ``quick sort`` or ``random quick sort``).

Analyzing the runtime of this algorithm is a bit tricky.  Let's consider a specific case of always choosing the first element as the pivot.  Let's see what happens with quick sort with this pivot selection rule.

## Radix Sort

[Radix sort](https://en.wikipedia.org/wiki/Radix_sort) (also called bucket sort) is an interesting algorithm where we don't perform an explicit comparisons between elements in our list.  We instead sort, e.g. if we are sorting integers, based on comparing the ones digits, then the tens digit, etc.  Let's check out [the visualization of Radix sort](https://visualgo.net/en/sorting) at our favorite website!

## The Speed Limit for Comparison-Based Sorting

(my apologies, this might be hard to understand without having taken discrete math, but we'll try).

There's a theorem that states that any algorithm for sorting that works by comparing elements of the list to each other has running time of $\Omega(n \log n)$ (that is the running time can be bounded below by $n \log n$).

To understand this we can think of the problem of sorting as determining which of the $n!$ possible permutations of a list is the right one to obtain the list in sorted order.

We can then think of creating a tree where at each level of the tree we perform a comparison to try to eliminate some of the $n!$ possible permutations.

Let's say each of our comparison perfectly divides the number of possible permutations that go each direction in our tree in half.  This is what the picture would look like.

<div class="mermaid">
graph TD
  r[n!] --> b[n!/2]
  r --> c[n!/2]
  b --> e[n!/4]
  b --> f[n!/4]
  c --> g[n!/4]
  c --> h[n!/4]
</div>

We'll go over the details as a class, but we will have to use one equation that we won't prove: $\log n! = \Omega(n \log n)$.

