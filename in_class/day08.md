---
title: "Day 8: A-Star Search and Intro to Sorting"
toc_sticky: true
---

This is a work in progress.


## A-Star Search

## Sorting

### Selection sort

### Bubble Sort

### Merge sort

### Heap sort

## Complexity of Sorting Algorithms

### Analyzing Selection Sort

Let's start by analyzing the worst case running time of selection sort.  Compute the number of operations necessary to run selection sort in the worst case.  Determine $\Theta$.

### Analyzing Merge Sort

### Master Theorem

A generalizable recipe for analyzing recursive algorithms like this is the [master theorem](https://en.wikipedia.org/wiki/Master_theorem_(analysis_of_algorithms).  Reanalyze merge sort using the master theorem.  You may find the following special cases of the master theorem useful.

$T(n) = a T(n/b) + n$

Has a run time $\Theta(n^{\log_{b}{a}})$ if $\log_{b}{a} > 1$.

Has a run time $\Theta(n \log^{k+1} n)$ if $n^{\log_{b}{a}} \log{k} = \Theta(n)$.