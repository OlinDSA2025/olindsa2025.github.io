---
title: "Day 6: Graph data structures, depth-first and breadth-first search"
toc_sticky: true
---

## Adjacency Lists 

Last time, I asked you to think about the [adjacency list](https://en.wikipedia.org/wiki/Adjacency_list), which is a particular way to represent graphs in a computer program.

To get us on the same page let's use the following definition of a Graph.

```kotlin
class Graph<VertexType> {
    private var vertices: MutableSet<VertexType> = mutableSetOf()
    private var edges: MutableMap<VertexType, MutableSet<VertexType>> = mutableMapOf()

    /**
     * Add the vertex [v] to the graph
     * @param v the vertex to add
     * @return true if the vertex is successfully added, false if the vertex
     *   was already in the graph
     */
    fun addVertex(v: VertexType): Boolean {
        if (vertices.contains(v)) {
            return false
        }
        vertices.add(v)
        return true
    }

    /**
     * Add an edge between vertex [from] connecting to vertex [to]
     * @param from the vertex for the edge to originate from
     * @param to the vertex to connect the edge to
     * @return true if the edge is successfully added and false if the edge
     *     can't be added or already exists
     */
    fun addEdge(from: VertexType, to: VertexType): Boolean {
        if (!vertices.contains(from) || !vertices.contains(to)) {
            return false
        }
        edges[from]?.also { currentAdjacent ->
            if (currentAdjacent.contains(to)) {
                return false
            }
            currentAdjacent.add(to)
        } ?: run {
            edges[from] = mutableSetOf(to)
        }
        return true
    }

    /**
     * Clear all vertices and edges
     */
    fun clear() {
        vertices = mutableSetOf()
        edges = mutableMapOf()
    }
}
```

## Graph Traversal

One of the most important graph algorithms is the concept of searching for a path that connects two nodes within a graph.  This concept is known as [Graph Traversal](https://en.wikipedia.org/wiki/Graph_traversal) or Graph Search.

Within the space of graph traversal, there are a number of useful problems we might solve.
* [Shortest path](https://en.wikipedia.org/wiki/Shortest_path_problem) (finding the path between two nodes with the least cost)
* [Traveling salesman problem](https://en.wikipedia.org/wiki/Travelling_salesman_problem)
* [Hamiltonian path](https://en.wikipedia.org/wiki/Hamiltonian_path)
* [Eulerian path](https://en.wikipedia.org/wiki/Eulerian_path)
* ... (many more)

In this class we will be mainly concerned with the shortest path problem.

There are tons of problems that can be cast as graph traversal problems.  Let's think of a few as a class.  To get us started what are some problems that can be converted into graphs?

We're going to learn about four different methods for graph traversal in this class.  Today, we'll talk about the first two.

### Breadth-First Search (BFS)

Starting from some node in our graph, let's call it ``root``, we want to keep following edges until we find our node ``target``.  Our search proceeds by following all edges from the current node.  Once we've followed all of those edges, we follow edges from current to the next node, we follow edges from that set of nodes, etc. We do this until we find ``target`` or run out of nodes to visit.

### Depth-First Search (DFS)

Starting from some node in our graph, let's call it ``root``, we want to keep following edges until we find our node ``target``.  Our search proceeds by continuously following edges until we reach a point where no edges are available to traverse.  At that point, we can back track on our path and visit the next edge.

### General Approach to Graph Traversal

Our algorithms for graph traversal are all fairly similar.  The two we're going to learn about today can be described using the following framework.

```
toVisit ← {}
priorityList ← []

priorityList.add(root)
toVisit.add(root)

while priorityList is not empty:
    n ← priorityList.getHighestPriorityElement()
    if n == target:
        return true // path exists
    for m in nodesConnectedTo(n):
        if m is not in toVisit:
            priorityList.add(m)
            toVisit.add(m)

return false // no path
```

### Problem 1

Looking at the pseudocode above, what is the role of the ``toVisit`` list?  What might happen if we removed it?

### Problem 2

Given the pseudocode above and the ``Graph`` class, implement breadth-first search (BFS).  You can choose how you define your function, but perhaps add it as a new function of ``Graph``.

> Hint: think long and hard about what data structures you've learned about would achieve the desired prioritization of nodes.

### Problem 3

Given the pseudocode above and the ``Graph`` class, implement depth-first search (DFS).  You can choose how you define your function, but perhaps add it as a new function of ``Graph``.

> Hint: think long and hard about what data structures you've learned about would achieve the desired prioritization of nodes.

### Visualizations of Graph Traversal

Here are some resources for visualizing graph searching algorithms.
* [Stanford SAILORS tutorial on breadth-first search](https://cs.stanford.edu/people/abisee/tutorial/bfs.html)
* [Stanford SAILORS tutorial on depth-first search](https://cs.stanford.edu/people/abisee/tutorial/dfs.html)
* [Stanford SAILORS tutorial on comparing DFS and BFS](https://cs.stanford.edu/people/abisee/tutorial/bfsdfs.html)

## Graph Properties

We probably won't have a ton of time to work with these during class today, but here are some useful properties of graphs.  You will have to implement some of these in the assignment.

### Number of Connected Components

For an undirected graph (where ``A`` connected to be ``B`` is implies ``B`` connected to ``A``), a connected component is a set of vertices such that there is a path between any two vertices in the set.  If all vertices in a graph are connected, we would say the graph has 1 connected component.  On the other hand, if there are some vertices that are not reachable from each other, that would create additional components.

Suppose you were given a ``Graph`` object where you were guaranteed that all edges were symmetric (``A`` connected to ``B`` implies ``B`` connected to ``A``).  Write pseudocode to determine the number of connected components in your graph.

### DAGs (Directed, Acyclic Graph)

A directed graph is acyclic if it contains no cycles.  A cycle is a path that starts at a given node and returns to that same node.

There are several algorithms to determine if a graph is a Directed Acyclic Graph (DAG).  One of the easier ones to understand is Kahn's algorithm, which has the following description from [the Wikipedia page on Topological Sorting](https://en.wikipedia.org/wiki/Topological_sorting). It turns out that a graph is a DAG if and only if there is a valid topological sorting of the nodes in the DAG.

```
L ← Empty list that will contain the sorted elements
S ← Set of all nodes with no incoming edge

while S is not empty do
    remove a node n from S
    add n to L
    for each node m with an edge e from n to m do
        remove edge e from the graph
        if m has no other incoming edges then
            insert m into S

if graph has edges then
    return error   (graph has at least one cycle)
else 
    return L   (a topologically sorted order)
```

### Trees

An undirected graph is a tree if there is exactly one path between any pair of nodes.  This is guaranteed if the graph is connected and the total number of edges if equal to the number of vertices minus 1.

A directed graph is a tree if it is acyclic and the graph the results from making the edges undirected is a tree.