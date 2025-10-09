---
title: "Day 11: More Dynamic Programming"
toc_sticky: true
published: true
---

## Oral Quiz 1

First, sign up for a time to meet with me (see link on Canvas).  You need to make it to this time unless something catastrophic happens.

Here are some things I noticed in the practice quizzes.
* When determining runtimes (non divide and conquer), figure out what are the main steps you have to perform, determine how many operations each step takes, and then add up the total number of operations.  Conclude by converting to $\Theta$.
* For divide and conquer algorithms, be ready to draw a tree diagram or use the master theorem.
* When reading code, I found that people who talked through what the code as doing in greater detail had an easier time giving the relevant details.
* For graph search (e.g., Dijkstra), make sure you understand what the variables represent (e.g., ``dist[v]`` returns the shortest known path from the source to vertex ``v``).

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
> Change making.  Given $n$ different coin denominations worth $x_1, x_2, \ldots, x_n$ cents and a target value of $D$ cents, determine the minimum number of coins you can use to add up exactly $D$ cents.  You can use as many of each denomination of coin as you'd like.  Solve the problem using dynamic programming where you create a table to store the solutions to various subproblems, fill out rows and/or columns of the table that correspond to small or easy to solve subproblem, and then determine a rule for filling out the rest of the table.  Finally, determine how you would compute the solution to your original problem by referencing a particular cell in your table.
> 
> Bonus question (if you have time): can you modify your approach to count the number of ways you can make change for $D$ cents.
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