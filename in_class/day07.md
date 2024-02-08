---
title: "Day 7: DAGs, Dijkstra's Algorithm, and Heaps"
toc_sticky: true
---

## Directed-Acyclic Graphs

Starting off, let's revisit a problem that most of you didn't get to from last class.  This is the problem of determining of a given directed graph is acyclic. To motivate this, let's consider the following graph.

```mermaid!
graph LR
  A --> B
  B --> C
  A --> C
  C --> D
  B --> D
  A --> E
  D --> E
```

Perhaps unsurprisingly, a directed graph is a directed acyclic graph ([DAG](https://en.wikipedia.org/wiki/Directed_acyclic_graph)) if it contains no cycles.  Cycles are paths through the graph that repeat vertices.

One of the supplementary problems in the last class is an algorithm known as Kahn's algorithm for determining if a graph is a DAG.  More specifically, it computes a topological sorting of the vertices of the graph, and if a sorting exists, the graph has no cycles.  A topological sorting of a graph is an ordering of the graph's vertices $v_1, v_2, \ldots, v_n$ such that the edge $v_i \rightarrow v_j$ can only exist if $i < j$.

Here is pseudocode for the algorithm Kahn's algorithm.

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

Let's go through this example together to see how Kahn's algorithm works.

Let's try Kahn's algorithm on a graph that does contain a cycle to see what happens.

```mermaid!
graph LR
  A --> B
  B --> C
  C --> D
  C --> B
  A --> D
```

## Dijkstra's Algorithm



## Min-Heaps