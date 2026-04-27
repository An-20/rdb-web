Two events $A$ and $B$ are **mutually exclusive** if $P(A \,\text{and}\, B) = 0$. Events that are mutually exclusive can have their probabilities added.

Set notation can be used to describe probabilities:
- $A \cup B$ is the **union** of $A$ and $B$, meaning when either $A$ or $B$ (inclusive) happens.
- $A \cap B$ is the **intersection** of $A$ and $B$, meaning when both $A$ and $B$ happen.
- $A'$ is the **complement** of $A$, meaning when everything that is not $A$ happens.

A Venn diagram can be used to find the formula relating the probabilities of the union and intersection:
$$
P(A \cup B) = P(A) + P(B) - P(A \cap B)
$$
Events $A$ and $B$ are **independent** if $P(A\cap B) = P(A) P(B)$. Another condition is given by:
$$
A, B\,\,\textrm{independent} \iff P(A|B) = P(A)
$$
because $P(A|B) = \frac{P(A\cap B)}{P(B)} = \frac{P(A)P(B)}{P(B)} = P(A)$.

$P(A|B)$ is the probability of $A$ happening given that $B$ has happened (the probability of $A$ given $B$). We can use the formula:
$$
P(A|B) = \frac{P(A \cap B)}{P(B)}
$$
Rearranging, we get:
- $P(A \cap B) = P(A|B) \times P(B)$
- $P(A|B) \times P(B) = P(B|A) \times P(A)$
