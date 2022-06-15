# LFC
Formal Languages and Compilers

**Useful links:**

- [javaTpoint](https://www.javatpoint.com/automata-tutorial)
- [KaTex support table](https://katex.org/docs/support_table.html)

## How does a Compiler work?

- **Lexical analysis:** identify and translate code lines into its components
- **Syntactic analysis:** verify the syntax of the code, creating the *parse tree* and the *abstract syntax tree*
- **Semantic analysis:** verify the absence of semantic errors (logical errors, not "grammar" ones)
- **Intermediate code generation:** conversion to Assembler language
- **Final code generation:** conversion to binary code

<aside>
⚙ We are gonna focus on the first two steps, defining how a machine can understand if some code written in its language L follows the rules of a grammar G

</aside>

---

### Grammars and Languages

[Grammars and languages](Grammars%20and%20languages%209848aeaf688f42e3891907fcf497330c.md) 

### Context-free Grammars and Languages

[Context-Free grammars and languages](Context-Free%20grammars%20and%20languages%209ab88fe8364a4d64b4c5bdae2ee98286.md) 

[Regular grammars and languages](Regular%20grammars%20and%20languages%20431a9ca95e4542478cc2127aae1744aa.md) 

---

# FSAs, DFAs, and NFAs

[Automatas](Automatas%2034abf3de0ed345178bfea4110ce42489.md) 

[NFA](NFA%207ebf251672cb404dbb0a3e50554c1f86.md) 

[Thompson's construction algorithm](Thompson's%20construction%20algorithm%209d74afa0da4d472c8380f3d1492d83bc.md) - Data una *reg. exp. $r$* costruisce l'NFA $N$ tale che :

$L(r)=L(N)$  ovvero hanno lo stesso linguaggio.

[Subset construction algorithm](Subset%20construction%20algorithm%20b0c5486b8ae14912b2ce3cac6fb9454c.md) - 

---

---

# End of notes taken on prof. Quaglia lessons

## Now let's go with God Ravula Ravindrababu

[Theory of Computation](Theory%20of%20Computation%20518fec38c3194836a173b6d0651ded3c.md) 

**Parsing 23/10/2020**

Given a grammar $G=(V,T,S,P)$ and a word $w$

Say whether $w \in L(G)$ and, if so, provide it's derivation tree

Two relevant kinds of parsing:

- Top-down —> leftmost derivation from root to yield
- Bottom-up —> rightmost derivation (in reverse order) from yield to root

**Top-down Parsing**

Let $w=bd$ and

$G: \space S \to Ad\space |\space Bd \\ \nobreakspace \nobreakspace \nobreakspace \nobreakspace \nobreakspace \nobreakspace \nobreakspace A \to a \\ \nobreakspace \nobreakspace \nobreakspace \nobreakspace \nobreakspace \nobreakspace \nobreakspace B \to b$

       `...`

**Predictive top-down parsing**

- no backtrack (completely deterministic)
- LL(1) grammars (LL=leftmost derivation)
    
    We construct a parsing table, we'll learn how to make it deterministic
    

**29/10/2020** 

[Theory of Computation](Theory%20of%20Computation%20518fec38c3194836a173b6d0651ded3c.md)