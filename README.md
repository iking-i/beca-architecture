# BECA — Bounded Evolutionary Commit Architecture

> **A theory proposal for multi-agent knowledge systems:** multiple agents begin from the same initial state, evolve in different local regions of one shared world, communicate during that evolution, and expose information to higher-level integration only after the relevant local state has stopped changing.

**Status:** v0.1 conceptual architecture / theory proposal  
**Not:** a software product, benchmark suite, or experimentally validated implementation

## In one sentence

> **Same origin + shared world + local evolution + peer communication + cessation of local change + second-stage integration.**

## Core distinction

BECA does **not** isolate agents from one another.

Agents may communicate observations, questions, hypotheses, warnings, and unfinished ideas while they evolve. Those messages become part of the receiver's local experience.

The decisive boundary is not whether an agent has produced a result. It is whether the relevant local information is **still changing**.

> **While a local state is changing, it remains part of local evolution. Once that local change stops, the state becomes eligible for higher-level integration.**

Closure does not require a solved task, a correct answer, a coherent conclusion, or high confidence.

A closed state may still be incomplete, wrong, contradictory, or unresolved. The only defining property is that the local process no longer changes it.

## Architecture

```text
                 Common initial state M0
        shared rules / ontology / worldview
                          |
          +---------------+---------------+
          |               |               |
          v               v               v
      Agent A         Agent B         Agent C
      region A        region B        region C
          |               |               |
          +<---- peer communication ----->+
          |               |               |
       local            local            local
      evolution        evolution        evolution
          |               |               |
   change stops      change stops      change stops
          |               |               |
   closed state A   closed state B   closed state C
           \              |              /
            +-------------+-------------+
                          |
                          v
                Second-stage integration
           compare / combine / abstract /
               generalize / update
                          |
                          v
                    shared state M1
```

The cycle can repeat:

```text
M0 -> differentiated local evolution -> local closure -> second-stage integration -> M1 -> ...
```

## Why propose this?

A local intelligent process may change repeatedly:

```text
observation
  -> provisional interpretation
  -> peer input / contradiction / new evidence
  -> revision
  -> relation-building
  -> reinforcement / weakening
  -> further change
  -> ...
  -> change stops
```

BECA treats this changing process as different from the task of integrating several already-closed local states.

The proposal is that these stages should have different rules:

- **inside an agent:** information may remain dynamic;
- **between agents:** communication may remain dynamic;
- **at the higher integration layer:** only information from local states that are no longer changing is accepted.

## Five principles

### 1. Same initial state
Agents begin from one shared initial state. Their later differences arise from different local histories, not from unrelated starting systems.

### 2. Situated local evolution
Agents occupy different positions in the same larger world. Their histories diverge because their local observations, relationships, events, failures, opportunities, and interactions differ.

### 3. Communicating boundaries
The local boundary protects ownership of mutable cognition; it is not a communication wall. Peer messages can influence an agent without directly becoming higher-level shared state.

### 4. Local evolutionary closure
A local state eventually stops changing within that process. This may happen through internal fixation, repeated experience becoming redundant, declining effective weight of new information, finite lifetime, time/resource limits, or external termination.

### 5. Second-stage integration
The higher layer operates on information from multiple closed local states and performs a new round of processing across them. It does not need a semantic answer from each agent, and it does not need to preserve the individual that produced each state.

## Data, experience, closed state, shared knowledge

BECA distinguishes four levels:

- **data** — an observation or received message;
- **experience** — information transformed through a local evolutionary history;
- **closed local state** — information that the relevant local process no longer changes;
- **shared knowledge** — information produced by second-stage processing across multiple closed local states.

## What BECA is not

BECA is not a theory of non-communicating agents.

A message from Agent A may change Agent B. But that message first enters B as input. It does not automatically become higher-level state simply because A transmitted it.

BECA is also not a theory of permanent truth. A closed local state is closed only relative to the ended local process. A later generation can start from a new shared state and evolve again.

BECA does not require permanent source tracking. The upper layer needs the closed information; source identity, provenance, or history may be added for engineering reasons but are not part of the theoretical minimum.

## Current contribution

This repository proposes the architectural sequence itself:

> **same origin + shared world + situated local evolution + peer communication + cessation of local change + second-stage integration**

The aim is to define the theory clearly enough that others can critique it, formalize it, implement it, compare it with adjacent architectures, or test where it fails.

## Repository map

- [`SPEC.md`](SPEC.md) — terminology and minimum architectural invariants
- [`ARCHITECTURE.md`](ARCHITECTURE.md) — detailed system structure and lifecycle
- [`TESTABLE_PREDICTIONS.md`](TESTABLE_PREDICTIONS.md) — observations that could support, narrow, or contradict the theory
- [`PRIOR_ART.md`](PRIOR_ART.md) — adjacent architectures and candidate distinctions
- [`CONTRIBUTING.md`](CONTRIBUTING.md) — how to critique or extend the proposal
- [`paper/BECA_v0.1.md`](paper/BECA_v0.1.md) — conceptual paper draft
- [`CITATION.cff`](CITATION.cff) — citation metadata

## Open questions

BECA v0.1 leaves several mechanisms open intentionally:

- how local fixation should be recognized;
- how different kinds of finite lifetime or external termination should be represented;
- how local position/perspective should be represented;
- how agents should evaluate provisional peer messages;
- how much of a closed state should cross the boundary;
- how the higher layer should combine incompatible closed states;
- how integrated state should become the basis for later generations.

## Invitation

This is a theory proposal, not a claim of completed validation.

If you see an equivalent prior architecture, a contradiction, a better formalization, or a domain where the distinction clearly fails, open an Issue. If you implement or test it, negative results are as useful as positive ones.
