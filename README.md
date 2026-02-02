# Data Structures and Algorithms

A comprehensive guide to fundamental data structures and algorithms with complexity analysis.

## Table of Contents

- [Big O Notation](#big-o-notation)
- [Abstract Data Types (ADT)](#abstract-data-types-adt)
- [Array List](#array-list)
- [Linked Lists](#linked-lists)
- [Cursor-Based Lists](#cursor-based-lists)
- [Stacks](#stacks)
- [Queues](#queues)
- [Sets](#sets)
- [Bit Vector](#bit-vector)
- [Computer Word](#computer-word)
- [Priority Queues](#priority-queues)
- [Dictionaries](#dictionaries)
- [Open Hashing](#open-hashing)
- [Closed Hashing](#closed-hashing)
- [Trees](#trees)
- [Unordered Trees](#unordered-trees)
- [Binary Search Trees](#binary-search-trees)
- [Partially Ordered Trees](#partially-ordered-trees)
- [Huffman Code](#huffman-code)
- [Graphs Overview](#graphs-overview)
- [Graph Algorithms](#graph-algorithms)
  - [Minimum Cost Spanning Tree](#minimum-cost-spanning-tree)
  - [Graph Traversal](#graph-traversal)
  - [Shortest Path Algorithms](#shortest-path-algorithms)

---

## Big O Notation

Big O notation describes the upper bound of algorithm complexity as input size approaches infinity.

### Common Complexities (Best to Worst)

| Notation | Name | Example |
|----------|------|---------|
| O(1) | Constant | Array access, hash table lookup |
| O(log n) | Logarithmic | Binary search |
| O(n) | Linear | Linear search, array traversal |
| O(n log n) | Linearithmic | Merge sort, heap sort |
| O(n²) | Quadratic | Nested loops, bubble sort |
| O(n³) | Cubic | Triple nested loops |
| O(2ⁿ) | Exponential | Recursive fibonacci |
| O(n!) | Factorial | Permutation generation |

### Rules
- Drop constants: O(2n) → O(n)
- Drop lower-order terms: O(n² + n) → O(n²)
- Different inputs use different variables: O(a + b) or O(a × b)

---

## Abstract Data Types (ADT)

An ADT is a mathematical model that defines a data type by its behavior (operations) rather than implementation.

**Key Characteristics:**
- Defines what operations can be performed
- Does not specify how operations are implemented
- Provides data abstraction and encapsulation

**Common ADTs:**
- List, Stack, Queue, Set, Map, Tree, Graph

---

## Array List

Dynamic array that grows automatically when capacity is reached.

**Operations:**
- Access: O(1)
- Search: O(n)
- Insert at end: O(1) amortized, O(n) worst case
- Insert at position: O(n)
- Delete: O(n)

**Advantages:**
- Fast random access
- Cache-friendly (contiguous memory)
- Simple implementation

**Disadvantages:**
- Expensive insertions/deletions in middle
- Wasted space when not full
- Reallocation overhead

---

## Linked Lists

Linear collection where elements point to the next element via pointers/references.

### Singly Linked List
**Operations:**
- Access: O(n)
- Search: O(n)
- Insert at head: O(1)
- Insert at tail: O(1) with tail pointer, O(n) without
- Delete: O(n)

### Doubly Linked List
Each node has pointers to both next and previous nodes.

**Advantages:**
- Bidirectional traversal
- Easier deletion when node reference is given

**Operations:**
- Same as singly linked list
- Can traverse backwards

### Circular Linked List
Last node points back to the first node.

**Use Cases:**
- Round-robin scheduling
- Music playlist loops

---

## Cursor-Based Lists

Simulates linked lists using arrays instead of pointers, useful in languages without pointer support.

**Structure:**
- Array of nodes with data and "next" index
- Free list to manage available slots

**Operations:**
- Similar to linked lists: O(1) insert/delete with position
- Access: O(n)

**Advantages:**
- No dynamic memory allocation
- Works in pointer-free environments

**Disadvantages:**
- Fixed maximum size
- More complex than pointer-based lists

---

## Stacks

LIFO (Last In, First Out) data structure.

**Operations:**
- Push: O(1)
- Pop: O(1)
- Peek/Top: O(1)
- IsEmpty: O(1)

**Implementations:**
- Array-based: fixed or dynamic size
- Linked list-based: dynamic size

**Applications:**
- Function call stack
- Expression evaluation
- Undo mechanisms
- Backtracking algorithms
- Parenthesis matching

---

## Queues

FIFO (First In, First Out) data structure.

**Operations:**
- Enqueue: O(1)
- Dequeue: O(1)
- Front/Peek: O(1)
- IsEmpty: O(1)

**Implementations:**
- Circular array
- Linked list

**Variants:**
- Deque (Double-ended queue)
- Circular queue

**Applications:**
- BFS traversal
- Job scheduling
- Buffer management
- Request handling

---

## Sets

Collection of unique elements with no duplicates.

**Operations:**
- Insert: O(1) average with hash set, O(log n) with tree set
- Delete: O(1) average with hash set, O(log n) with tree set
- Contains: O(1) average with hash set, O(log n) with tree set
- Union: O(n + m)
- Intersection: O(min(n, m))
- Difference: O(n)

**Implementations:**
- Hash set (unordered)
- Tree set (ordered)
- Bit vector (for small universe)

---

## Bit Vector

Array of bits used to represent a set of integers from a bounded universe.

**Structure:**
- Each bit represents presence (1) or absence (0) of an element

**Operations:**
- Insert: O(1) - set bit to 1
- Delete: O(1) - set bit to 0
- Contains: O(1) - check if bit is 1
- Union: O(n/w) where w is word size
- Intersection: O(n/w)

**Advantages:**
- Extremely space-efficient for dense sets
- Fast bitwise operations

**Disadvantages:**
- Fixed universe size
- Inefficient for sparse sets
- Only works with non-negative integers

---

## Computer Word

The natural unit of data used by a computer's processor.

**Characteristics:**
- Typically 32 or 64 bits
- Determines maximum integer size
- Affects memory addressing
- Influences performance of bitwise operations

**Relevance to Data Structures:**
- Bit vector operations work on word boundaries
- Hash functions often use word-size computations
- Cache line sizes are word-multiple

---

## Priority Queues

Queue where elements have associated priorities; highest priority element is dequeued first.

**Operations:**
- Insert: O(log n) with heap
- DeleteMin/Max: O(log n)
- FindMin/Max: O(1)
- DecreaseKey: O(log n)

**Implementations:**
- Binary heap (most common)
- Fibonacci heap (better amortized complexity)
- Binary search tree

**Applications:**
- Dijkstra's algorithm
- Huffman coding
- Event-driven simulation
- A* pathfinding
- Job scheduling

---

## Dictionaries

ADT that stores key-value pairs and supports efficient lookup by key.

**Operations:**
- Insert: O(1) average, O(n) worst (hash table)
- Delete: O(1) average, O(n) worst
- Search: O(1) average, O(n) worst
- With BST: O(log n) all operations

**Implementations:**
- Hash tables (unordered)
- Binary search trees (ordered)
- Skip lists

**Applications:**
- Symbol tables
- Database indexing
- Caching (LRU cache)
- Spell checkers

---

## Open Hashing

Also called separate chaining; collisions are handled by maintaining a linked list at each hash table slot.

**Structure:**
- Array of buckets (linked lists)
- Hash function maps keys to bucket indices

**Operations:**
- Insert: O(1) average
- Search: O(1 + α) where α = n/m (load factor)
- Delete: O(1 + α)

**Advantages:**
- Simple implementation
- Never fills up
- Less sensitive to hash function quality

**Disadvantages:**
- Extra memory for pointers
- Cache performance worse than closed hashing
- Potential for long chains

**Load Factor:**
- α = n/m (items/buckets)
- Performance degrades as α increases
- Typically rehash when α > 0.75

---

## Closed Hashing

Also called open addressing; all elements stored in the hash table array itself, collisions resolved by probing.

### Probing Methods

**Linear Probing:**
- h(k, i) = (h(k) + i) mod m
- Simple but causes primary clustering

**Quadratic Probing:**
- h(k, i) = (h(k) + c₁i + c₂i²) mod m
- Reduces clustering

**Double Hashing:**
- h(k, i) = (h₁(k) + i × h₂(k)) mod m
- Best distribution, no clustering

**Operations:**
- Insert: O(1/(1-α)) average
- Search: O(1/(1-α))
- Delete: Requires tombstone markers

**Advantages:**
- No extra memory for pointers
- Better cache performance
- Memory efficient

**Disadvantages:**
- Table can fill up
- Deletion is complex
- Performance degrades as load factor increases
- Requires good hash function

---

## Trees

Hierarchical data structure with a root node and child nodes forming a parent-child relationship.

**Terminology:**
- Root: Top node with no parent
- Leaf: Node with no children
- Height: Longest path from root to leaf
- Depth: Distance from root to node
- Degree: Number of children

**Properties:**
- Exactly one path between any two nodes
- n nodes, n-1 edges
- Connected acyclic graph

---

## Unordered Trees

Trees with no specific ordering of children.

**Types:**
- General trees (any number of children)
- K-ary trees (at most k children)

**Representations:**
- First-child/next-sibling
- Array of children
- Left-child/right-sibling

**Traversals:**
- Preorder: Root → Children
- Postorder: Children → Root
- Level-order: Breadth-first

**Applications:**
- File systems
- Organization charts
- XML/HTML DOM trees
- Game trees (minimax)

---

## Binary Search Trees

Binary tree where left subtree contains values less than parent, right subtree contains values greater.

**Properties:**
- Left child < Parent < Right child
- Inorder traversal yields sorted sequence

**Operations:**
- Search: O(log n) average, O(n) worst
- Insert: O(log n) average, O(n) worst
- Delete: O(log n) average, O(n) worst
- FindMin/Max: O(log n) average

**Deletion Cases:**
1. Leaf node: Simply remove
2. One child: Replace with child
3. Two children: Replace with inorder successor/predecessor

**Balanced BST Variants:**
- AVL trees: Height-balanced, strict balancing
- Red-Black trees: Less strict balancing, faster operations
- Splay trees: Self-adjusting, frequently accessed nodes move to root

**Applications:**
- Dictionary implementations
- Database indexing
- Expression trees
- Priority queues

---

## Partially Ordered Trees

Trees satisfying the heap property: parent is always greater (max-heap) or smaller (min-heap) than children.

**Binary Heap Properties:**
- Complete binary tree
- Heap property maintained
- Efficiently stored in arrays

**Array Representation:**
- Parent of i: ⌊(i-1)/2⌋
- Left child of i: 2i + 1
- Right child of i: 2i + 2

**Operations:**
- Insert: O(log n) - bubble up
- DeleteMin/Max: O(log n) - bubble down
- BuildHeap: O(n)
- FindMin/Max: O(1)

**Applications:**
- Priority queues
- Heap sort
- Graph algorithms (Dijkstra, Prim)

---

## Huffman Code

Optimal prefix-free binary encoding for data compression based on character frequencies.

**Algorithm:**
1. Create leaf node for each character with its frequency
2. Build min-heap of all nodes
3. Extract two minimum frequency nodes
4. Create internal node with frequency = sum of two nodes
5. Add new node back to heap
6. Repeat until one node remains (root)

**Properties:**
- Variable-length encoding
- Prefix-free (no code is prefix of another)
- Optimal for known frequencies
- More frequent characters get shorter codes

**Time Complexity:** O(n log n)

**Applications:**
- File compression (ZIP, GZIP)
- Image compression (JPEG)
- Video compression
- Network protocols

**Example:**
```
Character: A   B   C   D   E
Frequency: 5  10  12  15  28
Code:     110 111 10  0   1
```

---

## Graphs Overview

Collection of vertices (nodes) connected by edges.

**Types:**
- Directed vs. Undirected
- Weighted vs. Unweighted
- Cyclic vs. Acyclic (DAG)
- Connected vs. Disconnected
- Dense vs. Sparse

**Representations:**

**Adjacency Matrix:**
- 2D array: matrix[i][j] = 1 if edge exists
- Space: O(V²)
- Edge lookup: O(1)
- Iteration over neighbors: O(V)

**Adjacency List:**
- Array of linked lists/arrays
- Space: O(V + E)
- Edge lookup: O(degree(V))
- Iteration over neighbors: O(degree(V))

**Choosing Representation:**
- Dense graphs (E ≈ V²): Adjacency matrix
- Sparse graphs (E << V²): Adjacency list

---

## Graph Algorithms

### Minimum Cost Spanning Tree

A spanning tree that connects all vertices with minimum total edge weight.

#### Prim's Algorithm

**Strategy:** Grow MST one vertex at a time, always adding minimum weight edge that connects tree to new vertex.

**Algorithm:**
1. Start with arbitrary vertex
2. Maintain priority queue of edges from tree to non-tree vertices
3. Extract minimum edge, add vertex to tree
4. Update priority queue with new edges
5. Repeat until all vertices included

**Time Complexity:**
- With binary heap: O(E log V)
- With Fibonacci heap: O(E + V log V)

**Best for:** Dense graphs

**Pseudocode:**
```
Prim(G, w, r):
  for each u in V:
    key[u] = ∞
    parent[u] = NIL
  key[r] = 0
  Q = V  // priority queue
  while Q not empty:
    u = ExtractMin(Q)
    for each v adjacent to u:
      if v in Q and w(u,v) < key[v]:
        parent[v] = u
        key[v] = w(u,v)
```

#### Kruskal's Algorithm

**Strategy:** Sort all edges by weight, add edges in order if they don't create cycle.

**Algorithm:**
1. Sort all edges by weight
2. Initialize each vertex as separate tree (disjoint set)
3. For each edge in sorted order:
   - If endpoints in different sets, add edge to MST
   - Union the two sets
4. Stop when V-1 edges added

**Time Complexity:** O(E log E) or O(E log V)

**Data Structure:** Union-Find (Disjoint Set)

**Best for:** Sparse graphs

**Pseudocode:**
```
Kruskal(G, w):
  A = ∅
  for each vertex v in V:
    MakeSet(v)
  sort edges by weight
  for each edge (u,v) in sorted order:
    if FindSet(u) ≠ FindSet(v):
      A = A ∪ {(u,v)}
      Union(u,v)
  return A
```

---

### Graph Traversal

#### Breadth-First Search (BFS)

**Strategy:** Explore graph level by level, visiting all neighbors before moving to next level.

**Algorithm:**
1. Start from source vertex
2. Mark as visited, enqueue
3. While queue not empty:
   - Dequeue vertex
   - For each unvisited neighbor:
     - Mark visited, enqueue

**Time Complexity:** O(V + E)
**Space Complexity:** O(V)

**Data Structure:** Queue

**Properties:**
- Finds shortest path in unweighted graphs
- Visits vertices in order of distance from source
- Complete (finds solution if exists)

**Applications:**
- Shortest path in unweighted graphs
- Level-order traversal
- Connected components
- Bipartite graph testing
- Web crawling

**Pseudocode:**
```
BFS(G, s):
  for each vertex u in V:
    color[u] = WHITE
    distance[u] = ∞
    parent[u] = NIL
  color[s] = GRAY
  distance[s] = 0
  Q = ∅
  Enqueue(Q, s)
  while Q not empty:
    u = Dequeue(Q)
    for each v adjacent to u:
      if color[v] == WHITE:
        color[v] = GRAY
        distance[v] = distance[u] + 1
        parent[v] = u
        Enqueue(Q, v)
    color[u] = BLACK
```

#### Depth-First Search (DFS)

**Strategy:** Explore as far as possible along each branch before backtracking.

**Algorithm:**
1. Start from source vertex
2. Mark as visited
3. Recursively visit unvisited neighbors
4. Backtrack when no unvisited neighbors

**Time Complexity:** O(V + E)
**Space Complexity:** O(V) for recursion stack

**Data Structure:** Stack (implicit via recursion or explicit)

**Properties:**
- Explores deeply before exploring siblings
- Uses less memory than BFS for wide graphs
- Can detect cycles

**Applications:**
- Topological sorting (DAG)
- Cycle detection
- Path finding
- Connected components
- Maze solving
- Strongly connected components

**Pseudocode:**
```
DFS(G):
  for each vertex u in V:
    color[u] = WHITE
    parent[u] = NIL
  time = 0
  for each vertex u in V:
    if color[u] == WHITE:
      DFS-Visit(u)

DFS-Visit(u):
  time = time + 1
  discovered[u] = time
  color[u] = GRAY
  for each v adjacent to u:
    if color[v] == WHITE:
      parent[v] = u
      DFS-Visit(v)
  color[u] = BLACK
  time = time + 1
  finished[u] = time
```

**DFS Edge Classification:**
- Tree edges: Part of DFS tree
- Back edges: Point to ancestor (cycle indicator)
- Forward edges: Point to descendant
- Cross edges: All others

---

### Shortest Path Algorithms

#### Dijkstra's Algorithm

**Strategy:** Find shortest path from source to all vertices in weighted graph with non-negative weights.

**Algorithm:**
1. Initialize distances: source = 0, others = ∞
2. Use priority queue for vertices by distance
3. Extract vertex with minimum distance
4. For each neighbor, relax edge:
   - If new path shorter, update distance
5. Repeat until queue empty

**Time Complexity:**
- With binary heap: O((V + E) log V)
- With Fibonacci heap: O(E + V log V)

**Properties:**
- Greedy algorithm
- Only works with non-negative weights
- Single-source shortest path

**Applications:**
- GPS navigation
- Network routing protocols
- Google Maps
- Social network analysis

**Pseudocode:**
```
Dijkstra(G, w, s):
  for each vertex v in V:
    distance[v] = ∞
    parent[v] = NIL
  distance[s] = 0
  Q = V  // priority queue
  while Q not empty:
    u = ExtractMin(Q)
    for each vertex v adjacent to u:
      if distance[v] > distance[u] + w(u,v):
        distance[v] = distance[u] + w(u,v)
        parent[v] = u
```

**Relaxation:**
```
Relax(u, v, w):
  if distance[v] > distance[u] + w(u,v):
    distance[v] = distance[u] + w(u,v)
    parent[v] = u
```

#### Floyd-Warshall Algorithm

**Strategy:** Find shortest paths between all pairs of vertices using dynamic programming.

**Algorithm:**
1. Initialize distance matrix from adjacency matrix
2. For each intermediate vertex k:
   - For each pair (i,j):
     - Check if path through k is shorter
     - Update if yes: dist[i][j] = min(dist[i][j], dist[i][k] + dist[k][j])

**Time Complexity:** O(V³)
**Space Complexity:** O(V²)

**Properties:**
- All-pairs shortest path
- Works with negative weights (no negative cycles)
- Can detect negative cycles
- Dynamic programming approach

**Applications:**
- Transitive closure
- Network analysis
- Game theory
- Finding shortest paths in dense graphs

**Pseudocode:**
```
Floyd-Warshall(W):
  D = W
  for k = 1 to n:
    for i = 1 to n:
      for j = 1 to n:
        D[i][j] = min(D[i][j], D[i][k] + D[k][j])
  return D
```

**Negative Cycle Detection:**
- After algorithm completes, check diagonal
- If D[i][i] < 0 for any i, negative cycle exists

#### Warshall's Algorithm

**Strategy:** Compute transitive closure of a directed graph (determine if path exists between all vertex pairs).

**Algorithm:**
1. Initialize reachability matrix from adjacency matrix
2. For each intermediate vertex k:
   - For each pair (i,j):
     - If path i→k and k→j exist, mark i→j as reachable

**Time Complexity:** O(V³)
**Space Complexity:** O(V²)

**Difference from Floyd-Warshall:**
- Floyd-Warshall: Finds shortest paths (uses weights)
- Warshall: Finds reachability (boolean)

**Applications:**
- Reachability queries
- Strongly connected components
- Computing transitive closure
- Dependency analysis

**Pseudocode:**
```
Warshall(A):
  R = A  // reachability matrix
  for k = 1 to n:
    for i = 1 to n:
      for j = 1 to n:
        R[i][j] = R[i][j] OR (R[i][k] AND R[k][j])
  return R
```

---

## Algorithm Comparison

### Minimum Spanning Tree

| Algorithm | Time Complexity | Best For | Data Structure |
|-----------|----------------|----------|----------------|
| Prim's | O(E log V) | Dense graphs | Priority Queue |
| Kruskal's | O(E log E) | Sparse graphs | Union-Find |

### Shortest Path

| Algorithm | Type | Time Complexity | Weight Restriction |
|-----------|------|----------------|-------------------|
| Dijkstra | Single-source | O(E + V log V) | Non-negative |
| Floyd-Warshall | All-pairs | O(V³) | Any (no neg cycles) |
| Warshall | Reachability | O(V³) | Unweighted |

### Graph Traversal

| Algorithm | Order | Data Structure | Space | Use Case |
|-----------|-------|----------------|-------|----------|
| BFS | Level-by-level | Queue | O(V) | Shortest path (unweighted) |
| DFS | Depth-first | Stack | O(V) | Topological sort, cycles |

---

## Quick Reference Card

### Time Complexities Summary

**Data Structures:**
- Array: Access O(1), Search O(n), Insert O(n)
- Linked List: Access O(n), Search O(n), Insert O(1)
- Stack/Queue: All operations O(1)
- Hash Table: Average O(1), Worst O(n)
- BST: Average O(log n), Worst O(n)
- Heap: Insert/Delete O(log n), Find-min O(1)

**Sorting:**
- Merge Sort: O(n log n)
- Quick Sort: O(n log n) average, O(n²) worst
- Heap Sort: O(n log n)

**Graph Algorithms:**
- BFS/DFS: O(V + E)
- Dijkstra: O((V + E) log V)
- Prim's: O(E log V)
- Kruskal's: O(E log E)
- Floyd-Warshall: O(V³)

---

## Additional Resources

For more comprehensive course notes and study materials, visit:

**📚 Course Notes Repository:**  
[Data Structures and Algorithms Collected Notes](https://miro.com/app/board/uXjVKGSc5oY=/)

*This site contains compiled notes from multiple classes, including lecture slides, practice problems, exam reviews, and supplementary materials contributed by students and faculty.*
