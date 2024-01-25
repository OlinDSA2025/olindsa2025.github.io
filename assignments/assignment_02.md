---
title: Assignment 2
toc_sticky: true 
---

## Overview

In this assignment you will be implementing a doubly linked list in Kotlin.  You'll then define abstract data types for both a queue and a stack.  Once you've done that, you can use your newly minted data structures to solve some code-interview style problems.

## Part 1: Doubly Linked List

Implement a doubly linked list in Kotlin.  Your class should work with any data type (use [Kotlin's generics](https://kotlinlang.org/docs/generics.html)) and support the following operations (we use ``T`` to refer to the data type stored in the underlying linked list..

```kotlin
fun pushFront(data: T)
fun pushBack(data: T)
fun popFront(): T?
fun popBack(): T?
fun peekFront(): T?
fun peekBack(): T?
fun isEmpty(): Boolean
``` 

Make sure to include unit tests for each of these operations.

## Stack and Queue Abstract Data Types

The Stack abstract data type is:

```kotlin
interface Stack<T> {
    fun push(data: T)
    fun pop(): T?
    fun peek(): T?
    fun isEmpty(): Boolean
}
```


The Queue abstract data type is:

```kotlin
interface Queue<T> {
    fun enqueue(data: T)
    fun dequeue(): T?
    fun peek(): T?
    fun isEmpty(): Boolean
}
```


## Stack and Queue Implementations

> P1: Using your linked list class as a data structure, create a class that implements the stack abstract data type.  Make sure to include at least one unit test for each of the functions in the stack ADT.

> P2: Using your linked list class as a data structure, create a class that implements the queue abstract data type.  Make sure to include at least one unit test for each of the functions in the queue ADT.

## Practice Problems with Stacks and Queues

These next problems are similar to the types of problems you might encounter in a technical interview.  You should work out a strategy for implementing all fo them, but you only need to implement one in Kotlin.

> P3: How would you reverse the elements in a stack (i.e., put the elements at the top of the stack on the bottom and vice-versa)?  You can use as many additional stacks and queues as temporary storage in your approach.

> P4: Come up with a strategy to solve the [valid parentheses problem](https://leetcode.com/problems/valid-parentheses/description/).

> P5: Solve the copy stack problem (source: University of Washington CSE122)
>
> Given a stack return a copy of the original stack (i.e., a new stack with the same values as the original, stored in the same order as the
original). Your method should create the new stack and fill it up with the same values that are stored in the original stack.
>
> You may use one queue as auxiliary storage.

### More problems you might check out (totally optional... let's find more together)

* Splice stack (https://courses.cs.washington.edu/courses/cse122/23wi/lectures/5/5.pdf)
* https://leetcode.com/tag/queue/
* https://leetcode.com/tag/stack/
* https://leetcode.com/problems/simplify-path/
