#### Graph traversal algorithms
There are two basic ways to **traverse** a graph to visit every node:
- A **depth-first** traversal uses a **stack**, which can be implemented automatically by using the call stack and recursion. Alternatively, a non-recursive implementation could manually maintain a stack.
- A **breadth-first** traversal uses a queue.

In a **depth-first** traversal, the algorithm goes down one route as possible before backtracking and taking the next route. Depth-first traversals can be used to **navigate a maze**.
- Start with a stack with the start node and empty list of visited nodes
- Pop the top node off the stack. If it has not been visited yet, mark it as visited, then add all of its neighbours to the stack. Repeat until the stack is empty.[^1]

In a **breadth-first** traversal, nodes are visited in order of distance from the start node. Breadth-first traversals can be used to find the **shortest path** for an **unweighted graph**.
- Start with a queue with the start node and list of visited nodes with the start node
- Dequeue the next node in the queue. Add all of its unvisited neighbours to the queue and mark them as visited. Repeat until the queue is empty.[^2]

#### Tree traversal algorithms
There are three basic tree-traversal algorithms:
- **Pre-order**: Visit the root, then the left sub-tree, then the right sub-tree. Pre-order traversals can be used to **copy a tree**.
- **In-order**: Visit the left sub-tree, then the root, then the right sub-tree. In-order traversals can be used to **output the contents of a binary search tree in ascending order**.
- **Post-order**: Visit the left sub-tree, then the right sub-tree, then the root. Post-order traversals can be used to **convert infix expressions to RPN**, **produce a postfix expression from an expression tree**, or **empty a tree**.

#### Reverse Polish notation
In **Reverse Polish (postfix) notation**, the operator follows the operand. For example, the infix expression `3 - 4 * 2` becomes `3 4 2 * -`. RPN is used because:
- RPN **eliminates the need for brackets** in sub-expressions.
- RPN expressions are in a form **suitable for evaluation using a stack**. 
- RPN is used in interpreters based on stacks, for example Postscript and bytecode.

#### Searching algorithms
In **linear search**, items in a list are checked one-by-one to see if they are equal to the item being searched for. Linear search has a time complexity of $O(n)$. 

In **binary search**, the number of items being searched is repeatedly halved by comparing the middle item of the list with the item being searched for, which requires a **sorted** list. Binary search has a time complexity of $O(\log n)$.

In **binary tree search**, the same idea as binary search is used, except at each stage, a left or right subtree is eliminated. Binary tree search also has a time complexity of $O(\log n)$.

#### Sorting algorithms
In **bubble sort**, with each pass the largest item is 'bubbled' to the end of the list, by swapping each pair of items if the first one is larger. Each pass has $n$ comparisons, and $n$ passes are needed, giving a time complexity of $O(n^2)$[^3].

In **merge sort**:
- The list is recursively split into sublists until each sublist contains one element.
- The sublists are repeatedly merged to produce new sorted sublists, until there is one sublist remaining, which is the sorted list.
Merge sort is an example of the 'divide and conquer' approach to problem solving. The time complexity of merge sort is $O(n \log n)$.

#### Optimisation algorithms
**Dijkstra's algorithm** is used to find the shortest path between a specific start node and every other node in a weighted graph. It is similar to a breadth first traversal, but uses a priority queue.

The pseudocode of Dijkstra's algorithm is as follows (SPEC: "Students will not be expected to recall the steps in Dijkstra's shortest path algorithm."):
```
procedure Djkstra(G, v) is
    let the distance of the start node be zero
    let the distance of all other nodes be infinity
	let Q be a priority queue with the start node
	let the parent of all nodes be -1
	
	while Q is not empty do
		v = s.dequeue()
		for each unvisited neighbour u of v
			newDistance = distanceToV + distanceFromVToU
			if newDistance < distanceAtU THEN
			    distanceAtU = newDistance
			    parentOfU = v
```


[^1]: **Footnote on depth-first traversals**
	It may be easier to understand by just reading the pseudocode. Both recursive and non-recursive examples are below (from [Wikipedia](https://en.wikipedia.org/wiki/Depth-first_search)).
```
procedure DFS(G, v) is
    label v as visited
    for all directed edges from v to w that are in G.adjacentEdges(v) do
        if vertex w is not labeled as visited then
            recursively call DFS(G, w)

procedure DFS_iterative(G, v) is
    let S be a stack
    S.push(v)
    while S is not empty do
        v = S.pop()
        if v is not labeled as visited then
            label v as visited
            for all edges from v to w in G.adjacentEdges(v) do 
                S.push(w)
```

[^2]:**Footnote on breadth-first traversals**
	It may be easier to understand by just reading the pseudocode (from [Wikipedia](https://en.wikipedia.org/wiki/Depth-first_search)).
```
procedure BFS(G, root) is
    let Q be a queue
    label root as visited
    Q.enqueue(root)
    while Q is not empty do
        v = Q.dequeue()
        if v is the goal then
            return v
        for all edges from v to w in G.adjacentEdges(v) do
            if w is not labeled as visited then
                label w as visited
                w.parent := v
                Q.enqueue(w)
```

[^3]:**Footnote on time complexity of bubble sort**
	Any reasonable implementation of bubble sort (though is there such thing?) would have $n-1$ comparisons on the first pass, $n-2$ on the second, etc. Still, the sum of $(n-1) + (n-2) + \dots + 2 + 1$  is a quadratic function in $n$.
	