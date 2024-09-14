---
title: Graph algorithms and Competitive programming
author: Marius Rabenarivo
date: 14th September 2024
titlegraphic: background-graph.png
logo: logo.png
theme: Dresden
fonttheme: "professionalfonts"
bibliography: graph-algorithms.bib
nocite: '@*'
---

![](AlgoMada.png)

# About me

![](marius.jpg){height=75}

- Telecommunications, ESPA Alumni
- Computer Science, University of Reunion Island Alumni
- FaceDev Admin since 2012
- Founder member of AlgoMada
- Clojure dev
- Computer Science Enthusiast
- Current interests: Cryptocurrency, Clojure programming language
- Side project: BetaX Community ![](github-logo.png){height=32} github.com/puchka

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

# Definition of Competitive Programming

‘Competitive Programming’ in summary, is this: “Given well-known
Computer Science (CS) problems, solve them as quickly as possible!”.

# Tips to be competitive

- Type Code Faster
- Quickly identify problem type
- Do Algorithm Analysis
- Master Programming Languages
- Master the Art of Testing Code
- Practice and More Practice

# Data Structures

Data structure is ‘a way to store and organize data’ in order to support eﬃcient insertions, queries, searches, updates, and deletions.

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

# Adjacency Matrix

In contest problems involving graph, usually `V` is known, thus we can
build a ‘connectivity table’ by setting up a 2-D, `O(V^2)` static
array: `int AdjMat[V][V]`.

For an unweighted graph, we set `AdjMat[i][j] = 1` if there is an edge
between vertex `i-j` and set `0` otherwise.

For a weighted graph, we set `AdjMat[i][j] = weight(i, j)` if there is
an edge between vertex `i-j` with `weight(i, j)` and set `0`
otherwise.

# Adjacency List

Adjacency List, usually in form of C++ STL `vector<vii> AdjList`, with `vii` deﬁned as:

```
typedef pair<int, int> ii;
typedef vector<ii> vii; //our data type shortcuts
```

In Adjacency List, we have a vector of `V` vertices and for each vertex
`v`, we store another vector that contains pairs of (neighboring vertex
and it’s edge weight) that have connection to `v`.

If the graph is unweighted, simply store weight = 0 or drop this second attribute.

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

# Tree, Forward, Back and Cross Edges in Depth-First Search

- Tree Edge: It is an edge which is present in the tree obtained after applying DFS on the graph.
- Forward Edge: It is an edge $(u, v)$ such that $v$ is a descendant but not part of the DFS tree.
- Back edge: It is an edge $(u, v)$ such that $v$ is the ancestor of node $u$ but is not part of the DFS tree.
- Cross Edge: It is an edge that connects two nodes such that they do not have any ancestor and a descendant relationship between them.

![Tree, cross, forward and back edges](tree-forward-back-and-cross-edges.jpg "Tree, cross, forward and back edges"){height=100}

# Depth-First Search

![Depth-First Search progress on a directed graph](progress-dfs-directed-graph.png "Progress of DFS on a directed graph"){height=225}


# References

## Web

- [https://www.geeksforgeeks.org/tree-back-edge-and-cross-edges-in-dfs-of-graph/](https://www.geeksforgeeks.org/tree-back-edge-and-cross-edges-in-dfs-of-graph/)
- [https://github.com/bradtraversy/traversy-js-challenges/tree/main/08-binary-trees-graphs/11-adjacency-matrix-adjacency-list](https://github.com/bradtraversy/traversy-js-challenges/tree/main/08-binary-trees-graphs/11-adjacency-matrix-adjacency-list)


# References

## Book

![Introduction to Algorithms, 3rd edition by Thomas H. Cormen, Charles
E. Leiserson, Ronald L. Rivest and Clifford
Stein](K_on_girls_reading_cormen_algorithms.jpg "Introduction to
Algorithms, CLRS"){height=196}
