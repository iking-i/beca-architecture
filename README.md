# BECA — Bounded Evolutionary Commit Architecture

> A conceptual architecture for multi-agent knowledge systems in which **dynamic cognition stays inside independent agent boundaries, and only stabilized conclusions are committed for cross-agent integration**.

**Status:** v0.1 conceptual specification — open for critique, implementation, and falsification.

## Why BECA?

Many distributed and multi-agent systems exchange intermediate states while those states are still changing. This can be useful, but it also creates a class of problems: provisional beliefs leak across boundaries, stale versions are fused with newer ones, noise propagates, and global state may be repeatedly rewritten by local processes that have not yet converged.

BECA explores a different rule:

> **Do not fuse dynamic information across agent boundaries. Let each agent evolve information locally. Commit only a stabilized result. Integrate committed results at a higher layer.**

The architecture is inspired by a simple distinction:

- **Data** can be collected directly.
- **Experience** is data that has been transformed by a local process over time.
- **Shared knowledge** should be produced from stabilized experience, not from every intermediate mutation that occurred while the experience was still forming.

## Core architecture

```text
                 Shared / parent system M
                          |
                 common initialization
                          |
          +---------------+---------------+
          |               |               |
          v               v               v
      Agent A         Agent B         Agent C
    [boundary]       [boundary]       [boundary]
          |               |               |
     local input      local input      local input
          |               |               |
     V1 -> V2 ->       V1 -> V2 ->       V1 -> V2 ->
     V3 -> ...         V3 -> ...         V3 -> ...
          |               |               |
      Final A         Final B         Final C
          |               |               |
          +------ stable COMMIT -----------+
                          |
                          v
                Second-stage integration
             compare / validate / dedupe /
          resolve conflict / abstract / generalize
                          |
                          v
                    update shared state
```

## Five principles

### 1. Independent boundary
Each agent is an information-processing boundary, not merely a sensor or execution worker. Raw observations, local mistakes, temporary hypotheses, and unfinished reasoning remain local by default.

### 2. Local dynamic evolution
Information is allowed to change freely inside the boundary:

```text
observation -> hypothesis -> contradiction -> correction -> relation -> revised model
```

Change is not treated as corruption. It is part of the process by which experience becomes usable knowledge.

### 3. Stable commit
Intermediate versions are not eligible for higher-level fusion. Cross-boundary transfer happens through an explicit commit step that produces a versioned, immutable conclusion for that processing cycle.

### 4. Second-stage integration
The higher layer does not replay every agent's full internal process. It works on committed outputs from multiple independent sources, performing tasks such as cross-validation, conflict resolution, deduplication, abstraction, confidence adjustment, and generalization.

### 5. Evolution through diversity
Agents sharing a common starting structure are useful because they encounter different environments and develop different results. The system benefits from the **useful delta** produced by independent exploration, rather than from creating identical copies.

## What BECA is not

BECA is **not** a claim that all communication during execution is harmful. Operational messages, coordination signals, and task-level communication may still exist. The proposed restriction concerns information that is intended to become **shared learned knowledge**.

BECA is also not equivalent to simply making every message immutable. The key separation is between:

1. a **mutable local cognitive process**, and
2. an **immutable cross-boundary knowledge commit**.

## Research question

The central hypothesis is:

> Some multi-agent knowledge-integration failures are caused not by insufficient synchronization, but by allowing unfinished local information to participate in global fusion too early.

This repository is intended to make that hypothesis implementable and falsifiable.

## Minimal experiment

A first implementation can compare two systems initialized from the same base model and exposed to heterogeneous local environments:

- **Dynamic-sharing baseline:** agents periodically share intermediate beliefs/updates with the global layer.
- **BECA condition:** agents keep intermediate cognitive state local and submit only results that pass a local stabilization/commit criterion.

Candidate measures include knowledge contamination, stale-version conflict, recovery after local error, global task performance, convergence cost, communication cost, and generalization to new environments.

See [EXPERIMENTS.md](EXPERIMENTS.md) for a concrete test plan.

## Repository map

- [`SPEC.md`](SPEC.md) — normative concepts, invariants, and terminology
- [`ARCHITECTURE.md`](ARCHITECTURE.md) — lifecycle and component model
- [`EXPERIMENTS.md`](EXPERIMENTS.md) — minimal falsification-oriented experiments
- [`PRIOR_ART.md`](PRIOR_ART.md) — adjacent architectures and distinctions
- [`CONTRIBUTING.md`](CONTRIBUTING.md) — how to critique, implement, or test BECA
- [`paper/BECA_v0.1.md`](paper/BECA_v0.1.md) — conceptual paper draft

## Current maturity

BECA v0.1 is a **conceptual architecture**, not a validated algorithm. Several parts remain intentionally open, especially:

- how an agent decides that a conclusion is stable enough to commit;
- whether a commit should contain a conclusion, a compressed model delta, evidence, confidence, or all four;
- how the integration layer should resolve incompatible committed conclusions;
- when already-committed knowledge should be superseded by a later committed version;
- which problem classes benefit from delayed knowledge fusion and which are harmed by it.

These are research questions, not details to hide.

## Invitation

Independent implementations, counterexamples, negative results, and alternative formalizations are welcome. A useful outcome is not only to show where BECA works, but also to identify exactly where its boundary/commit rule fails.

If you build an implementation, please document the stabilization rule, commit payload, integration rule, and comparison baseline so results can be reproduced.
