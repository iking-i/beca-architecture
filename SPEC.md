# BECA Specification v0.2

This document defines the minimum concepts and invariants required for a system to meaningfully claim compatibility with **Bounded Evolutionary Commit Architecture (BECA)**.

## 1. Terminology

### 1.1 Parent system
A shared or higher-level system that provides common initialization and later learns from multiple agents.

### 1.2 Common initial worldview
The baseline state inherited by agents before their local trajectories diverge. It may include shared rules, ontology, prior knowledge, protocols, and a common model of the world.

BECA assumes that agents are meaningfully comparable because they originate from the same or mutually compatible baseline.

### 1.3 Shared world
The larger environment within which multiple agents exist. Agents may occupy different local regions, receive different events, or experience different histories while still operating inside one coherent world model.

### 1.4 Agent boundary
A logical boundary inside which information may remain mutable, provisional, contradictory, incomplete, or under active revision.

The boundary protects **local state ownership and mutability**. It is not a prohibition on communication.

### 1.5 Dynamic local state
Any representation inside an agent that is still allowed to change as a consequence of observation, peer communication, contradiction, reinterpretation, local learning, or model revision.

### 1.6 Peer communication
Messages exchanged between agents during local evolution. These messages may contain observations, questions, hypotheses, warnings, or provisional interpretations.

Peer communication becomes input to the receiving agent's local dynamic state. It does not automatically become authoritative parent-level knowledge.

### 1.7 Stabilized conclusion
A locally produced result that the agent currently considers complete enough to expose as a source contribution to higher-level integration.

A stabilized conclusion does not mean metaphysical certainty. It means the local processing cycle has reached an explicit commit condition.

### 1.8 Commit
A versioned, immutable publication of a stabilized conclusion and associated metadata from one source agent to the higher-level integration process.

### 1.9 Integration layer
The higher-level process that consumes committed outputs from multiple agents and performs cross-source operations such as validation, comparison, deduplication, conflict resolution, abstraction, and generalization.

### 1.10 Useful delta
The novel, transferable change produced by an agent relative to the common initialization or previously shared knowledge.

## 2. Core invariants

### BECA-I1 — Shared origin, divergent local histories
Agents participating in the same BECA population SHOULD begin from the same or mutually compatible initial worldview, while being allowed to experience different local regions, events, and histories in the shared world.

### BECA-I2 — Mutable local state remains locally owned
Dynamic cognitive state MUST NOT be treated as authoritative shared knowledge before commit.

An agent MAY communicate such state to peers, but the receiving peer treats it as input to its own local evolution rather than as an automatic parent-level truth update.

### BECA-I3 — Communication is permitted
BECA MUST NOT be interpreted as requiring communication isolation.

Agents MAY exchange observations, provisional beliefs, requests, critiques, warnings, and coordination messages during their evolution.

### BECA-I4 — Peer communication and parent-level knowledge integration are distinct
A peer message MAY influence another agent immediately.

A peer message MUST NOT, merely by being transmitted, count as a finalized contribution to the parent/shared knowledge base.

### BECA-I5 — Cross-boundary learned knowledge must be versioned
Every committed conclusion MUST have an identity or version that allows downstream systems to determine which committed state they are integrating.

### BECA-I6 — A commit is immutable
Once published, a commit MUST NOT be modified in place.

If an agent later changes its conclusion, it MUST publish a new commit that explicitly supersedes, refines, or contradicts the previous commit.

### BECA-I7 — Integration consumes commits, not hidden mutable state
The integration layer SHOULD operate on committed results and their evidence/metadata, rather than on the agent's complete mutable internal process.

### BECA-I8 — Local evolution precedes higher-level fusion
An agent MUST have an opportunity to revise its local state—including revision caused by peer interaction—before its output becomes eligible for shared knowledge integration.

### BECA-I9 — Multiple sources remain distinguishable during integration
The integration layer MUST preserve source identity at least until conflict analysis and provenance-sensitive processing are complete.

Prematurely flattening several independent commits into one undifferentiated state defeats the purpose of multi-source evolution.

## 3. Local lifecycle

A minimal BECA agent lifecycle is:

```text
INITIALIZE FROM COMMON WORLDVIEW
    |
    v
ENTER LOCAL REGION / RECEIVE LOCAL HISTORY
    |
    v
OBSERVE / COMMUNICATE / RECEIVE PEER INPUT
    |
    v
LOCAL DYNAMIC PROCESSING
    |
    +--> revise
    +--> reject
    +--> relate
    +--> compress
    +--> test
    +--> incorporate or reject peer messages
    |
    v
STABILIZATION CHECK
    |
    +-- not stable --> return to local processing
    |
    +-- stable ------> COMMIT
                          |
                          v
                       IMMUTABLE
```

The architecture intentionally does not prescribe a universal stabilization rule. Stability may be defined by confidence, convergence, contradiction rate, explicit task completion, repeated consistency checks, bounded deliberation, human approval, or a domain-specific criterion.

## 4. World positioning

BECA gains meaning from **same origin + different situated experience**.

A population may be represented as:

```text
M0 = common initial worldview

Agent A = M0 + local history HA
Agent B = M0 + local history HB
Agent C = M0 + local history HC
```

where `HA`, `HB`, and `HC` arise from different positions, events, relationships, or perspectives within one shared world.

The useful result of the system is not simple duplication of `M0`, but the differentiated knowledge produced by these divergent trajectories.

## 5. Communication semantics

BECA recognizes at least three information flows.

### 5.1 Environment input
Observations originating from the world.

### 5.2 Peer communication
Messages exchanged among agents during evolution.

Examples:

- observations;
- warnings;
- hypotheses;
- questions;
- partial interpretations;
- requests for verification;
- coordination signals.

These messages can change the receiver's local state.

### 5.3 Knowledge commit
A stabilized source contribution submitted for higher-level integration.

The architectural distinction is therefore:

```text
peer message -> local input -> local change

commit -> higher-level source input -> cross-source integration
```

## 6. Commit envelope

A recommended commit contains:

```text
Commit {
  commit_id
  source_agent_id
  base_worldview_version
  local_cycle_id
  local_scope
  conclusion
  evidence_summary
  confidence
  assumptions
  known_limitations
  peer_influences[]
  supersedes[]
  contradicts[]
  created_at
}
```

Only `conclusion` is conceptually mandatory. The additional fields are recommended because second-stage integration is difficult without provenance, scope, and context.

## 7. Second-stage integration

The integration layer receives stable, source-separated commits:

```text
Commit A_final
Commit B_final
Commit C_final
        |
        v
source comparison
        |
conflict detection
        |
scope analysis
        |
evidence weighting
        |
deduplication
        |
abstraction / generalization
        |
shared update candidate
```

The integration layer SHOULD NOT blindly average all commits. A BECA-compatible integrator may reject, quarantine, defer, merge, generalize, or supersede commits.

## 8. Stable does not mean permanent

A committed conclusion is immutable as a historical source result, but later knowledge may supersede it.

Example:

```text
A.Commit.12 = "X causes Y under condition C"

Later local evolution produces:

A.Commit.19 = "X causes Y only when C and D hold"
              supersedes A.Commit.12
```

The earlier commit remains part of provenance history, while the later commit can replace it in active shared knowledge after integration.

## 9. What BECA does and does not isolate

BECA isolates **authority and mutability**, not necessarily communication.

It does not require:

- social isolation;
- silent agents;
- independent universes;
- absence of collaboration;
- absence of provisional discussion.

It does require that a changing local state not become authoritative parent-level knowledge merely because it was communicated.

## 10. Minimal conformance

A system is minimally BECA-like if all of the following hold:

1. agents share the same or a compatible initial worldview;
2. agents experience different local histories within a coherent shared world;
3. agents may communicate during local evolution;
4. mutable local state remains owned by the local agent;
5. peer messages become local input rather than automatic parent-level truth;
6. agents publish explicit stabilized commits;
7. commits are immutable/versioned;
8. a higher layer integrates multiple commits while preserving source provenance during integration.
