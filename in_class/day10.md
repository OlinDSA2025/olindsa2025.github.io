---
title: "Day 10: Divide and Conquer"
toc_sticky: true
published: false
---

## Course Feedback Activity Coming Next Time

It's about that time when it would be really useful for us to do a feedback activity.  I'm not quite ready to run it today, and I want to prioritize helping you get going on the homework.  We'll do the feedback activity next class.  If you have some spare brain cycles, think a bit about the positives, negatives, and ideas for improvement with respect to the class.

## Divide and Conquer and Intro to Dynamic Programming

Today is going to primarily be about getting practice with divide and conquer algorithms.  We'll also throw in a recursive algorithm that doesn't quite fit the mold of divide and conquer.

**Problem 1** Solve the maximum contiguous subsequence problem by determining a divide and conquer algorithm to solve it.  Once you have the algorithm, use the master theorem to determine its runtime.

The maximum contiguous sub-sequence problem involves taking an input list $x_1, \ldots, x_n$ and determining two index values $i$ and $j$ such that $\sum_{k=i}^j x_k$ is as large as possible.

**Problem 2** Multiplying square matrices.  Given two square matrices, $A$ and $B$, each of size $n \times n$.  Determine a divide and conquer method for determining the product of the two matrices $C = AB$.  To solve the problem, you can make use of the technique of [block matrix multiplication](https://en.wikipedia.org/wiki/Block_matrix#Block_matrix_multiplication).  Show that the running time you get from using block matrix multiplication is the same as you get from the traditional method of matrix multiplication (the one you learned about in math class).

## Dynamic Programming

The book Introduction Algorithms by Cormen, Leiserson, Rivest, and Stein has the following description of the dynamic programming approach.

1. Characterize the structure of an optimal solution.
2. Recursively define the value of an optimal solution.
3. Compute the value of an optimal solution, typically in a bottom-up fashion.
4. Construct an optimal solution from computed information.

We'll see if we can understand how this applies to the Leetcode problem of [Minimum Cost Climbing Stairs](https://leetcode.com/problems/min-cost-climbing-stairs/description/).

> You are given an integer array cost where ``cost[i]`` is the cost of $i$th step on a staircase. Once you pay the cost, you can either climb one or two steps.
> You can either start from the step with index 0, or the step with index 1.
> Return the minimum cost to reach the top of the floor.
> 
> Example 1:
>  - Input: cost = [10,15,20]
>  - Output: 15
>
> Example 2:
>   - Input: cost = [1, 100, 1, 1, 1, 100, 1, 1, 100, 1]
>   - Output: 6


**Problem 3:** Change making.  Given $n$ different coin denominations worth $x_1, x_2, \ldots, x_n$ cents and a target value of $D$ cents, determine how many different ways you can combine the different coins to add up exactly $D$ cents.  You can use as many of each denomination of coin as you'd like.  Solve the problem using dynamic programming where you create a table to store the solutions to the problem, fill out rows and/or columns of the table that correspond to small or easy to solve instances of the problem, and then determine a rule for filling out the rest of the table.  Finally, determine how you would compute the solution to your original problem by referencing a particular cell in your table.