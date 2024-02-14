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

TODO

## Radix Sort

[Radix sort](https://en.wikipedia.org/wiki/Radix_sort) (also called bucket sort) is an interesting algorithm where we don't perform an explicit comparisons between elements in our list.  We instead sort, e.g. if we are sorting integers, based on comparing the ones digits, then the tens digit, etc.  Let's check out [the visualization of Radix sort](https://visualgo.net/en/sorting) at our favorite website!

## More Practice With the Master Theorem

Before getting started, let's dig into the [master theorem](https://en.wikipedia.org/wiki/Master_theorem_(analysis_of_algorithms)) to make sure we really understand it.

**Problem 1** Binary search can be applied to finding an element in a sorted list, by progressively eliminating half of the elements to be searched on each iteration.  Make sure you understand binary search, write a recurrence relation, and solve it using the master theorem.

**Problem 2** Maximum Contiguous Subsequence (need to write this up)

For more practice we can go to the problems assigned on the homework.