---
title: Graph traversal and Path-finding Algorithms used in Video Games
author: Marius Rabenarivo
date: 16th June 2024
titlegraphic: background-graph.png
logo: logo.png
theme: Dresden
fonttheme: "professionalfonts"
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

# Motivation: Why I do this?

![Feynman technique for studying](feynman-technique.png "Motivation: Why I do this?"){height=225}

# Definition of Computer Science

"We are about to study the idea of a computational
process. Computational processes are abstract beings that inhabit
computers. As they evolve, processes manipulate other abstract things
called data. The evolution of a process is directed by a pattern of
rules called a program. People create programs to direct processes. In
effect, we conjure the spirits of the computer with our spells."
Structure and Interpretation of Computer Programs, Harold Abelson and
Gerald J. Sussman

![](Fujiwara_No_Mokou_Law_Is_SICP.png "Fujiwara no Mokou Law is SICP"){height=100}

# What is a graph?

A data structure to represent link between objects.
A graph is defined by a set of nodes V and a set of edges E.

We can summarize this definition by the following formula:

$$
G = (E, V)
$$

Example:
[https://www.redblobgames.com/pathfinding/grids/graphs.html#properties](https://www.redblobgames.com/pathfinding/grids/graphs.html#properties)

# What's the difference between a graph and a tree?

A graph can contain cycles (a node can be visited twice).

![Tree vs Graph](Tree-Data-Structure-Example.png "Tree data structure example"){height=200}

# Different type of graphs

- Acyclic Graph

A graph that has no cycle.

- Cyclic Graph

A graph that has at least one cycle.

![Acyclic vs Cyclic graph](acyclic-cyclic.png "Acyclic vs Cyclic graph"){height=96}

# Different type of graphs

- Directed Graph 

A graph in which edge has direction. That is the nodes are ordered
pairs in the definition of every edge.

- Undirected Graph

A graph in which edge are not directed. Meaning, the edges are defined
by an unordered pair of nodes.

![Undirected vs Directed Graph](undirected-directed.png "Undirected/Directed graph"){height=96}

# Different type of graphs

- Directed Acyclic Graph

A graph that is both directed and acyclic.

![Directed Acyclic Graph](dag.png "Directed Acyclic Graph"){height=175}

# Different type of graphs

- Connected graph

Every pair of nodes has a path linking them. Put in another way, there
are no inaccessible node.

- Disconnected graph

A graph in which there is at least one inaccessible node.

![Disconnected vs Connected Graph](disconnected-connected.png "Disconnected vs Connected graph"){height=100}

# Different type of graphs

- A multigraph

A graph that can have multiple edges between the same nodes.

![A multigraph with multiple edges (red) and several loops (blue). By
0x24a537r9 - Own work, CC BY-SA 3.0,
https://commons.wikimedia.org/w/index.php?curid=12247695](Multi-pseudograph.png "A multigraph with multiple edges (red) and several loops (blue)."){height=150}

# Different way to represent a graph

There are 2 ways to represent a graph:

- adjacency list
For each node, provide a list of other nodes that are adjacent to it.
- adjacency matrix A matrix construct by aligning the nodes in the row
and the columns and putting a value if the nodes are linked by an edge.

![(a) Undirected graph with 5 vertices and 7 edges (b) Adjacency-list representation (c) Adjacency-matrix representation](graph-representation.png "Graph representation")

# Graph traversal algorithms

## BFS (Breadth-First Search)

A graph traversal algorithm in which one explore every possible node
in the current depth level before going to the next.  Usually used to
find shortest path distance from the start to a given vertex and the
associated predecessor subgraph.

## DFS (Depth-First Search)

A graph traversal algorithm in which one start with a root node
(arbitrarily chosen) then explore as far as possible along each
branch before backtracking.
Usually used as a subroutine in another algorithm.

![Graph traversal algorithms](graph-traversal-algorithms-1.png "Graph traversal algorithms"){height=80}

# BFS (Breadth-First Search)

![Breadth-first search pseudo-code](breadth-first-search-pseudocode.png "Breadth-first search pseudocode"){height=225}

# BFS (Breadth-First Search)

![Operation of BFS on an undirected graph](bfs-undirected-graph.png "Operation of BFS on an undirected graph"){height=225}

# Predecessor subgraph

The procedure BFS builds a breadth-ﬁrst tree as it searches the graph, as Fig-11 illustrates. The tree corresponds to the $\pi$ attributes.

More formally, for a graph $G = (V, E)$ with source $s$, we deﬁne the **predecessor subgraph** of $G$ as $G_{\pi} = (V_{\pi}, E_{\pi})$
$$
V_{\pi} = { v \in V : v.\pi \ne NIL }
$$

and

$$
E_{\pi} = { (v, \pi, v) : v \in V_{\pi} - {s} }
$$

# Breadth-first trees

The predecessor subgraph $G_{\pi}$ is a **breadth-ﬁrst tree** if
$V_{\pi}$ consists of the vertices reachable from $s$ and, for all $v \in V$,
the subgraph $G_{\pi}$ contains a unique simple path from $s$
to $v$ that is also a shortest path from $s$ to $v$ in $G$.

# Depth-First Search

![Depth-First Search Pseudocode](depth-first-search-pseudocode.png "Depth-First Search pseudocode"){height=225}

# Depth-First Search

![Depth-First Search progress on a directed graph](progress-dfs-directed-graph.png "Progress of DFS on a directed graph"){height=225}

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

![Example path-finding situation](concave1.png "Example path-finding situation"){height=225}

# Path-finding

![Example path-finding situation](concave2.png "Example path-finding situation"){height=225}

# A* Algorithm

## History

![A* was invented by researchers working on Shakey the Robot's path
planning.](330px-SRI_Shakey_with_callouts.jpg "A* was invented by
researchers working on Shakey the Robot's path planning."){height=200}

# Application in Video Games

For 2D video games, a tile map can be transformed into a graph.  Each
cell of the grid will be a node in the graph and the edges are going
to be the four directions: east, north, west, south.

![Map as graph](map-as-graph.png "Map as graph"){height=110}

Example:
[https://www.redblobgames.com/pathfinding/grids/graphs.html#grids](https://www.redblobgames.com/pathfinding/grids/graphs.html#grids)

# Dijkstra’s Algorithm

Dijkstra’s Algorithm works by visiting vertices in the graph starting
with the object’s starting point. It then repeatedly examines the
closest not-yet-examined vertex, adding its vertices to the set of
vertices to be examined.

![Dijkstra algorithm](dijkstra.png "Didjkstra algorithm illustration"){height=150}

# Gready Best-First search
The Greedy Best-First-Search algorithm works in a similar way, except
that it has some estimate (called a heuristic) of how far from the
goal any vertex is. Instead of selecting the vertex closest to the
starting point, it selects the vertex closest to the goal. Greedy
Best-First-Search is not guaranteed to find a shortest
path.

![Greedy Best-first search](best-first-search.png "Greedy Best-First Search"){height=128}

# Dijkstra’s Algorithm and Best-First-Search

Let’s consider the concave obstacle as described in the previous
section. Dijkstra’s Algorithm works harder but is guaranteed to find a
shortest path:

![Dijkstra's Algorithm with obstacle](dijkstra-trap.png "Dijkstra’s Algorithm with obstacle"){height=150}

# Dijkstra’s Algorithm and Best-First-Search

Greedy Best-First-Search on the other hand does less work but its path is clearly not as good:

![Greedy Best-First Search with trap](best-first-search-trap.png "Greedy Best-First Search with trap"){height=150}

# The A* Algorithm

A* is like Dijkstra’s Algorithm in that it can be used to find a
shortest path. A* is like Greedy Best-First-Search in that it can use
a heuristic to guide itself. In the simple case, it is as fast as
Greedy Best-First-Search:

![A* algorithm](a-star.png "A* algorithm"){height=150}

#

![](pathfinding-using-A-Star.png)

#

![](pathfinding-using-A-Star-1.png)

# References

- https://en.wikipedia.org/wiki/A*_search_algorithm 
- http://theory.stanford.edu/~amitp/GameProgramming/AStarComparison.html

