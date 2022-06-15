# Subset construction algorithm

Given a non-deterministic state machine:

${\it NFA} = \{Q_N,\Sigma, \delta_N, q_0, F_N\}$

we can determinate an deterministic equivalent :

${\it DFA}= \{Q_D, \Sigma, \delta_N, \{q_0\}, F_D \}$

Where:

 - $Q:$ States of the automatas

 - $F :$ Final states of the automatas

such that: 

$L({\it DFA})=L({\it DFA})$   → The languages are equivalent

- The number of states of the DFA is $2^{\it \# states\space of\space the\space NFA}$
    
    $Q_D = \mathcal P(Q_N) \rArr |Q_D|=2^{|Q_N|}$  
    
- The set of final states is:
    
    $F_D = \{ s \in Q_D |s\space \cap F_N \ne \empty \}$ 
    
- The new transition function is
    
    $\delta_D(s,a) = \bigcup_{p \in s} \delta_N(p,a), \forall s \in Q_D$
    

The algorithm is determined by the definition of the automata