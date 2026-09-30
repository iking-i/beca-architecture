# BECA — Bidirectional Evolutionary Recursion

> **A theory proposal for a recursive evolutionary system in which variation expands downward, processed information converges upward after change stops, and the improved upper state can generate a new downward expansion.**

**Status:** conceptual architecture / theory proposal  
**Working mechanism name:** **Bidirectional Evolutionary Recursion (BER)**  
**Informal name:** **Perfect Recursion**  
**Not:** a claim of established novelty, a completed implementation, or an experimentally validated theory

## Core idea

BECA is built around one closed recursive loop:

```text
DOWNWARD EXPANSION
        ↓
produce descendants / branches
        ↓
descendants may differ from their predecessors
        ↓
local change continues
        ↓
change stops
        ↑
processed information moves upward
        ↑
upper node changes using lower-level information
        ↑
upper node stops changing
        ↑
its processed state moves to the next higher level
        ↓
the improved state can become the origin of a new downward expansion
        ↓
...
```

The shortest description is:

> **Expand downward. Converge upward. Convergence creates the next expansion.**

Or, in evolutionary language:

> **Possibility is generated downward; evolutionary gain accumulates upward.**

## The recursive unit

Let `X` be any node in the hierarchy.

`X` is not a privileged root. The same rule can apply to every level.

```text
          parent of X
              ↑
              │  X stops changing
              │  and transfers processed information upward
              │
              X
          /   |   \
         /    |    \
       Y1    Y2    Y3 ...
```

A minimal recursive unit has four properties:

1. `X` can generate lower-level descendants or branches.
2. Only some descendants need to reproduce further.
3. Descendants may change relative to their predecessors.
4. When a node stops changing, it transfers processed information upward.

The parent uses incoming information to continue changing itself. When the parent also stops changing, the same transfer rule applies again at the next level.

## Two recursive directions

### Downward recursion — expansion

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

Downward recursion creates new branches, descendants, local histories, and possible variation.

### Upward recursion — convergence

```text
...
D
↑
C
↑
B
↑
A
↑
...
```

Upward recursion begins only when the relevant node has stopped changing.

The node transfers its processed information to its parent. The parent incorporates information from lower levels and continues changing until it too reaches cessation of change.

## The key boundary: cessation of change

The central transition is not death, task completion, correctness, confidence, or a predefined number of iterations.

It is simply:

```text
still changing
    -> remain at the current level

stops changing
    -> processed information becomes eligible to move upward
```

A state can be incomplete, wrong, contradictory, or limited and still satisfy this boundary if the process that owns it no longer changes it.

## Why this is more than ordinary generational evolution

Conventional evolutionary descriptions usually emphasize forward inheritance:

```text
parent -> offspring -> later offspring -> ...
```

In BECA, descendants also become information sources for the levels above them:

```text
parent
  ↓
descendants generate variation
  ↓
descendants stop changing
  ↑
processed information returns upward
  ↑
parent changes
```

The parent is therefore not merely replaced by descendants. It can itself be improved by the stabilized information produced below it.

## Why this is more than a fold/unfold pair

Structured recursion already contains notions analogous to **unfolding** and **folding**.

BECA's candidate distinction is not merely that both directions exist. It is the recursive evolutionary coupling between them:

```text
unfold / expand
    -> local evolution
    -> cessation of change
    -> upward convergence
    -> upper-level self-modification
    -> renewed downward expansion
```

The result of upward convergence changes the state that performs the next downward expansion.

## Self-similarity

The mechanism is recursive because the same rule applies again at every level:

```text
receive processed information from below
        ↓
continue changing
        ↓
stop changing
        ↓
transfer processed information upward
```

A node may simultaneously be:

- the upper layer of its descendants;
- the lower layer of its parent;
- a receiver of converged information;
- a changing processor;
- a future sender when its own change stops.

There is therefore no theoretically privileged final center inside the mechanism.

## Renewal

Upward convergence is not the end of the process.

A state formed or improved through convergence may generate another downward expansion:

```text
expansion
   ↓
variation
   ↓
cessation
   ↑
convergence
   ↑
improved state
   ↓
new expansion
   ↓
...
```

This gives the architecture its closed bidirectional recursion.

## Minimal invariants

A system is minimally BECA-like if:

1. it supports recursive downward generation of lower-level processes or descendants;
2. descendants may change relative to their predecessors;
3. not every descendant is required to continue the lineage;
4. information remains owned by a changing process while that process is still changing;
5. cessation of change is the boundary for upward transfer;
6. transferred information has already been processed by the lower-level process;
7. an upper node may change itself using information transferred from below;
8. when the upper node itself stops changing, the same upward-transfer rule applies again;
9. a converged or improved upper state may become the source of a new downward expansion.

## What remains intentionally undefined

The core theory does not yet prescribe:

- how many descendants a node produces;
- what determines which descendants reproduce;
- how descendants differ from predecessors;
- the exact representation of processed information;
- how a node combines conflicting incoming information;
- how cessation of change is detected;
- how far upward or downward the recursion can extend;
- whether any physical implementation can approximate an unbounded hierarchy.

These are implementation or formalization questions, not part of the minimum recursive mechanism.

## Novelty status

**Unverified architectural originality.**

Many neighboring ideas already exist: evolutionary algorithms, cultural algorithms, hierarchical evolutionary systems, catamorphisms/folds, anamorphisms/unfolds, hylomorphisms, metamorphisms, hierarchical aggregation, and recursive self-improvement.

The candidate contribution to investigate is narrower:

> **a self-similar evolutionary recursion in which downward expansion produces changing descendants, cessation of change triggers processed-information transfer upward, each upper node may itself change from that information and later transfer upward by the same rule, and an upward-converged state can initiate a new downward expansion.**

No claim of being the first equivalent architecture should be made until systematic prior-art review is complete.

## Repository map

- [`BIDIRECTIONAL_RECURSION.md`](BIDIRECTIONAL_RECURSION.md) — minimal definition of the current core mechanism
- [`SPEC.md`](SPEC.md) — terminology and invariants
- [`ARCHITECTURE.md`](ARCHITECTURE.md) — structural explanation and diagrams
- [`TESTABLE_PREDICTIONS.md`](TESTABLE_PREDICTIONS.md) — observations that could support, narrow, or contradict the theory
- [`PRIOR_ART.md`](PRIOR_ART.md) — adjacent ideas and the current novelty boundary
- [`paper/BECA_v0.1.md`](paper/BECA_v0.1.md) — conceptual paper draft
- [`CONTRIBUTING.md`](CONTRIBUTING.md) — how to critique or extend the proposal
- [`CITATION.cff`](CITATION.cff) — citation metadata

## Core sequence

> **downward expansion -> variation -> local change -> cessation of change -> upward transfer -> upper-level change -> upper-level cessation -> further upward transfer -> renewed downward expansion -> ...**
