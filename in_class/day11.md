---
title: "Day 11: More Dynamic Programming"
toc_sticky: true
published: true
---

## Dynamic Programming General Structure

The book Introduction Algorithms by Cormen, Leiserson, Rivest, and Stein has the following description of the dynamic programming approach.

1. Characterize the structure of an optimal solution.
2. Recursively define the value of an optimal solution.
3. Compute the value of an optimal solution, typically in a bottom-up fashion.
4. Construct an optimal solution from computed information.

## Practice Problems

(You won't be able to do all of these.  This is just for reference.  Turn in what you'd like.)

> **Exercise 1**
>
> Change making.  Given $n$ different coin denominations worth $x_1, x_2, \ldots, x_n$ cents and a target value of $D$ cents, determine how many different ways you can combine the different coins to add up exactly $D$ cents.  You can use as many of each denomination of coin as you'd like.  Solve the problem using dynamic programming where you create a table to store the solutions to the problem, fill out rows and/or columns of the table that correspond to small or easy to solve instances of the problem, and then determine a rule for filling out the rest of the table.  Finally, determine how you would compute the solution to your original problem by referencing a particular cell in your table.
{: .notice--success}

> **Exercise 2**
> 
> The Longest Common Subsequence (LCS) problem asks: given two sequences, what is the longest sequence that appears in both of them in the same order? In other words, it’s the longest sequence that you can form by deleting some elements (without changing the order) from each of the two original sequences.
{: .notice--success}

> **Exercise 3**
> 
> Revisit the maximum contiguous subsequence problem from last class.  Instead of using divide and conquer, use dynamic programming.
{: .notice--success}


> **Exercise 4**
>
> In the 0–1 Knapsack problem, we are given a set of items, each with a weight and a value, and we need to determine the number of each item to include in a collection so that the total weight is less than or equal to a given limit and the total value is as large as possible.
> 
> Please note that the items are indivisible; we can either take an item or not (0-1 property). For example,
>
> Input:
>  - value = [ 20, 5, 10, 40, 15, 25 ]
>  - weight = [ 1, 2, 3, 8, 7, 4 ]
>  - W = 10
> 
> Output: Knapsack value is 60 value = 20 + 40 = 60 (weight = 1 + 8 = 9 < W)
{: .notice--success}