---
title: "Day 5: Making Our Own Mutable List Using Arrays and Intro to Graphs"
toc_sticky: true
published: true
---

## Kotlin Arrays and Creating Our Own Mutable List

Kotlin has a built-in ``Array`` class ([documentation](https://kotlinlang.org/docs/arrays.html)) that can be used in much the same way as ``List`` (and mutable list).  The restrictions on ``Array`` mean that we can't add elements to it.

> **Exercise 1**: Using an Array as the underlying data structure, create a class called ``MyMutableIntList`` that can hold values of type ``Int`` (there a few hoops to jump through to make it hold any type, so let me know if you want to learn about that process).  Your class should support the following functions.
> 
> *Note 1:* the operator functions let you implement the same behavior that ``MutableList`` has in getting and setting elements (e.g., ``a[2] = 3``).
> 
> *Note 2:* when you create your class, you will need to think about how to grow your array when you run out of space.  In class we did some analysis that seemed to show that multiplying the array size by $2$ when it is full is faster than growing it by 1 each time.
{: .notice--success}

```kotlin
interface MutableIntList {
    /**
     * Add [element] to the end of the list
     */
    fun add(element: Int)

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
    operator fun get(index: Int): Int

    /**
     * Store [value] at position [index]
     * @param index the index to set
     * @param value to store at [index]
     */
    operator fun set(index: Int, value: int)
}
```

### Timing your code

You can add the following code to your ``main()`` function to see how efficient your class is for different list sizes.

```kotlin
fun main() {
    val arraySizes = listOf(100, 1000, 10000, 100000, 1000000, 10000000, 100000000)
    println("numberOfElements totalTime timePerElement")
    for (arraySize in arraySizes) {
        val myList = MyMutableIntList()
        val timeTaken = measureTime {
            for (i in 0..<arraySize) {
                myList.add(i)
            }
        }
        println("$arraySize $timeTaken ${timeTaken/arraySize}")
    }
}
```

If you find it useful, you can use this link to access [my solutions for this exercise](https://github.com/OlinDSA2024/Day05Finished).

## Intro to Graphs

In the next assignment we're going to dive into the world of graphs and graph searching.  Before we do so, let's take some time to understand what a graph is.

Graphs are ways to represent relationships between entities of some sort.  For example, you could have a social network graph where the entities are people and the relationships represent who is friends with whom.  You could have a graph where the entities are websites and the relationships are links between sites.

To formalize this a bit more, we use the terminology of *vertices* or *nodes* to refer to the entities in our graph (e.g., the people or websites in our examples above).  We use the term *edges* to represent the relationships (e.g., the existence of a friendship or a link in our two examples above).  In graph theory and algorithms, there are many different types of edges (e.g., directed, undirected, weighted, multi-edges) to represent different sorts of relationships.

For now, we're going to consider the case of directed edges where an edge encodes a unidirectional relationship between two entities.  For example, a directed edge from the node ``olin.edu`` to ``google.com`` might represent that Olin's website links to Google's website.

Before we get into the theory of graphs and the sorts of algorithms we might run on them, let's introduce the concept of an [adjacency list](https://en.wikipedia.org/wiki/Adjacency_list), which is a particular way to represent graphs in a computer program.  Note that this is not the only way to represent a graph in a computer program, but it is a very popular one.

> **Exercise 2**: read about adjacency lists.  On a whiteboard (if you are so inclined) write out a plan for how you would implement an adjacency list in Kotlin.  Your plan might be fairly abstract (e.g., listing out particular classes and functions without worrying about syntax).  If you have time to translate this into Kotlin code, please do so.
{: .notice--success}

Specifications:
* To represent your vertices, you could choose a particular type (e.g., ``String``), or you could use [generics](https://kotlinlang.org/docs/generics.html) to make it work for any class.
* At a minimum, your class should support the ability to add new vertices, add new edges, and get the list of vertices that are connected to a given vertex.

> Note: I expect there will be lots of questions on this, so please don't hesitate to call me over.


## Sample Solutions

Sample solutions for today are in [the Github repo](https://github.com/OlinDSA2024/DSA2024InClass) as a module.
