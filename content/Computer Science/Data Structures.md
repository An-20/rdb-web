## Data structures
A **data structure** is a concrete implementation of a data type, in contrast to an **abstract data type**, which defines the possible values and operations of a data type.

A **static** data structure is fixed in size, and cannot change the amount of memory it uses at runtime, e.g. an array. Static data structures cannot grow in size. Static data structures can cause inefficient memory usage, but are typically faster. A **dynamic** data structure can grow and shrink it size at runtime, e.g. a Python list.

## Queues
A **queue** is a first in first out (FIFO) data structure. New elements can only be added to the rear of a queue, and elements can only be removed from the front of a queue. Operations on queues include:
- Enqueue an item
- Dequeue an item
- Test for an empty queue
- Test for a full queue
#### Implementations
###### Linear queue
In a linear queue, pointers to the front and back, and the maximum queue size are stored. Items can be added until the rear pointer points to the last element of the queue.
###### Circular queue
In a circular queue, when the rear pointer points to the last array element, the next item added will be added back at the front of the array, 'looping' round.
###### Priority queue
A priority queue is ordered based on the priority of its items, and each new item is inserted so that the queue is sorted based on priority.

## Stacks
A **stack** is a last in first out (LIFO) data structure. Operations on stacks include:
- Push an item to the top
- Pop an item from the top
- Peek at the top item without removing it
- Test for an empty stack
- Test for a full stack

## Hash tables
A **hash table** stores a collection of items for quick retrieval. It is typically implemented with an empty array. To insert an item, a hashing algorithm is applied to get the index in the array to store at. Similarly, to retrieve an item, the index in the array is obtained by applying the hashing algorithm. If a collision occurs, the next available space is typically used (linear probing).

A hash table can be used to implement a **dictionary**, which is a mapping from keys to values.

## Vectors
A **vector** is a list of numbers ($[2.71, 3.14, -1.0]$), a function ($f(0) = 2.71, f(1) = 3.14, f(2) = -1.0$), and a geometric place in space ($\mathbb{R}^3$).

The **convex combination** of two vectors $u$ and $v$ is given by $\alpha u + \beta v$ where $\alpha, \beta \gt 0$ and $\alpha + \beta = 1$.

The **dot product** of two vectors $u = [u_1, \dots, u_n]$ and $v = [v_1, \dots, v_n]$ is $u \cdot v = u_1v_1 + \cdots + u_n v_n$. This can be used to find the angle between two vectors.

## Graphs
**Graphs** are used to model more complex relationships. A graph is the set of nodes and the set of edges connecting nodes. A graph can be directed or undirected, and weighted or unweighted.

An **adjacency matrix** can be used to represent a graph, with a two-dimensional array storing each potential edge and its weight. However, this can use large amounts of memory.

An **adjacency list** is more suitable for sparsely connected graphs. A list stores dictionaries for each edge, with each dictionary storing neighbouring nodes and the corresponding edge weights as key value pairs. 
#### Trees
Trees are connected, undirected graphs with no cycles.

A **rooted tree** is a tree where one node has been designated as the root. The root is the only node with no parent and all other nodes are descendants of the root. A **binary tree** is a rooted tree where each node has at most two children.
