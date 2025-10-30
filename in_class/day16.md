---
title: "Day 16: Lempel-Ziv"
toc_sticky: true
published: true
---

## A Note on Prime Numbers and Utilizing Bins

I didn't have the right result to describe why using a prime number can handle the case where the numbers you are hashing are all multiples of a single number $k$ (e.g., for even numbers $k=2).  The result can be formalized using the notion of generators of groups (and that is not something you need to know in this class, but you could learn about it in Sarah's class next semester).  In [this Wikipedia article](https://en.wikipedia.org/wiki/Cyclic_group), see the section on "Integer and modular addition."  The article states that if $k$ is relatively prime to the modulus number $n$, then repeatedly adding $k$ to itself will cover all the slots in our hash table.  (Note: a $n$ is relatively prime to $k$ if the greatest common divisor of $n$ and $k$ is 1).


## Lempel-Ziv Compression

One of the options for the current assignment is to implement Lempel-Ziv Compression.  Lempel-Ziv is a lossless compression algorithm, which means that the original data can be recovered exactly (without any loss of information) from the compressed data.

There are a number of different variants of Lempel-Ziv, but the one we're going to talk about in class today is the simplest to implement.

It's also worth noting that Lempel-Ziv is an optimal algorithm for lossless compression in a certain information-theoretic sense.  We likely won't have time to go over the details of this in class, but if you are interested you may consider looking at [this Wikipedia article](https://en.wikipedia.org/wiki/LZ77_and_LZ78#Theoretical_efficiency) that presents the sense in which the algorithm is optimal and links to some external sources that explore this topic in more depth.  The main article is Peter Shor's notes that are also linked below.  If there is time, and people are interested, I'll go over a quick explanation of the claim at the end of class.

## Encoding

We start with a stream of symbols and a codebook.  I'm going to use this string [from Peter Shor's notes](https://web.archive.org/web/20210528171521/http://www-math.mit.edu/~shor/PAM/lempel_ziv_notes.pdf) on the topic.

> AABABBBABAABABBBABBABB

In Lempel-Ziv (LZ) compression, we will also maintain a codebook. The codebook is going to be a mapping from strings to integers.  The strings (the keys) will represent the symbols from our data source and the integers (the values) will be unique identifiers that will help us compress the key. In some variants we start by creating a codebook entry for every possible symbol (letter) in our string.  In this version, we're going to start with a single mapping $\epsilon \rightarrow 0$.  As we scan through the string we'll adaptively add new mappings to our codebook as we encounter particular patterns.

Next, we're going to start scanning through the symbols of our string one-by-one and occasionally building the compressed representation of the data.  Our strategy will be to look for the longest substring that has yet to be compressed and is represented in our codebook.  As we scan our symbols, as long as these strings are in our codebook, we just keep moving through the data.  Once we find that the string is not in the codebook, we do two things

1. We add a new codeword
2. We output the compressed representation of the data.

Let's work through our example on the board.  If you're not in-class today, I'll point you to [this video of a worked example of the same string](https://www.youtube.com/watch?v=Dn-91_Vu_aM).  It's a little different from what I'll do in class, but you'll get the same main idea.

**Now we'll go through the example on the board.**

What questions arose for you from this demonstration?

> **Exercise 1**
> 
> Choose your own string to encode and go through the steps of Lempel-Ziv.  Before you start, take a second to think about what characteristics of the string might make it a more interesting example.
{: .notice--success}

## Decoding

Let's go through the process of decompressing the string that we compressed in our original example.  To do so, we'll scan through the compressed data and build the codebook and output the uncompressed data.

## Practical Considerations for Implementing this in Kotlin

When I wrote my own implementation, I found that it took me a while to figure out how to actually encode the data to binary (even though getting the codebook was fairly straightforward).  I found a nice helper class from Princeton that made the process a lot easier.  For your convenience, I (more accurately IntelliJ with some help from me) translated it into Java.  I modified the original design a bit to arrive at [this version](https://github.com/OlinDSA2024/HashingSample/blob/main/src/main/kotlin/BinaryUtils.kt).

The important functions in here are the following:
```kotlin
/**
 * Writes the specified bit to the output binary data.
 * @param x the `boolean` to write.
 */
fun write(x: Boolean) {}

/**
 * Writes the *r*-bit int to the output binary data.
 * @param x the `int` to write.
 * @param r the number of relevant bits in the char.
 * @throws IllegalArgumentException if `r` is not between 1 and 32.
 * @throws IllegalArgumentException if `x` is not between 0 and 2<sup>r</sup> - 1.
 */
fun write(x: Int, r: Int) {}


/**
 * @return the output as a byte array
 */
fun toByteArray(): ByteArray {
    return out.toByteArray()
}

/**
 * @return the output as a sequence of bytes that represent a string of
 * 0's and 1's
 */
fun toBinaryString():ByteArray? {}
```