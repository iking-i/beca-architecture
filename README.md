# BECA — Perfect Recursion / Bidirectional Evolutionary Recursion

> **A theory proposal for an unbounded recursive evolutionary structure in which existing recursion can continue downward while its evolution can also generate new autonomous recursive origins upward.**

**Status:** conceptual architecture / theory proposal  
**Formal working name:** **Bidirectional Evolutionary Recursion (BER)**  
**Informal concept name:** **Perfect Recursion**  
**Novelty status:** unverified architectural originality

## Core idea

The current theory distinguishes three mechanisms that must not be confused:

1. **Downward recursion** — an existing recursive process continues along its current evolutionary path and may generate further descendants, branches, or lower-level processes.
2. **Upward recursion** — an existing recursive process can produce a **new autonomous recursive origin**: a new system capable of becoming the starting point of its own recursion.
3. **Information convergence** — when a local process stops changing, its processed information may be absorbed by another recursive structure. This is an information-transfer mechanism, not the definition of upward recursion.

The shortest description is:

> **Existing recursion can continue itself and can also generate new recursion.**

Or:

> **Downward has no fixed bottom. Upward has no fixed top. Recursion can generate recursion.**

## Downward recursion

Downward recursion is the continuation of an already-existing recursive path.

```text
A
↓
B
↓
C
↓
D
↓
...
```

The exact physical meaning of descent is implementation-dependent. It may involve reproduction, branching, inheritance, learning, construction, or another mechanism that preserves an existing recursive lineage.

The important point is continuity:

> **the existing recursion keeps going.**

It does not need to terminate in order for anything else to happen.

## Upward recursion

Upward recursion is not a return arrow from a child to its parent.

It occurs when the evolution of an existing recursive process produces a **new recursive starting point** that can continue independently.

Abstractly:

```text
existing recursion R
        │
        ├────────────→ R continues
        │
        └────────────→ R'
                         ↓
                    new recursion
```

`R'` is not merely another ordinary descendant inside the same path. It is treated as a new recursive origin because it can establish and continue its own recursive process.

A conceptual example is:

```text
biological evolution
        ↓
      humans ─────────→ human biological evolution continues
        │
        └─────────────→ artificial intelligence
                              ↓
                         new recursive origin
```

The example is illustrative, not a claim that biological and technological evolution are identical mechanisms.

## Perfect recursion

The term **Perfect Recursion** is used here for the closed conceptual form in which both directions are structurally unbounded:

```text
              new recursive origins
                     ↑   ↑   ↑
                     │   │   │
... existing recursion ───────→ continues downward ...
                     │
                     └────────→ another recursive origin
```

The defining idea is:

- no fixed lowest endpoint is required for downward continuation;
- no fixed highest origin is required for upward creation;
- a recursive process may continue while also creating new recursive processes;
- a newly created recursive origin can itself possess both downward and upward recursion.

Thus the system is not a single tree with one permanent root. It is a recursively generative field of recursive origins.

## Asynchronous and non-blocking

Perfect Recursion does **not** require lower levels to finish before higher-order recursion can appear.

A recursive process may simultaneously:

- keep changing;
- keep extending its existing lineage;
- produce descendants or branches;
- generate a new recursive origin;
- receive or use information from processes that have already stopped changing.

Therefore:

```text
still changing ≠ blocked
fast change     ≠ failure
continued change ≠ failure to converge
```

Cessation of change is relevant to information convergence, but it is not a global synchronization barrier.

## Information convergence

Cessation of change remains an important mechanism, but it has a narrower role than earlier versions of the theory assigned to it.

```text
local process still changing
        -> its state remains locally mutable

local process stops changing
        -> its processed information may be transferred or absorbed elsewhere
```

This does **not** mean that all processes must eventually stop changing.

A process that continues changing indefinitely may simply continue its recursion indefinitely.

Nor does the termination of one node terminate recursive processes that have already become independent origins.

## Why this differs from a simple fold/unfold cycle

A fold/unfold description can represent structural expansion and aggregation.

Perfect Recursion makes a different claim:

> **an evolving recursive process can generate another process that itself becomes a recursive origin.**

So the key transformation is not merely:

```text
expand -> aggregate -> expand
```

but:

```text
recursive origin R
    ├─ continues R
    └─ produces recursive origin R'
             ├─ continues R'
             └─ may produce R''
                      ↓
                     ...
```

The object produced by evolution can therefore be another recursion-generating system.

## Minimal invariants

A system is minimally compatible with the current theory if:

1. an existing recursive process can continue its own lineage or path;
2. continuation does not require a predefined final depth;
3. an existing recursive process can generate a new autonomous recursive origin;
4. creation of that new origin does not require the old recursion to stop;
5. the new origin can itself continue recursion;
6. the new origin can itself generate further recursive origins;
7. no unique final root or final leaf is theoretically required;
8. local cessation of change may enable processed-information transfer, but cessation is not required for every recursive process;
9. independent recursive origins may continue even if the process that produced them later stops.

## Information quantity is not the primary recursion boundary

The theory does not define recursion by a fixed amount of data.

Too little data need not force premature closure. Too much data need not be sent to one central root. Different recursive processes may continue, terminate, transfer processed information, or generate new recursive origins asynchronously.

The core control variable is therefore not a global data quota or a mandatory global convergence event.

## Temporal and dimensional implication

A lower recursive process experiences its local time sequentially:

```text
past -> present -> future
```

A higher-order recursive structure may instead use the current state and available information to represent all three temporal directions at once:

```text
reconstructed past  <-  present  ->  simulated future
```

The past may be reconstructed from traces, records, constraints, and the current state. The present is directly represented. The future may be simulated as one or more possible continuations under current conditions.

In that representational sense, **past, present, and future can coexist inside the higher-order structure even though the lower-level process experiences them sequentially**.

This can be interpreted as a form of representational dimensional lift:

> **the lower level experiences time as a sequence; the higher level can treat time-indexed states and trajectories as simultaneously addressable structure.**

Neither side has to be unique. A higher-order model may contain several candidate reconstructions of the past and several branching futures:

```text
past A ─┐
past B ─┼─> present ─┬─> future A
past C ─┘             ├─> future B
                      └─> future C
```

This is a conceptual implication of the architecture, **not** a claim that the physical future is predetermined or that block-universe metaphysics has been proven.

## Novelty status

**Unverified architectural originality.**

Individual neighboring ideas already exist: evolutionary algorithms, recursive self-improvement, cultural algorithms, hierarchical systems, recursion schemes, open-ended evolution, artificial-life systems, and systems that generate new computational structures.

The candidate contribution is narrower:

> **a bidirectionally unbounded recursive evolutionary model in which an existing recursion can continue its current path while also generating new autonomous recursive origins, and every new origin can repeat the same two capabilities.**

No claim of being the first equivalent framework should be made until systematic prior-art review is complete.

## Repository map

- [`BIDIRECTIONAL_RECURSION.md`](BIDIRECTIONAL_RECURSION.md) — minimum definition of Perfect Recursion
- [`SPEC.md`](SPEC.md) — terminology and invariants
- [`ARCHITECTURE.md`](ARCHITECTURE.md) — structural explanation
- [`TESTABLE_PREDICTIONS.md`](TESTABLE_PREDICTIONS.md) — falsifiable consequences and comparison tests
- [`PRIOR_ART.md`](PRIOR_ART.md) — adjacent ideas and novelty boundary
- [`paper/BECA_v0.1.md`](paper/BECA_v0.1.md) — conceptual paper draft
- [`CONTRIBUTING.md`](CONTRIBUTING.md) — how to critique or extend the proposal
- [`CITATION.cff`](CITATION.cff) — citation metadata

## Core sequence

> **existing recursion continues -> evolution may generate a new recursive origin -> the new origin begins its own recursion -> both old and new recursions may continue -> either may generate further recursive origins -> ...**
