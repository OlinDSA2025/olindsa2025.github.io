---
title: Assignment 8
toc_sticky: true 
---

## Binary Search Trees

For this assignment you have two options.

### Option 1: Implement Part of Red-Black Trees

Create an implementation of Red-Black trees that supports at least the following operations:
* Insert
* Lookup (exact)
* Check invariants (makes sure that the Red-Black tree properties are maintained)

**Note: feel free to make your implementation work for just one type of data (I used Ints).  You could make it generic, but it's not necessary.**

If you want to go all out with this, you could implement remove also.

Advice / references:
* I was able to port [Michael Sambol's implementation from Python to Kotlin](https://github.com/msambol/dsa/blob/master/trees/red_black_tree.py)
* There is a really, [really awesome implementation from Jerry Chalupski](https://gist.github.com/chalup/bf39da54a14005c569ef514c3ce5ceb5), that uses some really cool functional programming concepts.  I'm not sure how to build n this code without just copying it, but I'll put it here anyway.

### Option 2: Solve Problems with Binary Search Trees

I've chosen some tech inteview-style problems from Leetcode (or my own) that you could do.  You could implement these in Kotlin or write down the process by which you would solve them (it's up to you).

* [Convert Sorted Array to a Binary Search Tree](https://leetcode.com/problems/convert-sorted-array-to-binary-search-tree/description/)
* Given a binary search tree, write pseudocode to find the closest element to a query.  You can assume you have a distance function to compute the distance between the query and any element in the BST.
* [Delete node in a BST](https://leetcode.com/problems/delete-node-in-a-bst/description/)
* [Range sum of BST](https://leetcode.com/problems/range-sum-of-bst/description/)
* Solve a problem of your choice from [this list of BST problems](https://leetcode.com/tag/binary-search-tree/).