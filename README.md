# BECA — Bounded Evolutionary Commit Architecture

> **A theory proposal for multi-agent knowledge systems:** multiple agents begin from the same initial state, evolve in different local regions of one shared world, communicate during that evolution, and pass only the results of completed local evolutionary processes into higher-level integration.

**Status:** v0.1 conceptual architecture / theory proposal  
**Not:** a software product, benchmark suite, or experimentally validated implementation

## In one sentence

> **Same origin + shared world + local evolution + peer communication + local closure + result commit + second-stage integration.**

## Core distinction

BECA does **not** isolate agents from one another.

Agents may communicate observations, questions, hypotheses, warnings, and unfinished ideas while they evolve. Those messages become part of the receiver's local experience.

What BECA separates is something narrower:

> **Information may remain dynamic while its local evolutionary process is active; only the result of a completed local process enters higher-level integration.**

Completion does not mean absolute truth or maximum confidence. A local process can end because it has effectively become fixed, because additional experience no longer changes it materially, or because a finite lifetime, time/resource limit, or external approval ends that process.

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
       closure          closure          closure
          |               |               |
      Result A         Result B         Result C
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
M0 -> differentiated local evolution -> completed results -> integration -> M1 -> ...
```

## Why propose this?

A local intelligent process may change its interpretation many times:

```text
observation
  -> provisional interpretation
  -> peer input / contradiction / new evidence
  -> revision
  -> relation-building
  -> reinforcement / weakening
  -> local closure
  -> determinate result
```

BECA treats this changing process as different from the task of integrating several already-completed results.

The proposal is that these stages should have different rules:

- **inside an agent:** information may remain dynamic;
- **between agents:** communication may remain dynamic;
- **at the higher integration layer:** only results from ended local processes are accepted as integration inputs.

## Five principles

### 1. Same initial state
Agents begin from one shared initial state. Their later differences should arise from different local histories, not from unrelated starting systems.

### 2. Situated local evolution
Agents occupy different positions in the same larger world. Their histories diverge because their local observations, relationships, events, failures, opportunities, and interactions differ.

### 3. Communicating boundaries
The local boundary protects ownership of mutable cognition; it is not a communication wall. Peer messages can influence an agent without directly becoming higher-level shared knowledge.

### 4. Local evolutionary closure
A local process eventually ends. This may happen through internal fixation or through a finite lifetime or external termination boundary. Its output then becomes a determinate result for that completed process.

### 5. Second-stage integration
The higher layer operates on multiple determinate results and performs a new round of processing across them. It does not need to reconstruct or preserve the individual that produced each result unless an implementation chooses to do so.

## Data, experience, result, knowledge

BECA distinguishes four levels:

- **data** — an observation or received message;
- **experience** — information transformed through a local evolutionary history;
- **determinate result** — the output of an ended local evolutionary process;
- **shared knowledge** — a result produced by second-stage integration across multiple completed local results.

## What BECA is not

BECA is not a theory of non-communicating agents.

A message from Agent A may change Agent B. But that message first enters B as input. It does not automatically become higher-level truth simply because A transmitted it.

BECA is also not a theory of permanent truth. A determinate result is final only relative to the local process that has ended. Later generations or later shared states may produce different results.

BECA does not require permanent source tracking. The upper layer needs the result; source identity, provenance, or history may be added for engineering reasons but are not part of the theoretical minimum.

## Current contribution

This repository proposes the architectural sequence itself:

> **same origin + shared world + situated local evolution + peer communication + local closure + result commit + second-stage integration**

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
- how the higher layer should combine mutually incompatible completed results;
- how integrated state should become the basis for later generations.

## Invitation

This is a theory proposal, not a claim of completed validation.

If you see an equivalent prior architecture, a contradiction, a better formalization, or a domain where the distinction clearly fails, open an Issue. If you implement or test it, negative results are as useful as positive ones.
