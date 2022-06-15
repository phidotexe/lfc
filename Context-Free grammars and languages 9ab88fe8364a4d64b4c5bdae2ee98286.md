# Context-Free grammars and languages

## Context-free Grammar

$G$ is a context-free grammar defined as 
$G = (V, \Sigma,S,P)$ where:

- V = Set of non terminals + $\epsilon$
- $\Sigma$  = Set of terminals
- $S$ = Start symbol
- $P$ = Production rules

<aside>
❓ $G = \{(S,A), (a,b), S, (S \to aAb, A\to aAb \mid \epsilon) \}$generates strings of form $a^nb^n$  ($aaabbb$)

</aside>

### Derivation tree

A derivation tree can be constructed following the derivations. A **canonical derivation tree** is composed following the same *rule* (the leftmost or rightmost non terminal) about which non terminal to derive next, at each level of the tree.  

![Untitled%2010.png](Untitled%2010.png)

**Ambiguity**

A grammar G is ambiguous if there exist a word $w \in L(G)$  which can be generated by two distinct canonical tree

![Untitled%2011.png](Untitled%2011.png)

---

### Properties of context-free languages

**Closure:** 

A set is closed under an operation if for each performance of that operation on members of the set always produces a member of the set. 
For example: the set of positive integers is closed under the addition operation.

**Closure properties ([proof](https://didatticaonline.unitn.it/dol/pluginfile.php/1110913/mod_resource/content/1/L-03_2.pdf))**

Valid: Union
Valid: Concatenation

Not valid: Intersection

### Simplification of context-free grammars (CFG cleanup)

Let $L$ be a context-free language. Then  $\exist$  a context-free grammar  $G$    such that $L(G)=L\setminus\{\epsilon\}$ 
and has:

1. No $\epsilon$ -production (i.e. no production in the shape $A\to\epsilon$)
2. No unit-production (i.e. no production in the shape $A\to B$)
3. No useless non-terminals (i.e. non-terminals that can't be reached with or without production rules)

---

### Chomsky Normal Form

Elements of the right side of the production are either one terminal or two non-terminals

$A \to a$ 

$A \to BC$

**Steps**

1. Apply simplification above (CFG cleanup)
2. Replace each production like $A \to BBB$   into $A\to BC, C \to BB$ 
3. Replace each production like $A\to aB$  into $A\to CB, C\to a$

### Pumping lemma ([proof](https://didatticaonline.unitn.it/dol/pluginfile.php/1130929/mod_resource/content/1/L-04.pdf))

If $L$ is a context-free language, then:

- $\exist p>0$  "Pumping lenght", such that $\forall z \in L, |z|>p$
- $\exist u,v,w,x,y$ such that (**PL-THESIS**)
    - $z = uvwxy$
    - $|vwx|\leq p$
    - $|vx|>0$ ($v$ e $x$  non simultaneamente nulle)
    - $\forall i>0, \nobreakspace uv^iwx^iy \in L$

<aside>
💡 We can prove that a language is **not** context-free by disproving the last rule of the PL-THESIS (it's a necessary but not sufficient condition)

</aside>

---