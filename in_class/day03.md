---
title: "Day 3: Arrays, Linked Lists, and Intro to Abstract Datatypes"
toc_sticky: true
published: false
---

## Meeting Our First Data Structures

Today we're going to meet our first data structures of the semester: the array and the linked list.  We'll talk about tradeoffs in terms of runtime of various operations on these data structures.  We'll also introduce the concept of **abstract data types (ADTs)** as a tool for separating the implementation of a data structure from the operations it supports.  

## Arrays

As we mentioned on day one, data structures represent different approaches to organizing data in some computerized storage system.  In this course we're going to learn about a bunch of different data structures in this class (e.g., linked lists, arrays, binary trees, graphs, etc.).  To help us wrap our minds around the big ideas of data structures, let's consider a very basic data structure: an array.

Depending on your programming background, perhaps you haven't encountered an array yet.  An array is an ordered collection of values (usually of a particular type).  Arrays are typically implemented in a computer using contiguous blocks of memory (e.g., stored in the computer's RAM).

When we create an array, we have to specify the capacity that we'd like our array to have (that is the size that we'd like to reserve for our array in the computer's memory).  Upon requesting an array of a particular size, we will be allocated a contiguous region in the computer's memory to store our values.  We can assume that requesting and being assigned a region in memory is relatively efficient (think of this as taking a constant number of operations).  Further, we can assume that we can efficiently write and read values from an array (think of these as taking a constant number of operations).

### Time Complexity of Various Array Operations

As stated above, for these operations we can assume that the requesting new memory, reading a single value, and writing a single value for our array takes a constant number of operations.

**Problem 1:** Suppose you have an array with $M$ elements and there is space for $C$ elements in the block of memory allocated to your array (with $M < C$).  Assume that the $M$ elements are stored such that they occupy the first $M$ slots of memory allocated to the array.  How much time would it take to add a new element to the end of your array?

**Problem 2:** Now, suppose you'd like to add an element to the beginning of your array.  If there are currently $M$ elements in your array, how many operations would it take to add an element to the beginning of the array?  Going back to our discussion of order-of-growth, what is the running time of this operations in terms of $\Theta$?

**Problem 3:** Now, suppose you want to add an element ot the end of your array but the number of elements stored in the array is equal to the current capacity $M = C$.  How many operations would it take to perform the following steps: request a size $M+1$ block of memory, copy the first $M$ elements to the new memory block, and then add the new element to the array?  Suppose you start $M = C = 1$ (an empty array with no capacity).  How many operations would it take to add $N$ elements to the end of this array if you added them one-by-one?  Determine $\Theta$ of the time complexity of adding these $N$ elements.

**Problem 4:** Similar to the previous problem, suppose you want to add $N$ elements to the end of an array in a one-by-one fashion.  Let's see if we can do better than we did in problem 3.  Instead of adding 1 unit of capacity every time we run out of space in our array, we're going to multiply our capacity by a factor of 2 (e.g., starting we start with capacity 1, then go to capacity 2, then capacity 4, and so on).  How many operations would it take to add $N$ elements to the end of this array if you added them one-by-one and follow the strategy of doubling the capacity of the array each time you run out of space (for simplicity you can assume that $N$ is a power of 2)?  Determine $\Theta$ of the time complexity of adding these $N$ elements in this fashion.

## Linked Lists

Next, we're going to learn about a data structure that excels at many of the operations that arrays are slow at and lags behind in areas where arrays are fast.  This data structure is the linked list.

A linked list is another way to represent an ordered collection of values.  Instead of storing our collection in a contiguous block of memory, instead we store data in nodes that each contain a value and a reference to both the next node and the previous node in our list (this sort of linked list is called a doubly linked list).  In addition to these nodes, we also maintain a reference to the first element (or the head of the linked list) and a reference to the last element (or tail of the linked list).  Let's draw a picture of what this looks like on the board together.

Now let's do some problems to understand the time complexity of various operations on our linked list.  For the purposes of these exercises, let's assume that we can request memory to store a new linked list node in constant time ($\Theta(1)$).

**Problem 5:** With folks around you, determine the time complexity ($\Theta$) of each of these operations on a linked list:
1. Add an element to the beginning of the list
2. Delete an element from the beginning of the list
3. Add an element to the back of the list
4. Delete an element from the back of the list
5. Print out the middle element of the list

**Problem 6:** A singly linked list is a linked list where each node only has a reference to the next element in the list.  In such a list, would the $\Theta$ of any of these operations in problem 5 be different?  If so, which would be different and what are their new $\Theta$ running times.

## Abstract Data Types

A common strategy for managing complexity in software is to separate the details of how a piece of software works (the implementation) from the functions that the software performs (the interface).  You may have seen this when you encountered object-oriented programming in Software Design.  When you created Python classes, you would define methods on those classes that could then be called to perform some operation.  The details of how these operations were carried out, were opaque to the caller (e.g., another class in our program).  In our study of data structures, we will make a similar distinction between the operations that a data type performs, and the specific underlying data structure that is used to implement this data type.

We call the specification of a set of operations (or semantics) for a data type an [Abstract Data Type](https://en.wikipedia.org/wiki/Abstract_data_type) (or ADT).  For instance, we might specify an ADT to represent an ordered collection with the following operations:
* Insert at a new element at position $i$
* Delete element at position $i$
* Access element at position $i$
* Append an element to the end of the list
* etc.

The actual implementation of this abstract data type (called a concrete data type) could use a linked list or an array (or something more exotic) as the underlying data structure.  Determining what concrete data type to use to implement a specific ADT will depend on the operations are most important for your application (you'll want to make those fast).  Perhaps, you could even create different implementations of the same ADT for different use cases (e.g., if you care about accessing elements quickly or adding new elements).

**Problem 7:** For example, the Python tutorial on lists states that while accessing elements in the list, appending an element ot the end of the list, or removing an element from the end fo the list is fast, adding or deleting an element at the beginning of the list is slow.  Based on what you worked out earlier in class, what underlying concrete data structure do you think Python uses for its list class?  Do some research to see if you are right.
