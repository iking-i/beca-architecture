# BECA — Bounded Evolutionary Commit Architecture

> **A theory proposal for evolutionary multi-agent systems:** one initial agent state first differentiates into multiple identical agents. Those agents then evolve continuously in different local regions of one shared world, may communicate during that evolution, and expose information to higher-level integration only after the relevant local state has stopped changing.

**Status:** v0.2 conceptual architecture / theory proposal  
**Not:** a software product, benchmark suite, or experimentally validated implementation

## In one sentence

> **One origin + first differentiation + continuous lineages + local evolution + peer communication + cessation of local change + second-stage integration + root-level structural improvement.**

## Core distinction

BECA does **not** isolate agents from one another.

Agents may communicate observations, questions, hypotheses, warnings, and unfinished ideas while they evolve. Those messages become part of the receiver's local experience.

The decisive boundary is not whether an agent has produced a semantic result. It is whether the relevant local information is **still changing**.

> **While a local state is changing, it remains part of local evolution. Once that local change stops, the state becomes eligible for higher-level integration.**

Closure does not require a solved task, a correct answer, a coherent conclusion, or high confidence.

A closed state may still be incomplete, wrong, contradictory, or unresolved. The defining property is only that the local process no longer changes it.

## First differentiation

BECA begins with one base agent `A`.

The first differentiation creates multiple agents with the **same initial state**:

```text
            A
         /  |  \
        B   C   D

initially:
A = B = C = D
```

`B`, `C`, and `D` are differentiations of `A`, not independently designed agents with different initial assumptions.

Their later differences arise from different local histories in the same world.

## Continuity after the first differentiation

The first differentiation is special.

After `B`, `C`, and `D` begin evolving, later differentiation must preserve the continuity of those lineages.

BECA therefore does **not** require this pattern:

```text
A0 -> B0 / C0 / D0
      closed information -> A1
A1 -> reset B1 / C1 / D1
```

That would repeatedly erase accumulated local history and recreate the environment from a new template.

Instead, existing branches continue from their own evolved states and may themselves differentiate further:

```text
             A
          /  |  \
         B   C   D
        / \     / \
       ...     ...

local histories continue along the branches
```

The evolutionary tree therefore grows outward continuously rather than being rebuilt from the root after every integration cycle.

## Root-level improvement

As branch states stop changing, information from those closed local states can return to `A` for second-stage processing.

```text
closed information from B --+
closed information from C ---+--> A: second-stage integration
closed information from D --+             |
                                           v
                                modification of A's base structure
```

This improvement is stronger than merely appending facts to a knowledge store.

The integrated information may modify the **underlying structure** of `A`: rules, weights, defaults, relations, processing structure, or other foundational mechanisms.

However, improving `A` does **not** imply resetting the already-evolving branches from the new `A` state.

The mechanism by which later changes to `A` may influence existing continuous lineages is intentionally left open until specified more precisely.

## Architecture

```text
                 Root agent A
              initial base state
                     |
          first differentiation only
          +----------+----------+
          |          |          |
          v          v          v
          B          C          D
      local world local world local world
          |          |          |
          +<--- peer communication --->+
          |          |          |
       continuous continuous continuous
       evolution  evolution  evolution
          |          |          |
     state stops state stops state stops
          |          |          |
          +----------+----------+
                     |
                     v
             second-stage integration
                     |
                     v
            modify A's base structure

Meanwhile, existing branches continue from their own histories
and may differentiate further without being reset from A.
```

## Five principles

### 1. One shared origin
The first differentiated agents begin from the same initial state. Their differences come from experience, not different initialization.

### 2. Continuous situated evolution
Each branch preserves its accumulated local history. Later differentiation extends existing lineages rather than recreating them from the updated root.

### 3. Communicating boundaries
The local boundary protects mutable evolution; it is not a communication wall. Peer messages may influence local change without automatically entering higher-level integration.

### 4. Local evolutionary closure
A local state can enter higher-level integration only after the relevant local process no longer changes it. Closure may arise through fixation, redundancy, finite lifetime, resource limits, or external termination.

### 5. Root-level structural integration
The root integrates information from closed branch states and may use it to modify its own underlying structure. This root improvement is distinct from resetting the branch lineages.

## Why continuity matters

If every integration cycle created fresh agents from the newest root state, the system would repeatedly lose:

- accumulated local experience;
- environmental continuity;
- long-term relationships;
- path-dependent adaptation;
- historical differences created by earlier evolution.

The system would be performing repeated reinitialization rather than continuous evolution.

BECA therefore treats **lineage continuity** as essential after the first differentiation.

## What BECA is not

BECA is not a theory of non-communicating agents.

BECA is not a theory in which every branch must solve a task before contributing upward.

BECA is not a repeated-reset architecture in which every new cycle clones the newest root state into fresh agents.

BECA does not require permanent source tracking. The higher layer needs closed information; source identity and provenance are optional engineering additions.

## Current contribution

The current theory proposes the following structure:

> **one initial agent -> first identical differentiation -> continuous situated lineages -> local change -> local closure -> upward integration -> root-level structural improvement, while branch continuity is preserved.**

## Repository map

- [`SPEC.md`](SPEC.md) — terminology and minimum architectural invariants
- [`ARCHITECTURE.md`](ARCHITECTURE.md) — detailed system structure and lifecycle
- [`TESTABLE_PREDICTIONS.md`](TESTABLE_PREDICTIONS.md) — observations that could support, narrow, or contradict the theory
- [`PRIOR_ART.md`](PRIOR_ART.md) — adjacent architectures and candidate distinctions
- [`CONTRIBUTING.md`](CONTRIBUTING.md) — how to critique or extend the proposal
- [`paper/BECA_v0.1.md`](paper/BECA_v0.1.md) — conceptual paper draft
- [`CITATION.cff`](CITATION.cff) — citation metadata

## Open questions

BECA currently leaves several mechanisms open intentionally:

- how local fixation should be recognized;
- how finite lifetime or external termination should be represented;
- how later differentiation occurs along an existing lineage;
- how modification of A's underlying structure should be represented;
- whether and how later changes to A influence already-continuous branches without resetting them;
- how much of a closed local state should cross the integration boundary;
- how the higher layer should combine incompatible closed states.

## Invitation

This is a theory proposal, not a claim of completed validation.

If you see an equivalent prior architecture, a contradiction, a better formalization, or a domain where the distinction clearly fails, open an Issue. If you implement or test it, negative results are as useful as positive ones.
