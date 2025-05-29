## Definitions
###### Binary operation
A **binary operation** is a process that involves two members of a set and produces a result. For example, the operation $\star$ could be defined as $a \star b = a^2 + b^2$.
- A binary operation $\star$ is **closed** over set $S$ if $\forall a, b \in S$, $a \star b \in S$.
- A binary operation $\star$ is **commutative** over set $S$ if $\forall a, b \in S$, $a \star b  = b \star a$.
- A binary operation $\star$ is **associative** over set $S$ if $\forall a, b, c \in S$, $a \star (b \star c) = (a \star b) \star c$.
- A binary operation $\star$ has an **identity** element $e$ in set $S$ if there exists a $e \in S$ such that $a \star e = e \star a = a$.
- A binary operation $\star$ has an **inverse** of element $a$, denoted $a^{-1}$, in set $S$ with identity $e$ if there is an $a^{-1} \in S$ such that $a \star a^{-1} = a^{-1} \star a = e$. An element $a$ is **self-inverse** if $a = a^{-1}$, and thus if $a^2 = e$.
###### Cayley table
A Cayley table shows the results of performing an operation with the element in the row first, and the element in the column second. A Cayley table is symmetric about the leading diagonal if the operation is commutative.
###### Latin square
A Latin square is a square table where each element appears exactly once in each row and column. The Cayley table of any group is a Latin square, but not all Latin squares represent a group[^1].

## Groups
A set $G$ under a binary operation $\star$ forms a group if it satisfies the **group axioms**:
- $G$ is closed under $\star$,
- the operation $\star$ is associative, 
- there exists an identity $e$ in $G$,
- and each element in $G$ has an inverse in $G$.
An **Abelian group** is a group where the binary operation $\star$ is also commutative.

The **order of a group** is the number of elements in the group.
The **order of an element** is the power an element must be raised to in order to get the identity element. The order of an element $a$ is $n$ such that $a^n = e$, where $e$ is the identity. The order of $e$ is 1.

#### Cyclic groups
A **cyclic** group is where each element of the group $G$ can be expressed as $a^n$, where $a$ is a **generator** of the group and $n\in\mathbb{Z}$. A cyclic group can have multiple generators; any element with order equal to the order of the group is a generator.

Cyclic groups, denoted $Z_n$ (where $n$ is the order of the group), have the following properties:
- Commutative binary operation (Abelian group)
- There must be at least one generator $a$ of order $n$, such that $a^n=e$
- If the order of a group $G$ is $p$, where $p$ is prime, then $G$ must be cyclic; groups of prime order must be cyclic.

#### Subgroups
A subgroup of a group $G$ is a subset of $G$ that satisfies the group axioms.
- The **trivial subgroup** is a subgroup with just the identity element.
- A **proper subgroup** is a subgroup of $G$ that is not $G$ itself (same idea as a proper subset).
Any subgroup must contain the identity element. The identity element and any self-inverse element forms a subgroup.

**Lagrange's theorem**[^2] states that the order of a subgroup $H$ must be a factor of the order of the group $G$. Therefore:
- The order of each element of $G$ is a factor of the order of $G$ (because each element can generate a cyclic subgroup $H$ such that the order of $H$ is equal to the order of the element, which must therefore be a factor of the order of $G$).
- If $G$ has a prime order, then $G$ has no proper subgroups[^3].

## Groups to know
The specification requires knowledge of all groups with order $\le 7$. This includes cyclic groups, $K_{4}$ (the Klein 4-group), and $S_{3}$ (the symmetric group of order 3). The cyclic groups $Z_{n}$ can be thought of as the set of integers $\{0,1,2,\dots,n-1\}$ under the operation of addition modulo $n$.
#### Order 1
There is one trivial Abelian cyclic group of order 1, $Z_1$:
$$
\begin{array}{l|l}
    & e \,\,\, \\
    \hline
    e & e
\end{array}
$$
#### Order 2
There is one Abelian cyclic group of order 2, $Z_2$:
$$
\begin{array}{l|ll}
    & e & a\,\,\,  \\
    \hline
    e & e & a \\
    a & a & e
\end{array}
$$
#### Order 3
There is one Abelian cyclic group of order 3, $Z_3$:
$$
\begin{array}{l|ll}
    & e & a & b\,\,\,  \\
    \hline
    e & e & a & b \\
    a & a & b & e \\
    b & b & e & a
\end{array}
$$
#### Order 4
There are two groups of order 4: the Abelian cyclic group $Z_4$ and the Abelian Klein 4-group $K_4$.
$$
Z_4:\,\,\,
\begin{array}{l|ll}
    & e & a & b & c\,\,\,  \\
    \hline
    e & e & a & b & c \\
    a & a & b & c & e \\
    b & b & c & e & a \\
    c & c & e & a & b
\end{array}

\,\,\,\,\,\,\,\,\,\,\,\,
K_4:\,\,\,
\begin{array}{l|ll}
    & e & a & b & c\,\,\,  \\
    \hline
    e & e & a & b & c \\
    a & a & e & c & b \\
    b & b & c & e & a \\
    c & c & b & a & e
\end{array}
$$
Where in $K_{4}$, each element is self-inverse. $K_{4}$ can also be thought of as the symmetries of a rectangle, where $a,b,c$ are a $180\degree$ rotation, or reflections in either axis (thus the elements are self-inverse).
#### Order 5
There is one Abelian cyclic group of order 5, $Z_5$.
$$
\begin{array}{l|lllll}
    & e   & a   & b & c  & d\,\,\, \\
    \hline
    e & e & a & b & c & d \\
    a & a & b & c & d & e \\
    b & b & c & d & e & a \\
    c & c & d & e & a & b \\
    d & d & e & a & b & c
\end{array}
$$
#### Order 6
There are two groups of order 6: the Abelian cyclic group $Z_6$ and the symmetric group $S_3$ (or the dihedral group $D_3$)[^4].
$$
Z_6:\,\,\,
\begin{array}{l|llllll}
    & e & p & q & r & s & t\,\,\, \\
    \hline
    e & e & p & q & r & s & t \\
    p & p & q & r & s & t & e \\
    q & q & r & s & t & e & p \\
    r & r & s & t & e & p & q \\
    s & s & t & e & p & q & r \\
    t & t & e & p & q & r & s
\end{array}
\,\,\,\,\,\,\,\,\,\,\,\,
D_6:\,\,\,
\begin{array}{l|llllll}
    & e & p & q & r & s & t\,\,\, \\
    \hline
    e & e & p & q & r & s & t \\
    p & p & e & t & s & r & q \\
    q & q & s & e & t & p & r \\
    r & r & t & s & e & q & p \\
    s & s & q & r & p & t & e \\
    t & t & r & p & q & e & s
\end{array}
$$
The symmetric group $S_{3}$ can be thought of as the group of all possible ways to rearrange three objects. $S_{3}$ is the same as $D_{3}$, which can be thought of as the symmetries of an equailateral triangle ($0\degree,120\degree,240\degree$rotations and reflections across the three medians).

Notes on $S_{3}$:
- It is the smallest non-Abelian group, so the Cayley table is not symmetric about the diagonal.
- In the above Cayley table, $e$ is the identity transformation $p,q,r$ can be thought of as reflections across the medians of an equilaterial triangle, and $s$ and $t$ can be thought of as $120\degree$ and $240\degree$ rotations.
- Note how $p,q,r$ are all self-inverse (as expected for reflections) and how $s$ and $t$ are inverses of each other (as expected for $120\degree$ and $240\degree$ rotations).
 
#### Order 7
There is one Abelian cyclic group of order 7, $Z_7$:
$$
\begin{array}{l|llllll}
    & e & p & q & r & s & t & u\,\,\, \\
    \hline
    e & e & p & q & r & s & t & u \\
    p & p & q & r & s & t & u & e \\
    q & q & r & s & t & u & e & p \\
    r & r & s & t & u & e & p & q \\
    s & s & t & u & e & p & q & r\\
    t & t & u & e & p & q & r & s\\
    u & u & e & p & q & r & s & t\\
\end{array}
$$

[^1]: **Footnote on Latin Squares**
	The Cayley table of any group is a Latin square, but not all Latin squares represent a group. A Latin square represents a quasigroup, where there is a closed operation and an inverse element for all elements, but there is not necessarily associativity or an identity.

[^2]: **Footnote on Lagrange's Theorem**
	This is A-level content, but it's useful at AS so it's here anyways.

[^3]: **Footnote on proper subgroups and the trivial subgroup**
	A group $G$ of prime order will still have the trivial subgroup. Whether the trivial subgroup is a proper subgroup is... debateable (the textbook says no, but Integral says yes).

[^4]: **Footnote on $S_{3}$ / $D_{3}$ / $D_{6}$**
	The Internet can't agree on whether this group is $D_{3}$ or $D_{6}$, so maybe just call it $S_{3}$ (OCR use $S_{3}$).
