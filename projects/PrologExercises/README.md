# Declarative Logic Programming & Deductive Knowledge Bases in Prolog

A collection of declarative logic programming modules implementing first-order relational deduction, list and set manipulation, acyclic graph pathfinding, recursive term evaluation, and complex deductive queries over relational geographic databases.

---

## Modules & Logic Systems

### 1. First-Order Relational Deduction (`genealogy_deduction.pl`)
* **Relational Modeling:** Encodes family lineages and kinship structures using first-order logic facts and Horn clauses.
* **Inference Rules:** Implements symmetric, transitive, and mutually exclusive relationship predicates (`child/2`, `parent/2`, `mother/2`, `father/2`, `partner/2`, `bachelor/1`).
* **Query Verification:** Validates deductive consistency and query resolution under the Closed-World Assumption (CWA).

### 2. Relational List Processing & Set Operations (`list_processing_sets.pl`)
* **Unification & Pattern Matching:** Tail-recursive list predicates implementing membership testing, head-tail decomposition, and accumulator-based processing.
* **Set Operations:** Implements relational set intersection (`same_member/3`), element extraction, list concatenation, and permutation generation.

### 3. Acyclic Graph Traversal & Cycle Detection (`acyclic_graph_traversal.pl`)
* **Path Generation:** Explores connectivity across directed graph topologies, identifying valid routes between arbitrary source and target nodes.
* **Cycle Prevention (`allways_acyclic/2`):** Tracks visited node histories to safely explore cyclic and acyclic graphs without entering infinite recursion.

### 4. Recursive Term Evaluation & Mondial Database Queries (`term_evaluation_mondial.pl`, `mondial.pl`)
* **Symbolic Arithmetic Evaluator (`eval/2`):** Recursively evaluates nested first-order algebraic term expressions (`plus/2`, `minus/2`, `times/2`) down to base constant integers.
* **Deductive Geospatial Queries:** Queries the extensive **Mondial geographic database** (`mondial.pl`) containing relational facts for countries, borders, rivers, and international organizations:
  * Multi-hop border adjacency inference.
  * Population and landmass threshold filtering.
  * Transnational boundary and regional alliance aggregations.
