---
title: Assignment 7
toc_sticky: true 
---

## Overview

In this assignment you will explore the idea of associative arrays and how they can be implemented using hash tables.

## Associative Arrays

Create an associative array class that has the following structure.

```kotlin
/**
 * Represents a mapping of keys to values.
 */
class AssociativeArray<K, V> {
    /**
     * Insert the mapping from the key, [k], to the value, [v].
     * If the key already maps to a value, replace the mapping.
     */
    operator fun set(k: K, v: V) {
        // your code here
    }

    /**
     * @return true if [k] is a key in the associative array
     */
    operator fun contains(k: K): Boolean {
        // your code here
    }

    /**
     * @return the value associated with the key [k] or null if it doesn't exist
     */
    operator fun get(k: K): V? {
        // your code here
    }

    /**
     * Remove the key, [k], from the associative array
     * @param k the key to remove
     * @return true if the item was successfully removed and false if the element was not found
     */
    fun remove(k: K): Boolean {
        // your code here
    }
    

    /**
     * @return the number of elements stored in the hash table
     */
    fun size(): Int {
        // your code here
    }

    /**
     * @return the full list of key value pairs for the associative array
     */
    fun keyValuePairs(): List<Pair<K, V>> {
        // your code here
    }
}
```

Your associative array should use separate chaining and the division-based method for hashing (consider using this resource [to determine primes to use in your hashing function](https://planetmath.org/goodhashtableprimes)).  Your code should handle rehashing as the number of elements stored in your associative array grows.

## Solving Problems with Hashing

Choose a problem to solve with hashing.  Here are some suggestions.

### Lempel-Ziv

Implement the Lempel-Ziv algorithm for lossless data compression.  There are a lot of resources for learning this.  [Peter Schor's notes](https://math.mit.edu/~djk/18.310/Lecture-Notes/LZ-worst-case.pdf) seem to be good.

### Markov Text Analysis

Download a text from some source (e.g., Project Gutenberg) and create a Markov model.  That is, given any word in the text, you should be able to return the number of times each word follows the given word in the text.  If you want to have some more fun with it, you could do a Markov Text Generator (a la Allen's Think Python, e.g.).

## Modifications

1. Choose a different hashing function to explore
2. Do some benchmarking to see how sensitive the performance of your associative array is to different choices for number of bins (e.g., using a power of 2 instead of a prime number)