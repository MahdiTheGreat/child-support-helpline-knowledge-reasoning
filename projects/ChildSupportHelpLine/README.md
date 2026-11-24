# Child Support Helpline: AI & Knowledge-Driven Triage System

An intelligent support seeker verification and conversational triage platform designed for the **World Childhood Foundation (WCF)**. The system utilizes formal OWL/RDF ontologies, natural language processing (NLP), and Belief-Desire-Intention (BDI) agent architectures to identify non-serious support seekers by modeling user profiles with sentiment analysis and real-time scoring to prioritize genuine cases.

---

## Architecture Overview

```
  Incoming Support Message
             │
             ▼
  ┌───────────────────────┐
  │  NLP & Sentiment      │ ──► Transformers Sentiment Pipeline & Lexical Scoring
  │  Analysis Pipeline    │
  └──────────┬────────────┘
             │
             ▼
  ┌───────────────────────┐
  │  User Profiling &     │ ──► Dynamic Metric Weighting & Real-Time Scoring
  │  Risk Scoring         │
  └──────────┬────────────┘
             │
             ▼
  ┌───────────────────────┐
  │  OWL/RDF Ontology     │ ──► Owlready2 Semantic Inference & Concept Classification
  │  Knowledge Engine     │
  └──────────┬────────────┘
             │
             ▼
  ┌───────────────────────┐
  │  BDI Decision Agent   │ ──► Prioritized Triage: Genuine Case Escalation vs. Non-Serious Filtering
  └───────────────────────┘
```

---

## Core System Components

### 1. NLP Sentiment & Content Analysis (`UserModelling.py`)
* **Transformer Sentiment Pipeline:** Evaluates conversational turn sentiment polarity and emotional valence using pre-trained Transformer models (`transformers.pipeline("sentiment-analysis")`).
* **Non-Ableist Lexical Filtering:** Implements profanity and hostility detection using non-ableist screening filters to ensure neurodiverse and distressed support seekers are not penalized.
* **Real-Time Seeker Scoring:** Continuously updates dynamic user profile scores based on sentiment trajectories, message repetition patterns, lexical cues, and dialogue progression to distinguish between authentic crises and trolling behaviors.

### 2. Semantic Knowledge Base & Ontologies (`ChildSupportHelplineOntology.rdf`)
* **Domain Modeling in OWL / RDF:** Formally encodes concepts including `User`, `SupportSeeker`, `GenuineUser`, `Troll`, `Message`, and `InteractionContext`.
* **Description Logic Reasoning:** Leverages `owlready2` to infer implicit user classifications from observed conversational assertions and dynamic behavioral traits.

### 3. Belief-Desire-Intention (BDI) Agent (`BdiAgent.py`)
* **Belief Base:** Dynamically populated by ontology assertions and real-time sentiment classifications.
* **Desires & Intentions:** Maintains prioritized goals including fast-track escalation of acute crisis cases to human counselors, interactive clarification for ambiguous interactions, and passive deprioritization of non-serious queries.
* **Commitment Strategies:** Supports multiple BDI commitment modes:
  * `blind`: Relentlessly pursues current triage goals until completion.
  * `singleMinded`: Maintains intentions until satisfied or deemed impossible.
  * `openMinded`: Continuously revises intentions in response to shifting incoming sentiment.

### 4. Conversational Dialogue Simulator (`Simulator.py`, `MessageTree.py`, `Conversation.py`)
* **Dialogue Tree Architecture:** Manages multi-turn conversation states and branch trajectories.
* **Agent-Based Simulation:** Benchmarks triage agent accuracy against diverse synthetic user profiles, evaluating classification precision, false-positive mitigation, and latency under high concurrent load.

---

## Technical Stack

* **Programming Language:** Python 3
* **Knowledge Engineering:** OWL, RDF, XML, Owlready2
* **NLP & Language Models:** Hugging Face Transformers, PyTorch
* **Agent Architecture:** Belief-Desire-Intention (BDI) Model
* **Project Presentation:** [Google Slides Overview](https://docs.google.com/presentation/d/1QW0NSJpARDNq2sTbprBaNJ0HrmLDV1auoYlFi1iQzoU/edit#slide=id.p)
