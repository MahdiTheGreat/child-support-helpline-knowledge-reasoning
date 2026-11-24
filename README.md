# Child Support Helpline: AI & Knowledge Representation System

A knowledge-driven artificial intelligence and reasoning platform integrating semantic ontologies, natural language processing (NLP), Belief-Desire-Intention (BDI) agents, Answer Set Programming (ASP), and declarative Prolog deduction.

> Designed a system for the World Childhood Foundation (WCF) using ontologies and NLP to identify non-serious support seekers by modeling user profiles with sentiment analysis and real-time scoring to prioritize genuine cases.

---

## Engineering & Reasoning Pillars

```
                         Child Support Helpline Platform
                                        │
    ┌───────────────────────────────────┼───────────────────────────────────┐
    ▼                                   ▼                                   ▼
Support Seeker Triage            Formal Argumentation            Deductive Knowledge Bases
& BDI Agent System              & Logic Programming (ASP)        & Relational Prolog
• OWL / RDF Ontologies          • Dung's Argumentation Semantics • First-Order Logic Deduction
• Transformers Sentiment NLP    • Conflict-Free & Admissible Sets• Acyclic Graph Traversal
• Real-Time Risk Profiling      • Stable & Preferred Extensions  • Term Evaluation
• Multi-Agent Dialogue Sim      • ASP (Clingo) vs. CSP Benchmarks• Mondial Relational Queries
```

---

### 1. Conversational Triage & Crisis Prioritization Platform ([`ChildSupportHelpLine`](projects/ChildSupportHelpLine/))
Developed for the **World Childhood Foundation (WCF)** to safeguard counselor bandwidth and accelerate genuine crisis interventions:
* **User Profiling & Dynamic Scoring:** Extracts sentiment trajectories, message frequency, and behavioral patterns using pre-trained Transformer sentiment pipelines and non-ableist lexical filters to calculate real-time troll vs. genuine seeker scores.
* **Semantic Ontologies:** Formalizes support seeker categories, interaction contexts, and risk factors in OWL/RDF using `owlready2` description logic inference.
* **BDI Agent Architecture:** Models autonomous decision agents with customizable commitment strategies (`blind`, `singleMinded`, `openMinded`) to balance immediate crisis escalation against non-serious user deprioritization.
* **Conversational Dialogue Simulator:** Simulates multi-agent interactions across conversation tree structures to evaluate triage accuracy and throughput.

---

### 2. Formal Argumentation & Answer Set Programming ([`ArgumentationSemanticsWithAsp`](projects/ArgumentationSemanticsWithAsp/))
Implements formal dispute and logical conflict resolution over directed Argumentation Frameworks ($AF = \langle AR, \text{attacks} \rangle$):
* **Declarative ASP Implementations:** Encodes Dung's classic argumentation semantics in Clingo syntax:
  * Conflict-Free Sets (`Conflict-free.pl`)
  * Admissible Sets (`Admissible.pl`)
  * Stable Extensions (`Stable.pl`)
  * Preferred Extensions (`Preferred.pl`)
* **ASP vs. CSP Empirical Evaluation:** Benchmarks Clingo Answer Set Programming against an imperative Constraint Satisfaction Problem (CSP) solver on dense random argumentation graphs ($p = 0.95$), highlighting how CDCL grounder optimizations minimize latency on combinatorial graph instances.

---

### 3. Declarative Logic Programming & Relational Deduction ([`PrologExercises`](projects/PrologExercises/))
Deductive knowledge representation and query resolution in Prolog under first-order Horn clause logic:
* **Relational Kinship Deduction (`genealogy_deduction.pl`):** Axiomatic modeling of family trees, gender predicates, and genealogical relations.
* **List Processing & Set Operations (`list_processing_sets.pl`):** Relational set intersection, member unification, and permutation generation.
* **Acyclic Graph Traversal (`acyclic_graph_traversal.pl`):** Cycle-safe pathfinding and reachability verification across directed networks.
* **Symbolic Term Evaluation & Geographic Knowledge Bases (`term_evaluation_mondial.pl`, `mondial.pl`):** Recursive algebraic expression evaluation and multi-hop deductive queries over the relational Mondial geographic database.

---

## Directory Structure

```text
child-support-helpline/
├── README.md
├── .gitignore
└── projects/
    ├── ChildSupportHelpLine/
    │   ├── README.md
    │   ├── BdiAgent.py
    │   ├── UserModelling.py
    │   ├── Simulator.py
    │   ├── Conversation.py
    │   ├── MessageTree.py
    │   ├── ChildSupportHelplineOntology.rdf
    │   └── ChildSupportHelplineOntologyWithIndividuals.rdf
    ├── ArgumentationSemanticsWithAsp/
    │   ├── README.md
    │   ├── Admissible.pl
    │   ├── Conflict-free.pl
    │   ├── Preferred.pl
    │   ├── Stable.pl
    │   └── AspVsCsp.py
    └── PrologExercises/
        ├── README.md
        ├── genealogy_deduction.pl
        ├── list_processing_sets.pl
        ├── acyclic_graph_traversal.pl
        ├── term_evaluation_mondial.pl
        └── mondial.pl
```

---

## Technology Stack

* **Programming & Logic Languages:** Python 3, Prolog, Answer Set Programming (Clingo).
* **Semantic Web & Knowledge Engineering:** OWL, RDF, XML, Owlready2, Protégé.
* **Natural Language Processing:** Hugging Face Transformers, PyTorch, Lexical Sentiment Analysis.
* **Agent Frameworks:** Belief-Desire-Intention (BDI) Agent Architecture.
* **Solvers & Tooling:** Clingo / Potassco, SWI-Prolog, CSP Backtracking Solvers.
