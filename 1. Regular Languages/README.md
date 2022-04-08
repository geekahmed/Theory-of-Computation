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
- Let $M = (Q, Σ, δ, q_0, F)$ be a finite automaton and let $w = w_1w_2...w_n$ be a string where each $w_i$ is a member of the alphabet $Σ$.
	- Then M accepts $w$ if a sequence of states $r_0, r_1, . . . , r_n$ in $Q$ exists with three conditions:
	1. $r_0 = q_0$,: the machine starts in the start state.
	2. $δ(r_i , w_{i+1}) = r_{i+1}, for \space i = 0, . . . , n − 1$,: the machine goes from state to state according to the transition function.
	3. and $r_n ∈ F$: t the machine accepts its input if it ends up in an accept state.
- M recognizes language A if A = {w| M accepts w}.
- A language is called a regular language if some finite automaton recognizes it.
### The Regular Operations
- Let A and B be languages. We define the regular operations union, concatenation, and star as follows:
	- Union: A ∪ B = {x| x ∈ A or x ∈ B}.
	- Concatenation: A ◦ B = {xy| x ∈ A and y ∈ B}.
	- Star: A∗ = {x1x2 . . . xk| k ≥ 0 and each xi ∈ A}.
- Let the alphabet Σ be the standard 26 letters {a, b, . . . , z}. If A = {good, bad} and B = {boy, girl}, then
	- A ∪ B = {good, bad, boy, girl},
	- A ◦ B = {goodboy, goodgirl, badboy, badgirl}, and
	- A∗ = {ε, good, bad, goodgood, goodbad, badgood, badbad, goodgoodgood, goodgoodbad, goodbadgood, goodbadbad, . . . }.
- A collection of objects is closed under some operation if applying that operation to members of the collection returns an object still in the collection.
- The class of regular languages is closed under the union operation.
- The class of regular languages is closed under the concatenation operation.

**Proof on closure under union operation.**

> Let M1 recognize A1, where M1 = (Q1, Σ, δ1, q1, F1), and M2 recognize
> A2, where M2 = (Q2, Σ, δ2, q2, F2).
> 
> Construct M to recognize A1 ∪ A2, where M = (Q, Σ, δ, q0, F).
> 
> 1. Q = {(r1, r2)| r1 ∈ Q1 and r2 ∈ Q2}. This set is the Cartesian product of sets Q1 and Q2 and is written Q1 ×Q2. It is the set of all pairs of states, the first from Q1 and the second from Q2.
> 2. Σ, the alphabet, is the same as in M1 and M2. In this theorem and in all subsequent similar theorems, we assume for simplicity that both M1 and M2 have the same input alphabet Σ. The theorem remains true if they have different alphabets, Σ1 and Σ2. We would then modify the proof to let Σ = Σ1 ∪ Σ2.
> 3. δ, the transition function, is defined as follows. For each (r1, r2) ∈ Q and each a ∈ Σ, let δ ((r1, r2), a) =( δ1(r1, a), δ2(r2, a) ). Hence δ gets a state of M (which actually is a pair of states from M1 and M2), together with an input symbol, and returns M’s next state.
> 4. . q0 is the pair (q1, q2).
> 5. F is the set of pairs in which either member is an accept state of M1 or M2. We can write it as F = {(r1, r2)| r1 ∈ F1 or r2 ∈ F2}. This expression is the same as F = (F1 × Q2) ∪ (Q1 × F2).
> 
> ***Note:*** F1 X F2  would define M’s accept states to be those for which both members of the pair are accept states. In this case, M would accept a string only if both M1 and M2 accept it, so the resulting language would be the intersection and not the union. In fact, this result proves that the class of regular languages is closed under intersection.

## Non-Determinism
- Nondeterminism is a useful concept that has had great impact on the theory of computation.
- In a nondeterministic machine, several choices may exist for the next state at any point.
	- There is no physical machine exists for NFA model.
- Nondeterminism is a generalization of determinism, so every deterministic finite automaton is automatically a nondeterministic finite automaton.
- Comparison between NFA and DFA:
- 
|               | NFA                          | DFA                   |
|:-------------:|:----------------------------:|:---------------------:|
| Symbol Arrows | 0,1, or many for each symbol | 1                     |
| Labels        | Alphabet Symbols or Epsilon  | Alphabet Symbols only |
- How does an NFA compute?
	- After reading a symbol, the machine splits into multiple copies of itself and follows all the possibilities in parallel. Each copy of the machine takes one of the possible ways to proceed and continues as before.
	- If the next input symbol doesn’t appear on any of the arrows exiting the state occupied by a copy of the machine, that copy of the machine dies, along with the branch of the computation associated with it.
	- If any one of these copies of the machine is in an accept state at the end of the input, the NFA accepts the input string.
	- If a state with an ε symbol on an exiting arrow is encountered, something similar happens. Without reading any input, the machine splits into multiple copies, one following each of the exiting ε-labeled arrows and one staying at the current state.
- Another way to think of a nondeterministic computation is as a tree of possibilities.
	- The root of the tree corresponds to the start of the computation. 
	- Every branching point in the tree corresponds to a point in the computation at which the machine has multiple choices.
#### Formal Definition of a Non-Deterministic Finite Automaton
- A nondeterministic finite automaton is a 5-tuple $(Q, Σ, δ, q_0, F)$
	- $Q$ is a finite set called the states.
	- $Σ$ is a finite set called the alphabet.
	- $δ : Q × Σ_{\epsilon} → P(Q)$ is the transition function.
	- $q_0 ∈ Q$ is the start state.
	- $F ⊆ Q$ is the set of accept states.
- $P(Q)$ is called the power set of $Q$.
- For any alphabet $Σ$ we write $Σ_ε$ to be $Σ ∪ {ε}$.
- Formal Definitation of Computation
	- Let $N = (Q, Σ, δ, q_0, F)$ be a finite automaton and let $w = w_1w_2...w_m$ be a string where each $w_i$ is a member of the alphabet $Σ$.
		- Then M accepts $w$ if a sequence of states $r_0, r_1, . . . , r_m$ in $Q$ exists with three conditions:
		1. $r_0 = q_0$,: the machine starts in the start state.
		2. $r_{i+1} {\in}{\space}δ(r_i , w_{i+1}), for \space i = 0, . . . , n − 1$
		3. and $r_m ∈ F$: t 

