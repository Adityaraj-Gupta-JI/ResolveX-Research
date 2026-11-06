# Mathematical Foundations — v0.1

## PCP definition
Given a finite list of pairs `(u_i, v_i)` of finite words over an alphabet, determine whether there exists a **nonempty** finite index sequence `i_1 ... i_k` such that `u_i1 ... u_ik = v_i1 ... v_ik`.

A witness can be checked mechanically; general PCP is undecidable. No finite search bound alone establishes an arbitrary NO instance.

## Residual transition idea
For two accumulated words `U` and `V`, continue a branch only if one is a prefix of the other. Represent the unmatched suffix together with the side on which it occurs. Equal words have an empty residual; equality after at least one tile is a SAT witness. The precise canonical state representation and soundness lemma must be written before implementation.

## Necessary arithmetic constraints
For tile counts `c_i >= 0`, a solution requires `sum_i c_i (|u_i|-|v_i|)=0` and matching symbol counts. Failure of necessary constraints may prove impossibility; satisfying them is not sufficient because order matters.

## Termination semantics
For the first version, use a deterministic sequential while-language with unbounded mathematical integers, assignments, guards and conditionals. A ranking function into a well-founded order may establish termination when its conditions hold for all reachable transitions. A recurrent set or lasso with suitable proof obligations may establish nontermination. Results must quantify over the specified initial states.

## Soundness requirements
- State abstraction must preserve the claimed reachability property.
- Pruning must not discard any possible witness unless justified.
- Repeated partial search states are not a general PCP UNSAT proof.
- Numerical visualization and AI scores are not proof objects.

## Reading backlog
Add properly checked bibliographic references for Post's original PCP paper, formal-language theory, program termination, ranking functions, TLA+, TLC, and symbolic model checking before publication.
