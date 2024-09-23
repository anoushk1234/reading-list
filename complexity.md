# Computational Complexity

## Primer
> First, consider a Turing machine as a model (you can use other models too as long as they are Turing equivalent) of the algorithm at hand.
When you provide an input of size 𝑛, then you can think of the computation as a sequence of the machine's configuration after each step, i.e., 𝑐0,𝑐1,… .
Hopefully, the computation is finite, so there is some 𝑡 such 𝑐0,𝑐1,…,𝑐𝑡. Then 𝑡 is the running time of the given algorithm for an input of size 𝑛.

> An algorithm is polynomial (has polynomial running time) if for some 𝑘,𝐶>0
, its running time on inputs of size 𝑛 is at most 𝐶𝑛𝑘. Equivalently, an algorithm is polynomial if for some 𝑘>0, its running time on inputs of size 𝑛 is 𝑂(𝑛𝑘)

> This includes linear, quadratic, cubic and more. On the other hand, algorithms with exponential running times are not polynomial.

> There are things in between - for example, the best known algorithm for factoring runs in time 𝑂(exp(𝐶𝑛1/3log2/3𝑛))
for some constant 𝐶>0; such a running time is known as sub-exponential. Other algorithms could run in time 𝑂(exp(𝐴log𝐶𝑛)) for some 𝐴>0 and 𝐶>1, and these are known as quasi-polynomial. Such an algorithm has very recently been claimed for discrete log over small characteristics.

## Classes
1) P
   - Problems that can be solved in polynomial time by deterministic machine
   - Are easy to solve, true or false kind of problems
   - Are tractable, easy to solve in theory and in practice
   - Ex: GCD
  
2) NP
   - Problems that can be solved by a non deterministic machine
   - hard to solve but easy to verify
   - Can ve verified by turing machine in polynomial time
   - Ex: Chess, Graph Coloring
  
3) Co-NP
   - "no" answers to the problem can be verified using a proof in polynomial time.
   - if a problem lies in NP then its complement(yes and no swapped) also lies in Co-NP.

4) NP-hard
   - atleast as hard as NP and every NP problem reduces to NP-hard
   - but not every NP-hard problem is NP
   - Takes a long time to verify solution
   - Solving it in poly time would allows us to solve all np problems in poly time
   - Ex: Halting Problem
  
5) NP-complete
   - if problem is both np and np-hard
   - A: if soln can be verified in poly time
   - B: if every problem in np can be reduced to this problem in poly time
   - Ex: vertex cover

Refs: https://www.cs.cornell.edu/courses/cs6820/2021fa/handouts/npcomp.pdf
