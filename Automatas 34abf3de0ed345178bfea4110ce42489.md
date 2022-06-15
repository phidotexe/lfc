# Automatas

# FSAs, DFAs, and NFAs

A **Finite-State Automation** or Machine (FSA or FSM), also called *state machine* is an abstract machine that can be in exactly one of a finite number of state at any time.

A **Deterministic Finite Automation** is a FSA that accepts or rejects a given string of symbols by running through a state sequence uniquely determined from the string itself

A **Non-deterministic Finite Automation** is a FSA that does not need to obey the same rules as DFAs. In particular every DFA is also a NFA.
Using the [Subset construction algorithm](Subset%20construction%20algorithm%20b0c5486b8ae14912b2ce3cac6fb9454c.md)  each NFA can be *translated into an equivalent DFA*, meaning a DFA that recognizes the same formal language.
NFA only recognize regular languages, and a regular expression can be translated in an NFA using the [Thompson's construction algorithm](Thompson's%20construction%20algorithm%209d74afa0da4d472c8380f3d1492d83bc.md) 

## Non-deterministic Finite state Automation

![Untitled%2012.png](Untitled%2012.png)

is a NFA that breaks at least one of those properties:

- each of its transitions is uniquely determined by its source state and input symbol
- reading an input symbol is required for each state transitions

If it follows both rules it is a DFA. 

This means that NFA can have more than one possible transition between states *and that some strings may not lead to a final state*. 

Example:
This machine can accept the language:

$L((a|b)^*)abb$

It is an NFA since at $S_0$  can transit to either itself or $S_1$ with the same input $a$, randomly

![Untitled%2013.png](Untitled%2013.png)

### **Transition Diagram**

States are represented as circles, transitions are arrows between states, with the terminal of the production written above it.

The final state is the state that can accept the string gotten by the sequence of transitions. 

![Untitled%2014.png](Untitled%2014.png)

**Difference between NFA and DFA**

Exercise : DFA and NFA with $\Alpha = \{0,1\}$ accepts all strings starting with $1$

Solution : 

**DFA**

![Untitled%2015.png](Untitled%2015.png)

Initially in the state $q_0$, the machine turns in the final state $q_1$ when receiving input 1. Here accepts other 0 or 1 transitions to itself.

When receiving 0 as first input it goes to the state $q_2$ which is a dead end.

This diagram means that a string that gets accepted *has to* start with a 1. On $q_1$ we generate each possible substring allowed by the vocabulary. 

**NFA**

![Untitled%2016.png](Untitled%2016.png)

Initially on the state $q_0$, the machine turns in the final state $q_1$  when receiving input 1. From $q_1$ on each possible input it it changes the state to $q_1$

### Transition Table

The transition table is a tabular representation of the transition function. It takes two arguments (a state and a symbol) and return a state (the "next state")

Columns correspond to input symbol
Rows correspond to states
The first row correspond to the start state (can have also an arrow towards it)
The final states may be represented with a star next to them

**Example of a DFA from a transition diagram**

![Untitled%2017.png](Untitled%2017.png)

Solution:

![Untitled%2018.png](Untitled%2018.png)

In each row, we are saying which state the automata will turn into when receiving a specific input (in this example 0 or 1)

**Example of a NFA from a transition diagram**

![Untitled%2019.png](Untitled%2019.png)

Solution:

![Untitled%2020.png](Untitled%2020.png)

We can notice that this is a Non-deterministic automata since the state $q_1$ , on an input = 0 can either turn in state e $q_1$ or $q_2$

[Subset construction algorithm](https://www.notion.so/Subset-construction-algorithm-6132ec8739874373b21ccd8191e2bbd5) → NFA to DFA

[Thompson's construction algorithm](https://www.notion.so/Thompson-s-construction-algorithm-4f8be6d302d64433ae7b5a8423fbf569) → regexp to NFA

---