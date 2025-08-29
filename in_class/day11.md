---
title: "Day 11: More Dynamic Programming"
toc_sticky: true
published: false
---

## Course Feedback Activity (total: 30 minutes)

2 minutes (individual): think back to your learning goals for the course.  Are your learning goals now similar or have they shifted?

So far the activities of DSA have fallen into the following three categories.

1. (Approximately) weekly assignments
2. Instructor-led activities (e.g., to introduce material or go over a problem)
3. Group-work in-class (e.g., on problems in the daily assignment)

One thing we haven't done yet is an open-ended project, which will be coming in the latter half of the class.

8 minutes (individual): With respect to the three main activities we've done thus far, please list some pluses and deltas.

5 minutes (group): We'll write pluses and deltas on the white boards.

5 minutes (group): Read what other people wrote and upvote or downvote them.

10 minutes (group): We'll pick a few themes to discuss verbally as a group.


## Fibonacci Revisited

As a reminder from last time, we motivated the idea of a dynamic programming by considering the technique of [memoization](https://en.wikipedia.org/wiki/Memoization) where we maintain a lookup table of previously performed computations so that before making a recursive call, we check whether we have computed the solution before, and if so, return the pre-computed value.

The idea of dynamic programming is quite similar, except that instead of using recursion as a means to fill in our precomputed values, we do so iteratively.

## Dynamic Programming General Structure

The book Introduction Algorithms by Cormen, Leiserson, Rivest, and Stein has the following description of the dynamic programming approach.

1. Characterize the structure of an optimal solution.
2. Recursively define the value of an optimal solution.
3. Compute the value of an optimal solution, typically in a bottom-up fashion.
4. Construct an optimal solution from computed information.

## Practice Problems

(You won't be able to do all of these.  This is just for reference.  Turn in what you'd like.)

**Problem 1:** Change making.  Given $n$ different coin denominations worth $x_1, x_2, \ldots, x_n$ cents and a target value of $D$ cents, determine how many different ways you can combine the different coins to add up exactly $D$ cents.  You can use as many of each denomination of coin as you'd like.  Solve the problem using dynamic programming where you create a table to store the solutions to the problem, fill out rows and/or columns of the table that correspond to small or easy to solve instances of the problem, and then determine a rule for filling out the rest of the table.  Finally, determine how you would compute the solution to your original problem by referencing a particular cell in your table.

**Problem 2:**  Longest Common Subsequence Problem
The Longest Common Subsequence (LCS) problem is finding the longest subsequence present in given two sequences in the same order, i.e., find the longest sequence which can be obtained from the first original sequence by deleting some items and from the second original sequence by deleting other items.

**Problem 3:**
In the 0–1 Knapsack problem, we are given a set of items, each with a weight and a value, and we need to determine the number of each item to include in a collection so that the total weight is less than or equal to a given limit and the total value is as large as possible.

Please note that the items are indivisible; we can either take an item or not (0-1 property). For example,

> Input:
>  - value = [ 20, 5, 10, 40, 15, 25 ]
>  - weight = [ 1, 2, 3, 8, 7, 4 ]
>  - W = 10
> 
> Output: Knapsack value is 60 value = 20 + 40 = 60 (weight = 1 + 8 = 9 < W)
