# Experiment No. 2: Implement Depth First Search (DFS) Traversal of a Graph

## Name: LOGESH.N.A

## Register Number: 212223240078

## AIM

To implement Depth First Search (DFS) traversal of a graph using Python 3.

---

## THEORY

Depth First Search (DFS) for a graph is similar to DFS for a tree. However, unlike trees, graphs may contain cycles, meaning a node can be visited more than once. To avoid processing the same node multiple times, a Boolean visited array is used.

A graph can have multiple DFS traversals. DFS starts at an arbitrary node and explores as far as possible along each branch before backtracking.

### DFS Steps

1. Initially, the stack and visited arrays are empty.
2. Visit the start node and push its unvisited adjacent nodes into the stack.
3. Pop the top node from the stack, visit it, and push its unvisited adjacent nodes.
4. Repeat the process until the stack is empty.

---

## ALGORITHM

1. Construct a graph with nodes and edges.
2. DFS uses a stack (explicit or recursion).
3. Insert the start node into the stack.
4. Check its successors (neighboring nodes).
5. If a node is not visited, add it to the stack and continue.
6. Continue this process until no more nodes need to be visited.

---

## PROCEDURE

1. Create a graph using adjacency list representation.
2. Read the number of vertices and edges.
3. Insert edges into the graph.
4. Select a starting node.
5. Mark the node as visited.
6. Visit all adjacent unvisited nodes recursively.
7. Continue until all reachable nodes are visited.
8. Display the DFS traversal path.

---

## PROGRAM

```python
from collections import defaultdict

def dfs(graph, start, visited, path):
    path.append(start)
    visited[start] = True

    for neighbour in graph[start]:
        if not visited[neighbour]:
            dfs(graph, neighbour, visited, path)

    return path

graph = defaultdict(list)

n, e = map(int, input().split())

for i in range(e):
    u, v = input().split()
    graph[u].append(v)
    graph[v].append(u)

start = list(graph.keys())[0]

visited = defaultdict(bool)
path = []

print("Sample Output:")

traversed_path = dfs(graph, start, visited, path)

print(traversed_path)
```

---

## SAMPLE INPUT

```text
8 9
A B
A C
B E
C D
B D
C G
D F
G F
F H
```

## SAMPLE OUTPUT

```text
['A', 'B', 'E', 'D', 'C', 'G', 'F', 'H']
```

---

## RESULT

Thus, a graph was constructed and implementation of Depth First Search (DFS) traversal for the same graph was done successfully.
