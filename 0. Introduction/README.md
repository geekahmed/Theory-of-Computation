# Chapter 0. Introduction
## Automata, Computability, and Complexity
> What are the fundamentals capabilities and limitations of computers?
- What makes some problems computationally hard and others easy?. This is the central question of complexity theory.
- One applied area that has been affected directly by complexity theory is the ancient field of cryptography.
- Complexity theory has pointed cryptographers in the direction of computationally hard problems around which they have designed revolutionary new codes.
- The theories of computability and complexity are closely related.
	- In complexity theory, the objective is to classify problems as easy ones and hard ones; whereas in computability theory, the classification of problems is by those that are solvable and those that are not.
	- Computability theory introduces several of the concepts used in complexity theory.
- Automata theory deals with the definitions and properties of mathematical models of computation.
## Mathematical Notation and Terminology
### SETS
- A set is a group of objects represented as a unit.
- The objects in a set are called its elements or members.
- For two sets A and B, we say that A is a subset of B, written A ⊆ B, if every member of A also is a member of B.
- A is a proper subset of B, written A $\subset$ B, if A is a subset of B and not equal to B.
	- In another words, if A is a proper subset of B, then all elements of A are in B but B contains at least one element that is not in A.
	- For example, if B = {1, 3, 5} then A = {1, 5} is a proper subset of B.
- The order of describing a set doesn’t matter, nor does repetition of its members.
	-  If we do want to take the number of occurrences of members into account, we call the group a multiset instead of a set.
- An infinite set contains infinitely many elements.
- The set with zero members is called the empty set and is written ∅.
- A set with one member is sometimes called a singleton set, and a set with two members is called an unordered pair.
- If we have two sets A and B, the union of A and B, written A∪B, is the set we get by combining all the elements in A and B into a single set.
- The intersection of A and B, written A ∩ B, is the set of elements that are in both A and B.
- The complement of A, written -A, is the set of all elements under consideration that are not in A.
### SEQUENCES AND TUPLES
- A sequence of objects is a list of these objects in some order and is designated by writing the list within parentheses.
- The order and repititions matter here in the sequences.
- Finite sequences often are called tuples.
	- A sequence with k elements is a k-tuple.
	- A 2-tuple is also called an ordered pair.
- The power set of A is the set of all subsets of A.
	- If A is the set {0, 1}, the power set of A is the set { ∅, {0}, {1}, {0, 1} }.
- If A and B are two sets, the Cartesian product or cross product of A and B, written A × B, is the set of all ordered pairs wherein the first element is a member of A and the second element is a member of B.
### FUNCTIONS AND RELATIONS
- A function is an object that sets up an input–output relationship.
- The set of possible inputs to the function is called its domain.
- The outputs of a function come from a set called its range.
- A function that does use all the elements of the range is said to be onto the range.
- A function with k arguments is called a k-ary function, and k is called the arity of the function.
- A predicate or property is a function whose range is {TRUE, FALSE}.
- A binary relation R is an equivalence relation if R satisfies three conditions:
	- R is reflexive if for every x, xRx;
	- R is symmetric if for every x and y, xRy implies yRx; and
	- R is transitive if for every x, y, and z, xRy and yRz implies xRz.
- 
## Definitions, Theorems, and Proofs
## Types of Proofs