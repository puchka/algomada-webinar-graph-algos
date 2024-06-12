---
title: Graph traversal and Path-finding Algorithms used in Video Games
author: Marius Rabenarivo
bibliography: graph-algorithms.bib
nocite: '@*'
---

![](AlgoMada.png)

# About me

![](marius.jpg){height=100}

- Telecommunications, ESPA Alumni
- Computer Science, University of Reunion Island Alumni
- FaceDev Admin since 2012
- Founder member of AlgoMada
- Clojure dev
- Computer Science Enthusiast
- Current interests: Cryptocurrency, Clojure programming language
- Side project: BetaX Community

# What is a graph?

A data structure to represent link between objects.
A graph is defined by a set of nodes V and a set of edges E.

We can summarize this definition by the following formula:

$$
G = (E, V)
$$

## What's the difference between a graph and a tree?

A graph can contain cycles (a node can be visited twice).

## Different type of graphs

- Acyclic Graph
A graph that has no cycle.
- Cyclic Graph
A graph that has at least one cycle.
- Directed Graph 
A graph in which edge has direction. That is the nodes are ordered
pairs in the definition of every edge.
- Undirected Graph
A graph in which edge are not directed. Meaning, the edges are defined
by an unordered pair of nodes.
- Directed Acyclic Graph
A graph that is both directed and acyclic.
- Connected graph
Every pair of nodes has a path linking them. Put in another way, there
are no inaccessible node.
- Disconnected graph
A graph in which there is at least one inaccessible node.

# Different way to represent a graph

There are 2 ways to represent a graph:

- adjacency list
For each node, provide a list of other nodes that are adjacent to it.
- adjacency matrix A matrix construct by aligning the nodes in the row
and the columns and putting a value if the nodes are linked by an edge.

![(a) Undirected graph with 5 vertices and 7 edges (b) Adjacency-list representation (c) Adjacency-matrix representation](graph-representation.png "Graph representation")

# Graph traversal algorithms

## DFS (Depth-First Search)

A graph traversal algorithm in which one start with a root node
(arbitrarily chosen) then explore as far as possible along each
branch before backtracking.

## BFS (Breadth-First Search)

A graph traversal algorithm in which one explore every possible node in
the current depth level before going to the next.

# BFS (Breadth-First Search)

![Breadth-first search pseudo-code](breadth-first-search-pseudocode.png "Breadth-first search pseudocode"){height=250}

# BFS (Breadth-First Search)

![Operation of BFS on an undirected graph](bfs-undirected-graph.png "Operation of BFS on an undirected graph"){height=250}

# Depth-First Search

![Depth-First Search Pseudocode](depth-first-search-pseudocode.png "Depth-First Search pseudocode"){height=250}

# Depth-First Search

![Depth-First Search progress on a directed graph](progress-dfs-directed-graph.png "Progress of DFS on a directed graph"){height=275}

# Path finding algorithms

## A* algorithm

A* (pronounced "A-Star") is a graph traversal and path-finding
algorithm.  Given a source and a goal node, the algorithm find the
shortest-path (with respect to given weights) from source to goal.

## Dijkstra algorithm

Dijkstra algorithm solves the single-source shortest-paths problem on
a weighted directed graph for the case in which all weights are
non-negative.

# Path-finding

![Example path-finding situation](concave1.png "Example path-finding situation"){height=250}

# Path-finding

![Example path-finding situation](concave2.png "Example path-finding situation"){height=250}

# A* Algorithm

## History

![A* was invented by researchers working on Shakey the Robot's path
planning.](330px-SRI_Shakey_with_callouts.jpg "A* was invented by
researchers working on Shakey the Robot's path planning."){height=250}

# References

- https://en.wikipedia.org/wiki/A*_search_algorithm 
- http://theory.stanford.edu/~amitp/GameProgramming/AStarComparison.html

