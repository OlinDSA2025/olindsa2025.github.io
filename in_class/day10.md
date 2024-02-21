---
title: "Day 10: Divide and Conquer"
toc_sticky: true
---

## Divide and Conquer and Intro to Dynamic Programming

Today is going to primarily be about getting practice with divide and conquer algorithms.  We'll also throw in a few other recursive algorithms (that may not quite fit the mold of divide and conquer) as well.

**Problem 1** Solve the maximum contiguous subsequence problem by determining a divide and conquer algorithm to solve it.  Once you have the algorithm, use the master theorem to determine its runtime.

The maximum contiguous sub-sequence problem involves taking an input list $x_1, \ldots, x_n$ and determining two index values $i$ and $j$ such that $\sum_{k=i}^j x_k$ is as large as possible.

**Problem 2** Multiplying square matrices.  Given two square matrices, $A$ and $B$, each of size $n \times n$.  Determine a divide and conquer method for determining the product of the two matrices $C = AB$.  To solve the problem, you can make use o of the technique of [block matrix multiplication](https://en.wikipedia.org/wiki/Block_matrix#Block_matrix_multiplication).