#### Algorithms

An **algorithm** is a finite, precisely described sequence of steps to solve a problem or complete a task. An algorithm must terminate in a finite amount of time.

#### Abstraction

**Abstraction** is a problem-solving technique that involves removing specific details to simplify problems. There are six types of abstraction:

- **Representational abstraction**, creating a new representation by removing unnecessary details. This is related to information hiding (hiding details of an object that do not contribute to its essential characteristics).
- **Abstraction by generalisation or categorisation**, grouping by common characteristics to create hierarchical relationships (relationships of the 'is a kind of type', for example a Student 'is a kind of' Person).
- **Procedural abstraction**, representing a computational method by abstracting away the actual values used in any particular computation, analogous to a mathematical formula.
- **Functional abstraction**, representing an unknown particular computation method.
- **Data abstraction**, hiding details of how data are actually represented. This allows isolating how compound data objects are used from how they are constructed, for example implementing a stack as an array and a pointer for the top of the stack.
- **Problem abstraction**, removing details until the problem reduces to a problem that has already been solved.

#### Decomposition

**Procedural decomposition** is where a problem is broken down into a number of sub-problems, with each sub-problem accomplishing a specific task. Each sub-problem may be further subdivided.

#### Composition

**Composition abstraction** is where procedures are combined to form compound procedures, by "plugging" outputs from some procedures into the inputs of others.

#### Automation

**Automation** is where models of real-world objects are used to solve problems. Automation involves:

- Designing algorithms to model the real world
- Implementing the algorithms in code
- Implementing the models in data structures
- Executing the code

## Sets

A **set** is an unordered collection of unique values. Sets can be constructed:

- Explicitly, e.g. $S = \{0, 1, 2, 3\}$
- Through set comprehension, e.g. $S = \{x | x \in \mathbb{N} \wedge x \le 3\}$
  The empty set, $\{\}$ or $\emptyset$ is the set with no elements.

Sets can be represented compactly, for example:
$$\{0^n1^n | n\ge 1\}$$
is the set of all strings with $n$ 0s followed by $n$ 1s.

A **subset** ($\subseteq$) is a set where every element is in some larger set. For example, $\{0, 1, 2, 3\}$ is a subset of $\mathbb{N}$. A **proper subset** ($\subset$) has the additional requirement that there is an element in the larger set not in the subset.

Types of set include:

- A **finite** set is one whose elements can be counted off by natural numbers up to a finite number.
- An **infinite** set is a set with an unlimited number of elements, for example the set of natural numbers $\mathbb{N}$, or the set of real numbers $\mathbb{R}$.
- A **countable set** is a set with the same cardinality (number of elements) as a subset of the natural numbers.
- A **countably infinite set** is a set that can be counted off by the natural numbers. The real numbers are not countable.
  The **cardinality** of a finite set is the number of elements in that set.

The **Cartesian products** of two sets, written $X \times Y$, is the set of all ordered pairs $(a, b)$ where $a$ is a member of $A$ and $b$ is a member of $B$. For example:

$$
\{1, 2\} \times \{3, 4\} = \{(1, 3),\,(1, 4),\,(2, 3),\,(2, 4)\}
$$

The four set operations are:

- **Membership** - $a \in S$ if $a$ is in the set $S$
- **Union** - the union of sets $A$ and $B$, $A \cup B$ are all the elements in $A$ or $B$ (or both)
- **Intersection** - the intersection of sets $A$ and $B$, $A \cap B$ are all the elements in both $A$ and $B$
- **Difference** - the set difference $A/B$ is defined as all the items in $A$ that are not in $B$ ($A/B = \{x : x\in A \wedge x\not\in B\}$)
