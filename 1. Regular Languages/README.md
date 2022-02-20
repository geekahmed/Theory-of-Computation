# Chapter 1. Regular Languages
## Finite Automata
- Finite automata are good models for computers with an extremely limited amount of memory.
- Finite automata and their probabilistic counterpart Markov chains are useful tools when we are attempting to recognize patterns in data.
- ![A finite automaton called M1 that has three states](https://github.com/geekahmed/Theory-of-Computation/blob/main/1.%20Regular%20Languages/Images/M1.png?raw=true)
	- A finite automaton called M1 that has three states.
	- The three states are labeled q1, q2, and q3.
	- The start state, q1, is indicated by the arrow pointing at it from nowhere.
	- The accept state, q2, is the one with a double circle.
	- The arrows going from one state to another are called transitions.
	- The output is either accept or reject.
	- The output is accept if M1 is now in an accept state and reject if it is not.
### Formal Definition of Finite Automata
- A finite automaton is a 5-tuple (Q, Σ, δ, q0, F)
	- Q is a finite set called the states.
	- Σ is a finite set called the alphabet.
	- δ : Q × Σ−→Q is the transition function.
	- q0 ∈ Q is the start state.
	- F ⊆ Q is the set of accept states.
- Aetting F to be the empty set ∅ yields 0 accept states, which is allowable.
- The transition function δ specifies exactly one next state for each possible combination of a state and an input symbol.
- Exactly one transition arrow exits every state for each possible input symbol.
- If A is the set of all strings that machine M accepts, we say that A is the language of machine M and write L(M) = A.
	- We say that M recognizes A or that M accepts A.
	- A machine may accept several strings, but it always recognizes only one language.
	-  If the machine accepts no strings, it still recognizes one language— namely, the empty language ∅.
### Formal Definitation of Computation
### Designing Finite Automata

