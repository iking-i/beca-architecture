# BECA — Bounded Evolutionary Commit Architecture

> **A theory proposal for an evolvable recursive multi-agent system:** a base agent differentiates into identical local agents, those agents evolve through different experiences in one shared world, closed information returns to the base integrator, and when the current round stops changing the accumulated knowledge is used to modify the base layer and form the next-generation base agent.

**Status:** v0.3 conceptual architecture / theory proposal  
**Not:** a software product, benchmark suite, or experimentally validated implementation

## In one sentence

> **Differentiate -> experience -> change -> local closure -> integrate knowledge -> round closure -> modify the base layer -> form A(n+1) -> differentiate again.**

## The recursive model

Let the base agent in round `n` be:

```text
A_n = base layer L_n + knowledge state K_n
```

At the start of the round, `A_n` differentiates into local agents with the same initial state:

```text
A_n = B_n = C_n = D_n   at differentiation
```

`B_n`, `C_n`, and `D_n` then enter different local regions and accumulate different experiences while remaining in the same world. They may communicate with one another.

During the round, information remains local while it is still changing. When some local information stops changing, it becomes eligible to return to `A_n`.

`A_n` first acts as an **integration database**: it accumulates and reorganizes closed information from the differentiated agents.

The round does **not** advance because a target amount of knowledge has been reached. It advances when the relevant state of the current round **stops changing**.

At that point, the accumulated knowledge is used to modify the underlying base layer:

```text
(L_n, K_n) -- round closure --> modify L_n using integrated knowledge --> A_(n+1)
```

`A_(n+1)` then begins a new round by differentiating again into identical local agents.

## Two kinds of closure

BECA contains two related boundaries.

### Local closure
A piece of local information can move upward only after the local process no longer changes it.

```text
changing local information
        -> remains local

local change stops
        -> may enter A_n's integration database
```

Local closure does not require correctness, task completion, high confidence, or a semantic conclusion.

### Round closure
The current recursive round ends when its integrated state no longer changes.

Only then does the system move from knowledge accumulation to **base-layer evolution**.

```text
local agents continue changing
        +
A_n knowledge state continues changing
        -> stay in round n

current round stops changing
        -> modify base layer
        -> form A_(n+1)
        -> start round n+1
```

## Why this is not repeated premature reset

A reset during active change would destroy continuity.

BECA therefore does not repeatedly recreate agents while the current round is still evolving.

Continuity is preserved **inside the round**:

- local agents retain their histories;
- relationships and environmental adaptation can accumulate;
- peer communication can change later experience;
- the integration database can continue receiving newly closed information.

A new differentiation occurs only after the current round has stopped changing and its knowledge has been used to create a new base agent.

The next round is therefore not a simple restart of the old system. It begins from an **evolved base layer**.

## Architecture

```text
                    A_n
          base layer L_n + knowledge K_n
                     |
                 differentiate
           +---------+---------+
           |         |         |
           v         v         v
          B_n       C_n       D_n
           |         |         |
        different local experience
           |<------ communication ------>|
           |         |         |
        dynamic local evolution
           |         |         |
       local change eventually stops
           \         |         /
            \        |        /
             closed information
                    |
                    v
             A_n integration database
                    |
          knowledge continues changing?
             /                 \
           yes                 no
            |                   |
       remain in round n        v
                        round closure
                              |
                              v
                     modify base layer L_n
                              |
                              v
                           A_(n+1)
                              |
                         differentiate
                              |
                          next round
```

## Core principles

1. **Same-state differentiation** — each round begins by differentiating the current base agent into identical local agents.
2. **Situated evolution** — the local agents become different through different experiences, not different initialization.
3. **Communication is allowed** — peer communication is part of local evolution.
4. **Changing information stays local** — information becomes eligible for upward integration only after its relevant local change stops.
5. **A acts as an integration database during the round** — closed information is accumulated and reorganized before base evolution.
6. **Round transition is triggered by cessation of change** — not by a predefined knowledge quota or task target.
7. **Base evolution happens between rounds** — integrated knowledge is used to modify the underlying base layer and create `A_(n+1)`.
8. **Recursion** — `A_(n+1)` repeats the same process by differentiating again.

## Knowledge update versus base-layer update

These are different operations.

During a round:

```text
K_n changes
L_n remains the current base layer
```

At round closure:

```text
integrated K_n
    -> used to modify L_n
    -> produces new base agent A_(n+1)
```

This is why BECA is more than a shared-memory architecture. The system does not only accumulate knowledge; accumulated knowledge can eventually alter the structure from which the next recursive round begins.

## What BECA is not

BECA is not a theory of isolated agents.

BECA is not a system in which every local state is immediately fused upward.

BECA is not a system that waits for a predefined knowledge maximum before evolving.

BECA is not a system that repeatedly resets active local processes.

BECA does not require permanent source tracking once closed information has entered the integration process.

## Current theoretical sequence

> **A_n -> identical differentiation -> situated local evolution -> local closure -> knowledge integration in A_n -> cessation of round-level change -> base-layer modification -> A_(n+1) -> identical differentiation -> ...**

This recursive sequence is the current core of BECA.

## Repository map

- [`SPEC.md`](SPEC.md) — terminology and minimum architectural invariants
- [`ARCHITECTURE.md`](ARCHITECTURE.md) — detailed recursive system structure
- [`TESTABLE_PREDICTIONS.md`](TESTABLE_PREDICTIONS.md) — observations that could support, narrow, or contradict the theory
- [`PRIOR_ART.md`](PRIOR_ART.md) — adjacent architectures and candidate distinctions
- [`CONTRIBUTING.md`](CONTRIBUTING.md) — how to critique or extend the proposal
- [`paper/BECA_v0.1.md`](paper/BECA_v0.1.md) — conceptual paper draft
- [`CITATION.cff`](CITATION.cff) — citation metadata

## Open questions

The current theory intentionally leaves several mechanisms open:

- how local cessation of change is detected;
- how round-level cessation of change is detected;
- exactly which closed information is retained in `K_n`;
- how conflicting closed information is integrated;
- how integrated knowledge modifies the base layer;
- which parts of the base layer are mutable between rounds;
- whether the integrator itself requires additional constraints to avoid introducing distortion.

## Invitation

This is a theory proposal, not a claim of completed validation.

Equivalent prior architectures, counterexamples, formalizations, implementations, and negative results are welcome.
