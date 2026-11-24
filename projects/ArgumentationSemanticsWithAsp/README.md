# Abstract Argumentation Semantics via Answer Set Programming (ASP)

A declarative logic programming framework implementing **Dung's Abstract Argumentation Semantics** using Answer Set Programming (ASP) in **Clingo**, alongside comparative empirical benchmarking against Constraint Satisfaction Problem (CSP) solvers.

---

## Theoretical Foundations

An Abstract Argumentation Framework (AF) is formalized as a directed graph pair:

$$AF := \langle AR, \text{attacks} \rangle$$

where $AR$ is a finite set of arguments and $\text{attacks} \subseteq AR \times AR$ is a binary attack relation between arguments.

```
       [ Argument A ] ───( attacks )───► [ Argument B ]
             ▲                                 │
             │                                 │
         ( defends )                       ( attacks )
             │                                 │
             │                                 ▼
       [ Argument C ] ◄───( attacks )─── [ Argument D ]
```

### Argumentation Semantics
* **Conflict-Free Sets:** A set $S \subseteq AR$ is conflict-free if $\forall a, b \in S$, $(a, b) \notin \text{attacks}$.
* **Admissible Sets:** A conflict-free set $S$ is admissible if it defends all its members: $\forall a \in S$, if $\exists b \in AR$ such that $(b, a) \in \text{attacks}$, then $\exists c \in S$ such that $(c, b) \in \text{attacks}$.
* **Stable Extensions:** An admissible set $S$ is a stable extension if $S$ attacks every argument outside $S$: $\forall b \notin S, \exists a \in S \text{ such that } (a, b) \in \text{attacks}$.
* **Preferred Extensions:** A set $S$ is a preferred extension if it is a maximal (with respect to set inclusion) admissible set of $AF$.

---

## ASP Declarative Programs

Implemented in declarative Clingo syntax using choice rules, integrity constraints, and deductive safety conditions:

1. **Conflict-Free Sets (`Conflict-free.pl`):** Generates candidate argument subsets and constrains them against active attacks within the selection.
2. **Admissible Sets (`Admissible.pl`):** Enforces defense requirements, eliminating conflict-free subsets containing undefended arguments.
3. **Stable Extensions (`Stable.pl`):** Verifies that all arguments outside the candidate set receive at least one incoming attack from a selected argument.
4. **Preferred Extensions (`Preferred.pl`):** Computes maximal admissible sets via saturation techniques or optimization directives.

### Predicate Schema
* Inputs: `arg/1` (arguments), `att/2` (attack edges).
* Outputs: `selected_arg/1` (arguments belonging to the computed extension).

---

## ASP vs. CSP Empirical Evaluation (`AspVsCsp.py`)

A comparative benchmark measuring solving runtime between Clingo ASP and an imperative Constraint Satisfaction Problem (CSP) solver on dense random argumentation graphs ($p = 0.95$, $N \in \{1, 5, 10, 20, 50\}$):

### Key Observations
* **Low-to-Medium Densities ($N \le 10$):** ASP and CSP exhibit comparable sub-second runtimes.
* **Complex Topologies ($N = 20$):** ASP demonstrates superior execution speed over CSP due to efficient unit propagation, nogood learning, and CDCL (Conflict-Driven Clause Learning) grounder optimizations.
* **Memory & Scalability Trade-offs:** ASP grounds combinatorial problem representations into memory before solving, which yields rapid query responses on moderate graphs but increases peak RAM utilization on extremely large instances ($N \ge 50$), whereas CSP maintains minimal memory footprints through backtracking search.
