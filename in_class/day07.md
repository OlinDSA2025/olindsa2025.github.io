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