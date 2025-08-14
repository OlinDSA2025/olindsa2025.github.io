---
title: "Day 9: More Sorting and More Divide and Conquer"
toc_sticky: true
---
Last class we saw heap sort, merge sort, and selection sort, but there are quite a few more to learn about.

## Quick Sort

[Quick Sort](https://en.wikipedia.org/wiki/Quicksort) is one of the most commonly used sorting algorithms.

There are quite a few ways to implement Quick Sort, but the general idea is the following:
* For an unsorted list, choose an element of the list as your pivot value, $p$.
* Iterate through the elements of your list, swapping as needed, until the pivot element is positioned at position $i$ and $a[j] < a[i]$ if $j < i$ and $a[j] \geq a[i]$ if $j \geq i$.
* Sort range of elements that are before the pivot in the list and those after the pivot recursively.

Let's look at the [algorithm visualization](https://visualgo.net/en/sorting) (you can choose quick or ``quick sort`` or ``random quick sort``).

Analyzing the runtime of this algorithm is a bit tricky.  Let's consider a specific case of always choosing the first element as the pivot.  Let's see what happens with quick sort with this pivot selection rule.

## The Speed Limit for Comparison-Based Sorting

(my apologies, this might be hard to understand without having taken discrete math, but we'll try)

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

## Radix Sort

[Radix sort](https://en.wikipedia.org/wiki/Radix_sort) (also called bucket sort) is an interesting algorithm where we don't perform an explicit comparisons between elements in our list.  We instead sort, e.g. if we are sorting integers, based on comparing the ones digits, then the tens digit, etc.  Let's check out [the visualization of Radix sort](https://visualgo.net/en/sorting) at our favorite website!

## More Practice With the Master Theorem

Before getting started, let's dig into the [master theorem](https://en.wikipedia.org/wiki/Master_theorem_(analysis_of_algorithms)) to make sure we really understand it.

**Problem 1** Binary search can be applied to finding an element in a sorted list, by progressively eliminating half of the elements to be searched on each iteration.  Make sure you understand binary search, write a recurrence relation, and solve it using the master theorem.


**Problem 2 (option 1)** For more practice we can go to the problems assigned on the homework.

**Problem 2 (option 2)** If you'd rather try a new problem.  See if you can solve the maximum contiguous subsequence problem by determining a divide and conquer algorithm to solve it and then using the master theorem to find its runtime.