# BECA Specification v0.1

This document defines the minimum concepts and invariants required for a system to meaningfully claim compatibility with **Bounded Evolutionary Commit Architecture (BECA)**.

## 1. Terminology

### 1.1 Parent system
A shared or higher-level system that initializes, coordinates, or learns from multiple agents.

### 1.2 Agent boundary
A logical boundary inside which information may remain mutable, provisional, contradictory, incomplete, or under active revision.

The boundary exists to prevent unfinished local cognitive state from automatically becoming shared learned knowledge.

### 1.3 Dynamic state
Any local representation that is still allowed to change as a consequence of new evidence, contradiction, reinterpretation, local learning, or model revision.

### 1.4 Stabilized conclusion
A locally produced result that the agent currently considers complete enough to expose outside its boundary.

A stabilized conclusion does not mean metaphysical certainty. It means the local processing cycle has reached an explicit commit condition.

### 1.5 Commit
A versioned, immutable cross-boundary publication of a stabilized conclusion and its associated metadata.

### 1.6 Integration layer
The higher-level process that consumes committed outputs from multiple agents and performs cross-source operations such as validation, comparison, deduplication, conflict resolution, abstraction, and generalization.

### 1.7 Useful delta
The novel, transferable change produced by an agent relative to the shared initialization or previously shared knowledge.

## 2. Core invariants

### BECA-I1 — Mutable local state must remain locally scoped
Dynamic cognitive state MUST NOT be treated as authoritative shared knowledge before commit.

An implementation MAY transmit operational coordination messages while an agent is active, but such messages MUST be distinguished from committed learned knowledge.

### BECA-I2 — Cross-boundary learned knowledge must be versioned
Every committed conclusion MUST have an identity or version that allows downstream systems to determine which committed state they are integrating.

### BECA-I3 — A commit is immutable
Once published, a commit MUST NOT be modified in place.

If an agent later changes its conclusion, it MUST publish a new commit that explicitly supersedes, refines, or contradicts the previous commit.

### BECA-I4 — Integration consumes commits, not hidden mutable state
The integration layer SHOULD operate on committed results and their evidence/metadata, rather than on the agent's complete mutable internal process.

### BECA-I5 — Local evolution precedes global fusion
An agent MUST have an opportunity to perform local revision before its output becomes eligible for shared knowledge integration.

### BECA-I6 — Multiple sources remain distinguishable during integration
The integration layer MUST preserve source identity at least until conflict analysis and provenance-sensitive processing are complete.

Prematurely flattening several independent commits into one undifferentiated state defeats the purpose of independent information sources.

## 3. Local lifecycle

A minimal BECA agent lifecycle is:

```text
INITIALIZE
    |
    v
OBSERVE / RECEIVE INPUT
    |
    v
LOCAL DYNAMIC PROCESSING
    |
    +--> revise
    +--> reject
    +--> relate
    +--> compress
    +--> test
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

The architecture intentionally does not prescribe a universal stabilization rule. Stability may be defined by confidence, convergence, contradiction rate, explicit task completion, human approval, bounded deliberation, repeated consistency checks, or a domain-specific criterion.

## 4. Commit envelope

A recommended commit contains:

```text
Commit {
  commit_id
  source_agent_id
  base_version
  local_cycle_id
  conclusion
  evidence_summary
  confidence
  scope
  assumptions
  known_limitations
  supersedes[]
  contradicts[]
  created_at
}
```

Only `conclusion` is conceptually mandatory. The additional fields are recommended because second-stage integration is difficult without provenance and scope.

## 5. Distinguishing communication from knowledge commit

BECA does not require agent isolation from all communication.

A system may have two channels:

```text
Operational channel
- coordination
- routing
- resource requests
- task status
- safety signals

Knowledge commit channel
- stabilized conclusions
- model deltas judged complete
- validated local findings
```

The architectural claim concerns the second channel.

## 6. Second-stage integration

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
evidence weighting
        |
deduplication
        |
abstraction / generalization
        |
shared update candidate
```

The integration layer SHOULD NOT blindly average all commits. A BECA-compatible integrator may reject, quarantine, defer, merge, generalize, or supersede commits.

## 7. Supersession

A committed conclusion is immutable, but knowledge is not permanently frozen.

Example:

```text
A.Commit.12 = "X causes Y under condition C"

Later local work produces:

A.Commit.19 = "X causes Y only when C and D hold"
              supersedes A.Commit.12
```

The earlier commit remains part of provenance history, while the later commit can replace it in active shared knowledge after integration.

This preserves two properties at once:

1. no in-place mutation of already-integrated source data;
2. long-term ability to correct knowledge.

## 8. Failure modes BECA is designed to study

BECA is motivated by, but does not yet claim to solve, the following failure modes:

- provisional-belief propagation;
- stale local state participating in global fusion;
- repeated global recomputation caused by local revision;
- source contamination, where one agent's unfinished belief influences another before independent evaluation;
- premature consensus;
- loss of provenance during aggregation;
- unstable global state caused by high-frequency low-quality updates.

## 9. Non-goals

BECA is not intended to guarantee:

- truth;
- consensus;
- optimal communication efficiency;
- convergence in all environments;
- immunity from malicious agents;
- perfect detection of when a conclusion is ready.

It is an architectural proposal for **where mutability is allowed and when cross-source fusion is permitted**.

## 10. Minimal conformance

A system is minimally BECA-like if all of the following hold:

1. agents have locally mutable knowledge state;
2. that mutable state is not automatically treated as shared learned knowledge;
3. agents publish explicit stable commits;
4. commits are immutable/versioned;
5. a higher layer integrates multiple commits while preserving source provenance during integration.
