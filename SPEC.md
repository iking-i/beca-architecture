# BECA Specification v0.3

This document defines the minimum concepts and invariants required for a system to meaningfully claim compatibility with **Bounded Evolutionary Commit Architecture (BECA)**.

## 1. Terminology

### 1.1 Parent system
A shared or higher-level system that distributes one common initial state into multiple agents and later integrates the results of their local evolution.

### 1.2 Common initial state
The same baseline state inherited by all agents before their trajectories diverge.

It may include rules, ontology, prior knowledge, protocols, default behavior, constraints, and a model of the world.

BECA assumes **one shared origin**, not merely several compatible but independently initialized systems.

### 1.3 Shared world
The larger environment within which multiple agents exist.

Agents occupy different local regions, receive different events, form different relationships, and accumulate different histories while remaining inside one coherent world.

### 1.4 Agent boundary
A logical boundary inside which information may remain mutable, provisional, contradictory, incomplete, or under active revision.

The boundary protects local state ownership and local evolution. It is not a prohibition on communication.

### 1.5 Dynamic local state
Any information inside an agent that is still changing as a consequence of observation, peer communication, contradiction, reinterpretation, learning, repetition, forgetting, weighting, or structural revision.

### 1.6 Peer communication
Messages exchanged between agents during local evolution.

Peer communication may include observations, questions, hypotheses, warnings, partial interpretations, requests, or coordination signals.

A peer message becomes input to the receiving agent's local evolution. It does not automatically become authoritative parent-level knowledge.

### 1.7 Local evolutionary closure
The point at which a local evolutionary process ends for the information being considered.

Closure does **not** mean absolute truth or maximal confidence.

It may occur because:

- further local experience no longer materially changes the result;
- repeated experience becomes redundant;
- new information receives too little weight to alter the established structure;
- the local system reaches a practical fixed point;
- a finite lifetime, time budget, resource budget, or externally imposed boundary ends the process;
- a human or external controller declares the local process complete.

A finite lifetime therefore acts as a natural or artificial boundary on local evolution. A system does not need an explicit "life task" in order for its accumulated information to eventually become fixed enough, or its processing window finite enough, that the local process ends.

### 1.8 Determinate result
The result that exists when a local evolutionary process has ended.

A determinate result is final **for that completed local process**. It may still be superseded in a later generation or by a later higher-level state, but the original local process no longer continues to modify it.

### 1.9 Commit
The transfer of a determinate result from the completed local process into the higher-level integration process.

A commit is conceptually about **result transfer**, not about preserving the identity or history of the source agent.

### 1.10 Integration layer
The higher-level process that consumes determinate results from multiple agents and performs second-stage processing such as comparison, conflict handling, deduplication, abstraction, recombination, and generalization.

### 1.11 Useful delta
The transferable difference produced by one agent's local history relative to the common initial state.

## 2. Core invariants

### BECA-I1 — Same origin, divergent local histories
Agents in one BECA population MUST begin from the same common initial state while being allowed to experience different local regions, events, relationships, and histories in the shared world.

### BECA-I2 — Mutable local state remains locally owned
Dynamic local state MUST NOT be treated as authoritative higher-level knowledge while its local evolutionary process is still active.

An agent MAY communicate provisional information to peers, but the receiving peer treats it as new input to its own local evolution.

### BECA-I3 — Communication is permitted
BECA MUST NOT be interpreted as requiring communication isolation.

Agents MAY exchange observations, provisional beliefs, questions, critiques, warnings, coordination signals, and unfinished ideas during evolution.

### BECA-I4 — Peer communication and higher-level integration are distinct
A peer message MAY change another agent immediately.

That message MUST NOT, merely by being transmitted, count as a completed result entering the higher-level integration process.

### BECA-I5 — Local evolution must end before higher-level fusion
Information becomes eligible for higher-level integration only after the relevant local evolutionary process has ended.

The end condition may be endogenous (fixation/convergence/redundancy) or exogenous (finite lifetime, time/resource limit, human approval, or another explicit termination boundary).

### BECA-I6 — A completed local result is not rewritten by the ended process
Once the local process has ended and its result has been committed, that completed process no longer modifies the submitted result.

Future change belongs to a new process, a new generation, or a new higher-level state rather than to retroactive mutation of the finished local process.

### BECA-I7 — Integration consumes results, not unfinished local processes
The integration layer SHOULD operate on determinate results produced by completed local evolution rather than replaying every mutable intermediate state.

### BECA-I8 — Source identity is optional
BECA does NOT require the integration layer to preserve the identity of the agent that produced a result.

In some implementations, provenance may be useful for debugging, auditing, trust, or analysis. These are implementation concerns, not a theoretical invariant.

The theoretical requirement is only that the higher layer receives multiple determinate results that can be integrated.

## 3. Local lifecycle

A minimal BECA lifecycle is:

```text
COMMON INITIAL STATE
        |
        v
ENTER LOCAL REGION / LOCAL HISTORY
        |
        v
OBSERVE / COMMUNICATE / RECEIVE PEER INPUT
        |
        v
LOCAL DYNAMIC EVOLUTION
        |
        +--> revise
        +--> reject
        +--> relate
        +--> compress
        +--> reinforce
        +--> weaken
        +--> incorporate or reject peer messages
        |
        v
HAS THIS LOCAL EVOLUTION ENDED?
        |
        +-- no --> continue local evolution
        |
        +-- yes --> DETERMINATE RESULT
                        |
                        v
                      COMMIT
```

The end of local evolution need not be caused by a task being solved.

A finite system can reach closure simply because its lifetime or processing window ends. This is analogous to a biological organism that has no single explicit life objective but nevertheless has a finite lifespan during which its accumulated structure gradually becomes more fixed.

## 4. World positioning

BECA gains meaning from **same origin + different situated experience**.

```text
M0 = common initial state

Agent A = M0 + local history HA
Agent B = M0 + local history HB
Agent C = M0 + local history HC
```

where `HA`, `HB`, and `HC` arise from different positions, events, relationships, and peer interactions inside one shared world.

The purpose of multiple agents is not duplication of `M0`, but differentiated evolution from one common starting point.

## 5. Communication semantics

BECA recognizes three distinct flows.

### 5.1 Environment input
Information originating from the shared world.

### 5.2 Peer communication
Information exchanged among agents during evolution.

These messages may change the receiver's dynamic local state.

### 5.3 Result commit
A determinate result transferred after the local evolutionary process has ended.

The distinction is:

```text
peer message -> local input -> further local evolution

completed local evolution -> determinate result -> higher-level integration
```

## 6. Result envelope

A minimal BECA result requires only the result itself.

```text
Result {
  conclusion
}
```

An implementation MAY attach optional metadata such as:

```text
scope
assumptions
limitations
evidence summary
confidence
source identity
local history summary
```

None of these metadata fields are required by the core theory.

The upper layer needs the **result of the completed local evolution**. It does not need to reconstruct the individual that produced it.

## 7. Second-stage integration

The integration layer receives multiple determinate results:

```text
Result A
Result B
Result C
    |
    v
comparison
    |
conflict handling
    |
deduplication
    |
relation discovery
    |
abstraction / recombination / generalization
    |
new shared state candidate
```

The higher layer performs a new type of processing across already-completed local results.

It is not simply continuing the unfinished cognition of any one agent.

## 8. Completed does not mean eternally true

A determinate result is final only relative to its ended local process.

Later generations or later system states may produce different results.

For example:

```text
Generation 1 result: X causes Y under condition C

Later shared state and new local evolution:

Generation 2 result: X causes Y only when C and D hold
```

The second result does not mean the first local process "resumed." It means a new evolutionary process produced a new result.

## 9. What BECA does and does not isolate

BECA isolates **local dynamic evolution from higher-level fusion**.

It does not require:

- social isolation;
- silent agents;
- independent universes;
- absence of collaboration;
- absence of provisional discussion;
- permanent source tracking.

It does require that unfinished local change not be treated as a completed input to second-stage integration.

## 10. Generational cycle

A natural BECA cycle is:

```text
M0
 |
 +--> Agent A local evolution --+
 +--> Agent B local evolution --+--> determinate results --> second-stage integration --> M1
 +--> Agent C local evolution --+

M1 can then become the common initial state of a later generation.
```

This allows the shared system to evolve without requiring every local intermediate mutation to become global state.

## 11. Minimal conformance

A system is minimally BECA-like if all of the following hold:

1. multiple agents begin from the same initial state;
2. agents experience different local histories within one shared world;
3. agents may communicate during local evolution;
4. mutable local state remains locally owned;
5. peer messages become local input rather than automatic higher-level truth;
6. the relevant local evolutionary process ends before its result enters higher-level integration;
7. the higher layer processes multiple determinate results rather than unfinished local states;
8. source identity is not required by the theory.
