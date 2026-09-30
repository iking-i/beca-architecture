# BECA — Bounded Evolutionary Commit Architecture

> **A theory proposal for multi-agent knowledge systems:** agents share a common initial worldview, evolve in different local regions of the same world, communicate during that evolution, and submit only stabilized conclusions for higher-level integration.

**Status:** v0.1 conceptual architecture / theory proposal  
**Not:** a software product, benchmark suite, or experimentally validated implementation

## In one sentence

> **Common origin + shared world + local evolution + peer communication + stable commit + second-stage integration.**

## Core distinction

BECA does **not** isolate agents from one another.

Agents may communicate observations, questions, hypotheses, warnings, and unfinished ideas while they evolve. Those messages become part of the receiver's local experience.

What BECA delays is something narrower:

> **An unfinished local cognitive state should not automatically become authoritative shared knowledge.**

Only a stabilized local conclusion becomes eligible for higher-level integration.

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
      Commit A         Commit B         Commit C
           \              |              /
            +-------------+-------------+
                          |
                          v
                Second-stage integration
          compare / resolve conflict / abstract /
          preserve scope / generalize / update
                          |
                          v
                    shared state M1
```

The same process can repeat:

```text
M0 -> differentiated local evolution -> commits -> integration -> M1 -> ...
```

## Why propose this?

A local intelligent process may change its interpretation many times before reaching a conclusion:

```text
observation
  -> provisional interpretation
  -> peer input / contradiction / new evidence
  -> revision
  -> relation-building
  -> stabilized conclusion
```

BECA treats this changing process as different from the task of integrating several already-stabilized source conclusions.

The proposal is that these two stages should have different mutability rules:

- **inside an agent:** information may remain dynamic;
- **between agents:** communication may remain dynamic;
- **at the higher knowledge-integration layer:** source contributions should arrive as explicit stable commits.

## Five principles

### 1. Common initial worldview
Agents begin from the same or mutually compatible baseline: rules, ontology, inherited knowledge, protocols, and a basic model of the world.

### 2. Situated local evolution
Agents occupy different positions in the same larger world. Their histories diverge because their local observations, relations, events, and interactions differ.

### 3. Communicating boundaries
The local boundary protects ownership of mutable cognition; it is not a communication wall. Peer messages can influence an agent without directly overwriting the parent knowledge state.

### 4. Stable commit
A locally stabilized conclusion is published as an explicit, versioned source contribution. Later corrections create later commits rather than silently rewriting the earlier source state.

### 5. Second-stage integration
The higher layer works across multiple source-preserving commits: identifying agreement, conflict, scope, duplication, exceptions, and higher-level common structure.

## Data, experience, conclusion, knowledge

BECA distinguishes four levels:

- **data** — an observation or received message;
- **experience** — information transformed through a local evolutionary history;
- **committed conclusion** — a locally stabilized source result;
- **shared knowledge** — a result produced by second-stage integration across multiple source conclusions.

## What BECA is not

BECA is not a theory of non-communicating agents.

A message from Agent A may change Agent B. But that message first enters B as input. It does not automatically become parent-level truth simply because A transmitted it.

BECA is also not a claim that stabilized conclusions are permanently true. A later local cycle may produce a new commit that supersedes an earlier one.

## Current contribution

This repository proposes the architectural separation itself:

> **common origin + shared world + situated local evolution + peer communication + stable source commits + second-stage multi-source integration**

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

- how identical the common initial worldview must be;
- how local position/perspective should be represented;
- how agents should evaluate provisional peer messages;
- how stabilization should be defined;
- what metadata a commit should carry;
- how the integration layer should combine stable but mutually incompatible conclusions;
- how integrated state should become the basis for later generations.

## Invitation

This is a theory proposal, not a claim of completed validation.

If you see an equivalent prior architecture, a contradiction, a better formalization, or a domain where the distinction clearly fails, open an Issue. If you implement or test it, negative results are as useful as positive ones.
