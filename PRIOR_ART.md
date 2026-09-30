# Prior Art and Adjacent Architectures

BECA is a conceptual architecture. This document identifies nearby ideas so that novelty claims can be made carefully and tested rather than asserted.

The purpose is not to claim that every component is new. The relevant question is whether the **combination of local mutable cognition, explicit stabilization, immutable cross-boundary commit, and source-aware second-stage integration** produces a distinct and useful architecture.

## 1. Federated Learning

Canonical federated learning keeps training data on clients while clients compute local model updates and a server aggregates those updates into a shared model.

Representative references:

- McMahan et al., *Communication-Efficient Learning of Deep Networks from Decentralized Data* (AISTATS 2017): https://research.google/pubs/communication-efficient-learning-of-deep-networks-from-decentralized-data/
- Konečný et al., *Federated Learning: Strategies for Improving Communication Efficiency* (2016): https://research.google/pubs/federated-learning-strategies-for-improving-communication-efficiency/

### Similarity

- common initialization/shared model;
- local computation on separate clients;
- local results are transmitted upward;
- higher layer aggregates information from multiple sources.

### Difference to investigate

Federated learning usually treats client updates as optimization contributions and aggregates them iteratively. The local update does not have to represent a semantically complete or stabilized conclusion.

BECA instead proposes a stronger information-lifecycle boundary:

```text
federated-style loop:
local update -> aggregate -> redistribute -> local update -> ...

BECA knowledge loop:
local mutable evolution -> stabilization -> immutable commit
                         -> source-aware second-stage integration
```

BECA therefore asks whether some forms of learned knowledge should be withheld from global fusion until the local source has completed an explicit stabilization cycle.

This distinction needs experimental validation. It should not be presented as automatically superior to federated optimization.

## 2. Blackboard systems

Classical blackboard systems use a shared workspace that multiple specialized knowledge sources read and update while collaboratively solving a problem.

Background:

- Blackboard system overview and classic Hearsay-II references: https://en.wikipedia.org/wiki/Blackboard_system
- Historical discussion of transactional blackboards: https://www.sciencedirect.com/science/article/pii/0954181086900518

### Similarity

- multiple independent or specialized sources contribute to a higher-level solution;
- integration occurs across heterogeneous sources;
- source coordination and shared knowledge are explicit architectural concerns.

### Difference to investigate

Blackboard systems are centered on a shared evolving workspace. Partial solutions and hypotheses may be posted to that shared state and then influence other knowledge sources.

BECA's central rule is almost the opposite for learned knowledge:

> unfinished local cognitive state remains behind the agent boundary; the shared integration layer receives only stabilized commits.

The blackboard is therefore closer to a continuously shared workspace, whereas BECA proposes a transaction-like boundary between local cognition and shared knowledge.

## 3. Transactional blackboards

Transactional extensions to blackboard systems were proposed to coordinate concurrent knowledge sources and synchronize shared-data access.

Reference:

- *Transactional blackboards*, Artificial Intelligence in Engineering 1(2), 1986: https://www.sciencedirect.com/science/article/pii/0954181086900518

### Similarity

- explicit transaction concepts;
- concern about concurrent updates and synchronization;
- structured access to shared knowledge.

### Important distinction

A transaction mechanism can protect concurrent shared-state writes without imposing BECA's semantic rule that the **knowledge itself must first mature inside a separate local cognitive boundary**.

A strong prior-art review should examine transactional blackboard literature in detail before making formal novelty claims.

## 4. Event Sourcing

Event sourcing stores state changes as immutable events in an append-only history. Current state can be reconstructed from those events.

References:

- Microsoft Azure Architecture Center: https://learn.microsoft.com/en-us/azure/architecture/patterns/event-sourcing
- Martin Fowler, *Event Sourcing*: https://martinfowler.com/eaaDev/EventSourcing.html

### Similarity

- immutable records;
- version/provenance history;
- later changes are represented by new records rather than in-place mutation.

### Difference

Event sourcing normally preserves **every relevant state-changing event** because the event history itself is the source of truth.

BECA does not require the global layer to preserve or consume every internal cognitive mutation. The local dynamic trajectory may remain private/local; only stabilized commits need cross the knowledge boundary.

In shorthand:

```text
event sourcing:
change1 -> event1
change2 -> event2
change3 -> event3
all retained globally

BECA:
V1 -> V2 -> V3 -> V4   (local mutable process)
                  |
                  +-> Final Commit (cross-boundary)
```

## 5. Actor model / message-passing systems

Actor-style architectures isolate local state and communicate through messages. This is conceptually adjacent to BECA's agent boundary.

### Similarity

- local state ownership;
- explicit boundaries;
- message-based cross-boundary interaction.

### Difference

Actor isolation alone does not define which messages are provisional cognitive state versus stable learned knowledge. BECA adds a semantic lifecycle and integration policy for knowledge-producing agents.

A deeper literature review is still required here.

## 6. Multi-agent debate and shared-memory LLM systems

Modern LLM multi-agent systems often let agents inspect one another's hypotheses, critiques, intermediate reasoning summaries, or a shared scratchpad.

### Potential BECA contrast

BECA predicts that, for some tasks, early visibility of provisional hypotheses may create anchoring, correlated error, or premature consensus. It therefore proposes an experimental condition in which agents remain epistemically independent until local commit.

This is one of the clearest near-term empirical tests of the architecture.

## 7. What may be distinctive about BECA

The potentially distinctive contribution is not any one item below in isolation, but the combined rule set:

1. **agent as cognitive transaction boundary**;
2. **mutable information allowed internally**;
3. **unfinished learned state prevented from becoming shared learned knowledge**;
4. **explicit local stabilization before commit**;
5. **commit immutable and versioned**;
6. **multiple committed sources kept distinguishable during integration**;
7. **higher layer performs second-stage synthesis rather than replaying all local cognitive history**;
8. **later corrections supersede previous stable commits instead of mutating their history**.

## 8. Novelty status

Current status: **unverified architectural originality**.

It is reasonable to say that BECA combines familiar ideas in a specific way and defines a concrete research hypothesis. It is not yet reasonable to claim that no equivalent architecture exists in the literature.

Before any formal novelty claim or academic submission, the review should be expanded across:

- distributed artificial intelligence;
- blackboard systems;
- transactional knowledge bases;
- actor systems;
- federated learning and federated analytics;
- multi-agent reinforcement learning;
- consensus and belief-fusion systems;
- epistemic logic / opinion dynamics;
- multi-agent LLM debate and shared-memory architectures;
- database isolation and commit semantics applied to AI knowledge systems.

## 9. Prior-art question to keep asking

The strongest comparison question is:

> Has an existing architecture already defined agents as locally mutable cognitive domains whose learned knowledge becomes globally eligible only after a semantic stabilization/commit step, followed by source-preserving second-stage integration?

If yes, BECA should cite and build on it. If no, that combination is the candidate contribution to test.
