---
title: "Day 13: Reviewing Assignment 5 and Looking Toward Assignment 6"
toc_sticky: true
---

## Reviewing Assignment 5

Get in a group with two people who did [Needleman-Wunsch](https://en.wikipedia.org/wiki/Needleman%E2%80%93Wunsch_algorithm) and two people who did [Smith-Waterman](https://en.wikipedia.org/wiki/Smith%E2%80%93Waterman_algorithm).  Together go through the following questions:

* With respect to the matrix multiplication questions, how did those go for you?  Share some development or testing strategies that worked particularly well (we'll do a quick shareout of these among the class).
* Take turns explaining the algorithm you implemented to the folks who implemented the other algorithm.  Make note of any similarities or differences between the two algorithms.

## Looking Towards Assignment 6

The period from now until Spring Break will consist of a fairly short, self-directed project.  Use this link to find [the details of assignment 6](../assignments/assignment_06.md).  I'll give you 30 minutes to start to formulate some initial ideas for this assignment.  We'll take the last part of class to do some sharing of ideas in small groups.

## Packaging Kotlin Files

Last time Daeyoung asked about what it would take to package a Kotlin program for distribution.  I'm still looking into this, but here are a few things to keep in mind.

1. Kotlin is the preferred language for Android Mobile development.  If your target is developing for Android, you are in great shape!
2. Jetbrains has a product called [Compose Multiplatform](https://www.jetbrains.com/lp/compose-multiplatform/) that can deploy Kotlin to many different platforms.  The current platforms that are production ready are Android and Desktop (Mac, Windows, Linux).
3.  There are a bunch of other solutions (e.g., spring.io) that were designed around packaging Java applications, which can also work for Kotlin (since Kotlin also executes on the JVM).

It would be really cool to investigate these more.  I'll see if I can create a sample application before Spring break.