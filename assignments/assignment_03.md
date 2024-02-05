---
title: Assignment 3
toc_sticky: true 
---

## Getting Started

You should fork this base [Assignment03 repo](https://github.com/OlinDSA2024/Assignment03).  If you want your repo to be private, please make sure to add me, ``paulruvolo``, as a collaborator for when you turn in your work.

## Representing Graphs

Create a Kotlin class to represent graphs a directed, weighted graph.  Your graph should implement the ``Graph<VertexType>`` interface (in the base repo).

```kotlin

/**
 * This is a simple ``Graph`` that represents a directed graph
 * @param VertexType the representation of a vertex in the graph
 */
interface Graph<VertexType> {
    /**
     * @return the vertices in the graph
     */
    fun getVertices(): Set<VertexType>

    /**
     * Add an
     */
    fun addEdge(from: VertexType, to: VertexType, cost: Double)

    /**
     *
     */
    fun getEdges(from: VertexType): Map<VertexType, Double>

    /**
     * Remove all edges and vertices from the graph
     */
    fun clear()
}
```

* You should be able to retrieve a collection of vertices in the graph (e.g., you might maintain a ``MutableList`` or a ``Mutable`` set that contains all of your vertices.)
* Given a vertex, $$v$$, you should be able to retrieve a collection of vertices that are neighbors of $$v$$ (that is any vertex $$m$$ such that there exists an edge $$v \rightarrow m$$).

## Creating a Priority Queue

Create a data structure called [``PriorityQueue``](https://en.wikipedia.org/wiki/Priority_queue) that supports the following operations (this interface is already in the base repo).

```kotlin
/**
 * ``MinPriorityQueue`` maintains a priority queue where the lower
 *  the priority value, the sooner the element will be removed from
 *  the queue.
 *  @param T the representation of the items in the queue
 */
interface MinPriorityQueue<T> {
    /**
     * @return true if the queue is empty, false otherwise
     */
    fun isEmpty(): Boolean

    /**
     * Add [elem] with at level [priority]
     */
    fun addWithPriority(elem: T, priority: Double)

    /**
     * Get the next (lowest priority) element.
     * @return the next element in terms of priority.  If empty, return null.
     */
    fun next(): T?

    /**
     * Adjust the priority of the given element
     * @param elem whose priority should change
     * @param newPriority the priority to use for the element
     *   the lower the priority the earlier the element int
     *   the order.
     */
    fun adjustPriority(elem: T, newPriority: Double)
}
```

In order to implement your priority queue, you'll want to create a ``MinHeap``.  For your ``MinHeap`` you can either build it from scratch (e.g., using [this Wikipedia page](https://en.wikipedia.org/wiki/Heap_(data_structure)) as a guide) or you can build off (or probably just use) the reference implementation [here](https://github.com/OlinDSA2024/Assignment03/blob/main/src/main/kotlin/MinHeap.kt).  The priority queue will be a pretty thin wrapper on top op the heap.

## Searching

Implement Dijkstra's algorithm to search through a graph for the shortest path.  Your algorithm should return the shortest path (not just the cost) between a given start node and a given destination node.  If no path exists between the two nodes, return ``null``.

## Solving Problems with Dijkstra

Dijkstra can be used to solve a bunch of problems.  Here are some you might want to try for practice.  Choose at least one of these options.

* [Project Euler Problem 81](https://projecteuler.net/problem=81) (also look at 82 and 83 for harder variants)
* [Implement a Maze Solver](https://inginious.org/course/competitive-programming/graphs-maze)
* Create a graph that represents the cost (however you want to define it) to travel between particular various cities (you choose which ones).  Compute some shortest paths on this graph using your Dijkstra implementation.  If you want to define a map on a different level of granularity (e.g., city streets) that is cool too!

## Turning in your Code

Submit the fork of the base ``Assignment03`` repo.

## Assessment

See the rubric on Canvas.