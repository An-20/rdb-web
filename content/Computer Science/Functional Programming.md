A **function** is a rule that, for each element in some set A of inputs, assigns an output chosen from set B, but without necessarily using every member of B. The **domain** is a set from which the function’s input values are chosen. The **co-domain** is a set from which the function’s output values are chosen.

A **higher-order** function takes a function as an argument or returns a function as a result, or does both.

A function `f` has a function type `f: A -> B`, where `A -> B` denotes the type of a function that takes an argument type `A` and outputs a result type `B`.

First-class objects are objects which can:
- appear in expressions
- be assigned to a variable
- be assigned as arguments
- be returned in function calls.

In functional languages, a function is a first-class object. This means that it can be an argument to another function as well as the result of a function call.

Partial function application is where some arguments of a multi-argument function are fixed, giving a new function with less arguments. For example, consider the function `add` that takes two integers and adds them. This gives `add: Integer -> (Integer -> Integer)`. Partial function application means that `add 4` is a new function that when applied to an integer, returns that integer plus 4.

The brackets can be removed to give `add: Integer -> Integer -> Integer`. The function add is now viewed as taking one argument after another and returning a result of data type integer.

The operation **functional composition** combines two functions to get a new function. Given two functions `f: A -> B` and `g: B -> C`, the function `g ○ f`, called the **composition** of g and f, is a function whose domain is A and co-domain is C. The function on the right is applied first.

#### Functional languages
- **map** is the name of a higher-order function that applies a given function to each element of a list, returning a list of results. 
- **filter** is the name of a higher-order function that processes a data structure, typically a list, in some order to produce a new data structure containing exactly those elements of the original data structure that match a given condition.
- **reduce** or **fold** is the name of a higher-order function which reduces a list of values to a single value by repeatedly applying a combining function to the list values.
For all three of these higher-order functions, the function argument comes first, and the list argument comes second.

A list has a **head** and a **tail**, where the head is the first item in the list, and a tail is the remainder of the list, written as `head:tail` in Haskell. The head is a list element, while the tail is a list itself. `4:[3, 5]` would represent a list with head 4 and tail `[3, 5]`. A list can also be empty.
