---
title: "Day 5: Making Our Own Mutable List Using Arrays and ???"
toc_sticky: true
---

## Kotlin Arrays

Kotlin has an built-in ``Array`` class ([documentation](https://kotlinlang.org/docs/arrays.html)) that can be used in much the same way as ``List`` (and mutable list).  The restrictions on ``Array`` mean that we can't add elements to it.

Let's take some time to write some basic array code together.

## Implement Mutable List

Using an Array as the underlying data structure, create class called ``MyMutableList`` that can hold an element of any data type (let's say the data type is called ``T``) and supports the following functions.

```kotlin
/**
 * Add [element] to the end of the list
 */
fun add(element: T): Boolean

/**
 * Remove all elements from the list
 */
fun clear()

/*
 * @return the size of the list
 */
fun size(): Int

/**
 * @param index the index to return
 * @return the element at [index]
 */
operator fun get(index: Int):T

/**
 * Store [value] at position [index]
 * @param index the index to set
 * @param the value to store at [index]
 */
operator fun set(index: Int, value: T)
```

Use this link to access [my solutions for this exercise](https://github.com/OlinDSA2024/Day05Finished).
