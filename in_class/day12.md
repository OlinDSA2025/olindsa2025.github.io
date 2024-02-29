---
title: "Day 12: Work / Practice on Dynamic Programming"
toc_sticky: true
---

Today, you have the option of either working on the homework or doing some more practice problems with dynamic programming.  You do not have to submit anything for today (there will be no day 12 assignment).

## More Practice With Dynamic Programming

Let's start off with the last two problems from day 11.

**Longest Common Subsequence Problem**
The Longest Common Subsequence (LCS) problem is finding the longest subsequence present in given two sequences in the same order, i.e., find the longest sequence which can be obtained from the first original sequence by deleting some items and from the second original sequence by deleting other items.

**0–1 Knapsack problem:**
In the 0–1 Knapsack problem, we are given a set of items, each with a weight and a value, and we need to determine the number of each item to include in a collection so that the total weight is less than or equal to a given limit and the total value is as large as possible.  You can use more than one of each item, but you can't use a fraction (the items are indivisible; we can either take an item or not (0-1 property)). For example,

> Input:
>  - value = [ 20, 5, 10, 40, 15, 25 ]
>  - weight = [ 1, 2, 3, 8, 7, 4 ]
>  - W = 10
>
> Output: Knapsack value is 60 value = 20 + 40 = 60 (weight = 1 + 8 = 9 < W)

** After you solve this: how does this solution compare to the change-making problem **

To find additional problems, you can search for terms like "dynamic programming sample problems".  You will get some like:
* [Longest Increasing Subsequence](https://www.techiedelight.com/longest-increasing-subsequence-using-dynamic-programming/)
* [Matrix Chain Multiplication](https://www.techiedelight.com/matrix-chain-multiplication/)