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

# Graph traversal algorithms

## DFS (Depth-First Search)

A graph traversal algorithm in which one start with a root node
(artritrarily choosen) then expore as far as possible along each
branch before backtracking.

## BFS (Breadth-First Search)

A graph traversal algorithm in which one explore every possible node in
the current depth level before going to the next.

# Path finding algorithms

## A* algorithm

## Dijkstra algorithm
