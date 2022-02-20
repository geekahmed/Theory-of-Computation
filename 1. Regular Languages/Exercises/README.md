# Chapter 1. Regular Language - Exercises and Problems
## Exercises
### Excercise No. 1
The following are the state diagrams of two DFAs, M1 and M2. Answer the following questions about each of these machines.
![enter image description here](https://github.com/geekahmed/Theory-of-Computation/blob/main/1.%20Regular%20Languages/Images/M1M2.png?raw=true)
a. What is the start state?

    For M1: q1
    For M2: q1

b. What is the set of accept states?

    For M1: q2
    For M2: q1, q4

c. What sequence of states does the machine go through on input aabb?

    For M1: q1 -> q2 -> q3 -> q1 -> q1
    For M2: q1 -> q1 -> q1 -> q2 -> q4

d. Does the machine accept the string aabb?

    For M1: No
    For M2: Yes

e. Does the machine accept the string ε?

    For M1: No
    For M2: Yes
### Excercise No. 2
Give the formal description of the machines M1 and M2 pictured in Exercise 1.1.
**For M1**
$Q = \{q_1, q_2, q_3\}$
$\Sigma = \{a, b\}$
$q_0  = q_1$
$F = \{q_2\}$
$\delta$ =
|   |  a | b  |
|---|---|---|
| $q_1$  |  $q_2$ | $q_1$  |
|  $q_2$ | $q_3$  |  $q_3$ |
|  $q_3$ |  $q_2$ |  $q_1$ |

**For M2**
$Q = \{q_1, q_2, q_3,q_4\}$
$\Sigma = \{a, b\}$
$q_0  = q_1$
$F = \{q_1, q_4\}$
$\delta$ =
|   |  a | b  |
|---|---|---|
| $q_1$  |  $q_1$ | $q_2$  |
|  $q_2$ | $q_3$  |  $q_4$ |
|  $q_3$ |  $q_2$ |  $q_1$ |
| $q_4$  |  $q_3$ | $q_4$  |
### Excercise No. 3
The formal description of a DFA M is ({q1, q2, q3, q4, q5}, {u, d}, δ, q3, {q3} ) , where δ is given by the following table. Give the state diagram of this machin
|   | u  | d  |
|---|---|---|
|  $q_1$ |   $q_1$ |  $q_2$  |
|   $q_2$ |   $q_1$ |  $q_3$  |
|  $q_3$ |   $q_2$ |   $q_4$ |
|  $q_4$  |   $q_3$ |   $q_5$ |
|   $q_5$ |  $q_4$  |   $q_5$ |

![enter image description here](https://github.com/geekahmed/Theory-of-Computation/blob/main/1.%20Regular%20Languages/Images/Q3.png?raw=true)