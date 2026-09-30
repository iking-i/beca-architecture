# BECA Specification v0.4

This document defines the minimum concepts and invariants required for a system to meaningfully claim compatibility with **Bounded Evolutionary Commit Architecture (BECA)**.

## 1. Terminology

### 1.1 Parent system
A shared or higher-level system that distributes one common initial state into multiple agents and later performs second-stage processing across the states left by their local evolution.

### 1.2 Common initial state
The same baseline state inherited by all agents before their trajectories diverge.

It may include rules, ontology, prior knowledge, protocols, default behavior, constraints, and a model of the world.

BECA assumes one shared origin, not merely several compatible but independently initialized systems.

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

A peer message becomes input to the receiving agent's local evolution. It does not automatically become higher-level shared state.

### 1.7 Local evolutionary closure
The boundary at which a local evolutionary process stops changing the state under consideration.

This is the central BECA transition.

Closure does **not** require:

- completion of a task;
- a correct answer;
- a coherent conclusion;
- high confidence;
- maximum knowledge;
- internal consistency.

Closure only requires that, for this local process, the state is no longer changing.

This may happen because:

- repeated experience no longer changes the structure;
- new information has too little effective weight to alter an established structure;
- the local process reaches a practical fixed point;
- a finite lifetime ends;
- a time or resource boundary is reached;
- a human or external controller terminates the process.

A finite lifetime therefore functions as a natural or artificial boundary even when the agent has no explicit life task.

### 1.8 Closed local state
The state that remains when local evolutionary change has stopped.

A closed local state may be complete or incomplete, correct or wrong, coherent or contradictory. Those properties are separate from closure.

The defining property is simply:

> **the local process no longer changes it.**

### 1.9 Commit
The transfer of a closed local state, or information extracted from that closed state, into the higher-level integration process.

Commit is an engineering name for crossing the boundary. The theoretical core is not the act of producing a result; it is the transition from a changing local state to a non-changing local state that can now be used by the higher layer.

### 1.10 Integration layer
The higher-level process that consumes multiple closed local states or their transferred information and performs second-stage processing such as comparison, conflict handling, deduplication, relation discovery, abstraction, recombination, and generalization.

### 1.11 Useful delta
The transferable difference produced by one agent's local history relative to the common initial state.

## 2. Core invariants

### BECA-I1 — Same origin, divergent local histories
Agents in one BECA population MUST begin from the same common initial state while being allowed to experience different local regions, events, relationships, and histories in the shared world.

### BECA-I2 — Mutable local state remains locally owned
Dynamic local state MUST NOT become an input to higher-level fusion merely because it currently exists or has been communicated.

An agent MAY communicate provisional information to peers, and the receiving peer MAY use it as input to its own local evolution.

### BECA-I3 — Communication is permitted
BECA MUST NOT be interpreted as requiring communication isolation.

Agents MAY exchange observations, provisional beliefs, questions, critiques, warnings, coordination signals, and unfinished ideas during evolution.

### BECA-I4 — Peer communication and higher-level integration are distinct
A peer message MAY change another agent immediately.

Transmission between peers does not itself mean that the transmitted information has crossed the local-to-higher-level integration boundary.

### BECA-I5 — The boundary is cessation of local change
Information becomes eligible for higher-level integration only when the relevant local evolutionary process no longer changes it.

The important distinction is therefore:

```text
changing local state  !=  integration input
closed local state     ->  integration input
```

### BECA-I6 — Closure may be endogenous or exogenous
The cessation of change may arise from internal fixation, redundancy, weighting dynamics, or another local fixed point; or it may arise because an external lifetime, time, resource, or human boundary stops the process.

BECA does not require a goal-completion event.

### BECA-I7 — Closure does not imply correctness or completeness
A closed local state MAY still contain uncertainty, error, contradiction, missing information, or unresolved structure.

The higher layer exists precisely because several closed local states may still need further processing when considered together.

### BECA-I8 — Integration consumes closed states, not unfinished processes
The integration layer SHOULD operate on information that is no longer changing within the source local process rather than continuously fusing all intermediate mutations.

### BECA-I9 — Source identity is optional
BECA does NOT require the integration layer to preserve the identity of the agent that produced a closed state.

Provenance may be useful for debugging, auditing, trust, or research, but it is not a theoretical invariant.

The higher layer theoretically needs the closed information, not the continued existence or reconstruction of its source individual.

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
IS THIS STATE STILL CHANGING IN THIS LOCAL PROCESS?
        |
        +-- yes --> continue local evolution
        |
        +-- no  --> CLOSED LOCAL STATE
                        |
                        v
                higher-level integration
```

No explicit task needs to have been solved.

A biological analogy is a finite organism with no single explicit life objective: its internal state changes throughout life, some structures gradually become difficult to alter, and eventually the local process ends because the organism's lifetime ends. Whatever state remains is no longer changed by that organism.

## 4. World positioning

BECA gains meaning from **same origin + different situated experience**.

```text
M0 = common initial state

Agent A(t) = M0 transformed by local history HA(t)
Agent B(t) = M0 transformed by local history HB(t)
Agent C(t) = M0 transformed by local history HC(t)
```

`HA`, `HB`, and `HC` arise from different positions, events, relationships, and peer interactions inside one shared world.

The purpose of multiple agents is not duplication of `M0`, but differentiated evolution from one common starting point.

## 5. Communication semantics

BECA recognizes three distinct flows.

### 5.1 Environment input
Information originating from the shared world.

### 5.2 Peer communication
Information exchanged among agents while their local states are still capable of changing.

These messages may change the receiver's dynamic local state.

### 5.3 Closed-state transfer
Information crossing upward after the relevant local change has ceased.

The distinction is:

```text
peer message -> local input -> further local change

cessation of local change -> closed local state -> second-stage integration
```

## 6. What crosses the boundary

BECA does not require a semantic "answer" or "conclusion" object.

At minimum, what crosses the boundary is information representing the closed local state strongly enough for the higher layer to process it.

An implementation MAY transmit:

- the whole closed state;
- a compressed representation;
- selected information extracted from it;
- a conclusion if one exists;
- optional metadata.

Possible optional metadata include scope, assumptions, limitations, confidence, source identity, or a local-history summary.

None of these are required by the core theory.

## 7. Second-stage integration

The integration layer receives information from multiple closed local states:

```text
Closed state A
Closed state B
Closed state C
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
new shared state M1
```

The higher layer performs a new type of processing across information that is no longer changing within its source local processes.

It is not simply continuing the unfinished cognition of one agent.

## 8. Closed does not mean eternally true

Closure is relative to one ended local process.

A later generation can begin from a new common state and evolve again.

For example:

```text
Generation 1 closes at state S1
        |
        v
second-stage integration produces M1
        |
        v
Generation 2 starts from M1 and changes again
```

The later change does not mean the first local process resumed. It is a new process operating from a later state.

## 9. What BECA does and does not isolate

BECA isolates **ongoing local change from higher-level fusion**.

It does not require:

- social isolation;
- silent agents;
- independent universes;
- absence of collaboration;
- absence of provisional discussion;
- permanent source tracking;
- task completion;
- a finalized semantic conclusion.

It requires only that higher-level integration not continuously consume information that is still changing inside the relevant local process.

## 10. Generational cycle

A natural BECA cycle is:

```text
M0
 |
 +--> Agent A local evolution --+ -> closed state A --+
 +--> Agent B local evolution --+ -> closed state B --+--> second-stage integration --> M1
 +--> Agent C local evolution --+ -> closed state C --+

M1 can then become the common initial state of a later generation.
```

This allows the shared system to evolve without requiring every local intermediate mutation to become global state.

## 11. Minimal conformance

A system is minimally BECA-like if all of the following hold:

1. multiple agents begin from the same initial state;
2. agents experience different local histories within one shared world;
3. agents may communicate during local evolution;
4. mutable local state remains locally owned;
5. peer messages become local input rather than automatic higher-level fusion input;
6. the relevant local state stops changing before it crosses into higher-level integration;
7. the higher layer processes information from multiple closed local states rather than continuously fusing unfinished local mutations;
8. neither task completion nor a semantic "result" is required;
9. source identity is not required by the theory.
