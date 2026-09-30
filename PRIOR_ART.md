# Prior Art and Adjacent Architectures

BECA is a conceptual architecture. This document identifies nearby ideas so that novelty claims can be made carefully and tested rather than asserted.

The purpose is not to claim that every component is new. The relevant question is whether the **combination of same-origin agents, situated local evolution, peer communication, local evolutionary closure, result-only transfer, and second-stage integration** produces a distinct and useful architecture.

## 1. Federated Learning

Canonical federated learning keeps training data on clients while clients compute local model updates and a server aggregates those updates into a shared model.

### Similarity

- common initialization/shared model;
- local computation on separate clients;
- local results are transmitted upward;
- a higher layer aggregates information from multiple sources.

### Difference to investigate

Federated learning usually treats client updates as optimization contributions and aggregates them iteratively. A local update does not necessarily represent the output of a completed local evolutionary process.

BECA instead proposes a lifecycle distinction:

```text
federated-style loop:
local update -> aggregate -> redistribute -> local update -> ...

BECA knowledge loop:
same initial state
-> situated local evolution + peer communication
-> local evolutionary closure
-> determinate result
-> second-stage integration
```

The difference is not that BECA agents are silent or isolated. They may communicate continuously. The proposed boundary concerns when local information becomes eligible for higher-level integration.

## 2. Blackboard systems

Classical blackboard systems use a shared workspace that multiple specialized knowledge sources read and update while collaboratively solving a problem.

### Similarity

- multiple local sources contribute to a higher-level result;
- shared information and coordination are explicit architectural concerns;
- partial information can influence multiple participants.

### Difference to investigate

Blackboard systems are centered on an evolving shared workspace. Partial solutions and hypotheses may themselves become part of that shared state.

BECA permits partial hypotheses to circulate between agents, but distinguishes that peer circulation from higher-level integration. A communicated provisional idea remains input to local evolution; the higher layer receives the result only after the relevant local process has ended.

## 3. Transactional blackboards

Transactional extensions to blackboard systems coordinate concurrent knowledge sources and synchronize shared-data access.

### Similarity

- explicit transaction concepts;
- concern about concurrent updates and synchronization;
- structured transitions between local and shared state.

### Important distinction

A transactional mechanism can protect shared writes without defining the semantic lifecycle BECA proposes.

BECA's candidate distinction is that the **local evolutionary process itself has a bounded lifetime**, and only its completed result enters second-stage integration.

## 4. Event Sourcing

Event sourcing stores state changes as immutable events in an append-only history.

### Similarity

- a completed record may be treated as fixed after publication;
- later change can be represented by later state rather than silent retroactive rewriting.

### Difference

Event sourcing normally preserves every relevant state-changing event because history itself is part of the source of truth.

BECA does not require the higher layer to preserve the local history at all. Intermediate changes may disappear with the local process. The upper layer needs the result produced when that process ends.

```text
event sourcing:
change1 -> event1
change2 -> event2
change3 -> event3
history retained globally

BECA:
V1 -> V2 -> V3 -> ... -> local closure
                         |
                         +-> determinate result
```

## 5. Actor model / message-passing systems

Actor-style architectures isolate local state and communicate through messages. This is conceptually adjacent to BECA's local-state boundary.

### Similarity

- local state ownership;
- explicit boundaries;
- message-based interaction.

### Difference

Actor isolation alone does not define the distinction between:

- information that is still part of an active local evolutionary process; and
- the completed result that should enter a higher-level synthesis process.

BECA adds that lifecycle distinction.

## 6. Multi-agent debate and shared-memory systems

Modern multi-agent systems often let agents inspect one another's hypotheses, critiques, intermediate summaries, or a shared scratchpad.

BECA is compatible with rich peer discussion. It does **not** require agents to remain epistemically independent until commit.

Its contrast is narrower:

> peer communication may alter local evolution, but communicated provisional information does not automatically become a completed input to the higher-level integration layer.

This means a BECA-like implementation could support constant discussion among agents while still separating ongoing local cognition from result-level integration.

## 7. Biological and generational analogy

BECA can also be described by analogy to finite biological lifecycles, although this analogy is not itself evidence for the architecture.

An organism does not need a single explicit "life task" in order for its local evolutionary history to end. A finite lifespan imposes a natural closure boundary. Over time, repeated experience may become redundant, existing structures may dominate new low-weight inputs, and development may increasingly stabilize.

BECA generalizes this into a systems principle:

> a local process can end because it has reached internal fixation or because a finite lifetime/resource boundary terminates it.

The upper layer can then integrate the result without requiring the local individual to continue existing or remain traceable.

## 8. What may be distinctive about BECA

The potentially distinctive contribution is not any one element in isolation, but the combined rule set:

1. multiple agents begin from the same initial state;
2. they occupy different local regions of one shared world;
3. they may communicate and influence one another during evolution;
4. each retains locally mutable state while its local process is active;
5. local evolution has an end condition, whether internal or externally imposed;
6. only the resulting determinate state enters higher-level integration;
7. the upper layer performs second-stage processing across those completed results;
8. source identity and provenance are optional implementation metadata rather than theoretical requirements;
9. the integrated result may become the common initial state of a later generation.

## 9. Novelty status

Current status: **unverified architectural originality**.

It is reasonable to say that BECA combines familiar ideas in a specific way and states a distinct information-lifecycle proposal. It is not yet reasonable to claim that no equivalent architecture exists in the literature.

Before any formal novelty claim, comparison should be expanded across:

- distributed artificial intelligence;
- blackboard systems;
- transactional knowledge bases;
- actor systems;
- federated learning and federated analytics;
- multi-agent reinforcement learning;
- consensus and belief-fusion systems;
- epistemic logic / opinion dynamics;
- multi-agent LLM debate and shared-memory architectures;
- database isolation and commit semantics applied to AI knowledge systems;
- evolutionary and generational learning architectures.

## 10. Prior-art question to keep asking

The strongest comparison question is:

> Has an existing architecture already defined one common initial state that is distributed into multiple agents, allows them to evolve and communicate in different local regions of one shared world, waits until each relevant local evolutionary process ends, then integrates only the resulting determinate outputs at a higher layer?

If yes, BECA should cite and build on it. If no, that combination is the candidate contribution.
