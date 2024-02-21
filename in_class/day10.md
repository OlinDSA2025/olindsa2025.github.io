---
title: "Day 10: Divide and Conquer"
toc_sticky: true
---

## Divide and Conquer and Intro to Dynamic Programming

Today is going to primarily be about getting practice with divide and conquer algorithms.  We'll also throw in a few other recursive algorithms (that may not quite fit the mold of divide and conquer) as well.

**Problem 1** Solve the maximum contiguous subsequence problem by determining a divide and conquer algorithm to solve it.  Once you have the algorithm, use the master theorem to determine its runtime.

The maximum contiguous sub-sequence problem involves taking an input list $x_1, \ldots, x_n$ and determining two index values $i$ and $j$ such that $\sum_{k=i}^j x_k$ is as large as possible.

**Problem 2** Multiplying square matrices.  Given two square matrices, $A$ and $B$, each of size $n \times n$.  Determine a divide and conquer method for determining the product of the two matrices $C = AB$.  To solve the problem, you can make use o of the technique of [block matrix multiplication](https://en.wikipedia.org/wiki/Block_matrix#Block_matrix_multiplication).

**Problem 3** Change making.  Given $n$ different coin denominations worth $x_1, x_2, \ldots, x_n$ cents and a target value of $D$ cents, determine how many different ways you can combine the different coins to add up exactly $D$ cents.  You can use as many of each denomination coins as you'd like.  Hint: this algorithm can work with a recursive solution, but it won't be a traditional divide and conquer.

## Dynamic Programming

The book Introduction Algorithms by Cormen, Leiserson, Rivest, and Stein has the following description of the dynamic programming approach.

1. Characterize the structure of an optimal solution.
2. Recursively define the value of an optimal solution.
3. Compute the value of an optimal solution, typically in a bottom-up fashion.
4. Construct an optimal solution from computed information.

Let's see if we can understand how to apply this strategy to our change-making problem.