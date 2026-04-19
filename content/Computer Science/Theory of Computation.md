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
- Executing the code.

*IS*: Computer science involves building clean abstract models (abstractions) describing messy, noisy real-world objects or phenomena. Computer scientists choose what to include or discard in a model, to use the minimum amount of detail necessary to model the problem in order to solve a given problem to the required degree of accuracy.

Computer science puts models into action to solve problems. This involves creating algorithms that use the data that has been modelled.

#### Sets
A **set** is an unordered collection of unique values. Sets can be constructed:
- Explicitly, e.g. $S = \{0, 1, 2, 3\}$
- Through set comprehension, e.g. $S = \{x | x \in \mathbb{N} \wedge x \le 3\}$, where $|$ means 'such that'.
- In Python, `{2 * x for x in {1, 2, 3}}` constructs `{2, 4, 6}`. This is a set comprehension over the set `{1, 2, 3}`.

Some symbols are expected to be known:
- The **empty set**, $\{\}$ or $\emptyset$ is the set with no elements.
- The symbol $\land$ means **AND**.

Sets can be represented compactly, for example:
$$\{0^n1^n | n\ge 1\}$$
is the set of all strings with $n$ 0s followed by $n$ 1s.

A **subset** ($\subseteq$) is a set where every element is in some larger set. For example, $\{0, 1, 2, 3\}$ is a subset of $\mathbb{N}$. A **proper subset** ($\subset$) has the additional requirement that there is an element in the larger set not in the subset (i.e. the two sets are not identical).

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
- **Membership**: $a \in S$ if $a$ is in the set $S$
- **Union**: the union of sets $A$ and $B$, $A \cup B$ are all the elements in $A$ or $B$ (or both)
- **Intersection**: the intersection of sets $A$ and $B$, $A \cap B$ are all the elements in both $A$ and $B$
- **Difference**: the set difference $A/B$ is defined as all the items in $A$ that are not in $B$ ($A/B = \{x : x\in A \wedge x\not\in B\}$)

#### Regular expressions
A **regular expression** is a way of describing a set, allowing particular types of languages to be described in a convenient shorthand notation. For example:
- `a (a|b)*` generates `{a, aa, ab, aaa, aab, aba, abb, ...}`
- `aa+` generates `{aa, aaa, aaaa, ...}`
- `a (a|b)?` generates `{a, aa, ab}`.

The following **metacharacters** are expected to be known:
- `*`: 0 or more repetitions
- `+`: 1 or more repetitions
- `?`: 0 or 1 repetitions (i.e. optional)
- `|`: alternation (i.e. 'or')
- `()`: grouping regular expressions.

The precedence of the above metacharacters is (from highest to lowest):
- `()` grouping
- `* + ?` characters
- `|` alternation.
For example, `a|bc+` generates `{a, bc, bcc, bccc, ...}`

Regular expressions and FSMs are equivalent ways of defining a regular language. A **regular language** is any language that can be represented by a regular expression, or any language that a FSM will accept.

###### Context-free languages
A **context-free language** is a wider set of languages following context-free grammars, which are formed of production rules. Context-free languages can be represented using **Backus-Naur Form** (BNF):
```
<integer> ::= <digit> | <digit> <integer>
<digit> ::= 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9
<number> ::= <integer> | <integer> . <integer> 
```
(this is a bad example)

BNF represents some languages that cannot be represented using regular expressions because it allows recursion.

#### Classification of algorithms
Algorithms can be compared by expressing their **complexity** as a function relative to the size of the problem input. Algorithms can be more **efficient time-wise**, or **space-wise**. 

*IS*: Efficiently implementing automated abstractions means designing data models and algorithms that run quickly while taking up minimal amounts of resources such as memory.

Mathematical functions are used to describe complexities:
- A **linear function** is of the form $y = kx$, for a constant $k$, e.g. $y = 2x$.
- A **polynomial function** is of the form $y = k_1x^n + \cdots$, for a constant $k$ and $n$, e.g. $y = 2x^3$.
- An **exponential function** is of the form $y = k^x$, for a constant $k$, e.g. $y = 2^x$.
- A **logarithmic function** is of the form $y = \log_k(x)$, for a constant $k$, e.g. $y = \log_{10}(x)$.

The number of **permutations** of $n$ distinct objects is $n$ factorial, denoted $n!$.

Big-O notation is used to express time complexity. The following complexities are expected to be known:
- **Constant time**, e.g. getting the last item in a list
- **Logarithmic time**, e.g. binary search
- **Linear time**, e.g. linear search
- **Polynomial time**, e.g. bubble sort ($O(n^2)$)
- **Exponential time**, e.g. a naive implementation of Fibonacci numbers.

Algorithmic complexity and hardware impose limits on what can be computed. Problems can be classified as being:
- **Tractable**: problems that have a polynomial (or less) time solution
- **Intractable**: problems that have no polynomial (or less) time solution. Heuristic methods are often used when tackling intractable problems.

Some problems cannot be solved algorithmically. For example, the **Halting problem** is the unsolvable problem of determining, without executing the program, whether any program will eventually stop if given a particular input. This demonstrates that there are some problems that cannot be solved by a computer.

#### Turing machines
**Turing machines** are a model of computation. They can be viewed as a computer with a single fixed program, expressed by:
- A finite **set of states** in a **state transition diagram**. One of the states is a **start state**, and states with no outgoing transitions are **halting states**.
- A finite **alphabet** of symbols.
- An **infinite tape** with marked-off squares.
- A **read-write head** that travels along the tape, one square at a time.

A **Universal Turing machine** is a Turing machine that could simulate any other Turing machine by reading a description of it from the input tape. Turing machines are important as they provide a **general / formal model of computation**, giving a definition of what is computable.
