---
title: "Day 8: A-Star Search and Intro to Sorting"
toc_sticky: true
---

## A-Star Search

Before we turn the page to the next topic of the course, sorting, I want to talk about a really another graph traversal algorithm, [A-star](https://en.wikipedia.org/wiki/A*_search_algorithm) search.

What's beautiful about a-star search is that it can drastically speed up dijkstra's algorithm in certain cases by cutting down on search certain paths.

Before showing the algorithm, we should realize that A-star is solving a bit different problem than Dijkstra's.  A-star is specifically solving finding a path from a given start vertex to the goal (rather than to any possible destination as we did in Dijkstra's).

The key insight of A-star is to make use of a heuristic function that serves as a lower in terms of the cost to move from a particular node in the graph to the goal.  Let's do some work at the board to understand what a heuristic means and under what conditions it can work with A-star (this is known as the [admissibility condition](https://en.wikipedia.org/wiki/Admissible_heuristic)).

We use the notation $h(v)$ denotes the lower bound on traversing from $v$ to the goal node.  Given this construction, we can modify our pseudocode for Dijkstra's algorithm from last time to get the A-star algorithm.

```
for each vertex, v that is not the source:
    prev[v] ← UNDEFINED
    dist[v] ← INFINITY
    queue.addWithPriority(v, INFINITY)

dist[source] ← 0
f[source]  ← h(source)
queue.addWithPriority(source, f[source])

while queue is not empty:
    u ← vertex in queue with min priority
    remove u from queue
    if u == goal:
        // reconstruct shortest path from prev
        return
    for each neighbor v of u still in queue:
        alt ← dist[u] + edgecost(u, v)
        if alt < dist[v]:
            dist[v] ← alt
            queue.changePriority(v, alt + h(v))
            prev[v] ← u
```

## Sorting

The [sorting problem](https://en.wikipedia.org/wiki/Sorting_algorithm) typically involves taking an input list of items and rearranging them so that the resultant list contains the items in some order.  A simple example would be arranging numbers in ascending order.  There are many variants and settings to this problem, but for this part of the class, let's imagine that we are simply taking lists of integers and sorting them in ascending order.

We're going to learn about three of the many sorting algorithms today.

### Selection sort

[Selection sort](https://en.wikipedia.org/wiki/Selection_sort) is a very simple algorithm.  We continuously look for the minimum value in the part of the list that is unsorted and then place that element at the front.  Let's develop the pseudocode for this and prove that the algorithm yields a sorted list.

### Merge sort

[Merge sort](https://en.wikipedia.org/wiki/Merge_sort) is a divide and conquer approach to sorting a list.  We'll develop some pseudocode for this one together.

The basic idea is to chop our list in two, sort both halves, and then reassemble the two sorted halves into a sorted whole.

### Heap sort

This one is pretty awesome.  You just insert all of your values into a binary min heap and then take them all out using the ``getMin()`` function.

## Complexity of Sorting Algorithms

### Analyzing Selection Sort

Let's start as a group by analyzing the worst case running time of selection sort.  Compute the number of operations necessary to run selection sort in the worst case.  Determine $\Theta$.

### Analyzing Heap Sort

**Problem 1:** Determine the $\Theta$ of heap sort.

### Analyzing Merge Sort

**Problem 2:** Determine the $\Theta$ of merge sort.

### Master Theorem

A generalizable recipe for analyzing recursive algorithms like this is the [master theorem](https://en.wikipedia.org/wiki/Master_theorem_(analysis_of_algorithms)).  

**Problem 3:** Reanalyze merge sort using the master theorem.  You may find the following special cases of the master theorem useful.

$T(n) = a T(n/b) + n$

Has a run time $\Theta(n^{\log_{b}{a}})$ if $\log_{b}{a} > 1$.

Has a run time $\Theta(n \log^{k+1} n)$ if $n^{\log_{b}{a}} \log{k} = \Theta(n)$.