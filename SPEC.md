# BECA Specification v0.7

This specification defines the current mechanism of **Perfect Recursion / Bidirectional Evolutionary Recursion (BER)**.

## 1. Terms

### 1.1 Lower-level process
A process that continues to operate in direct contact with its local conditions and can produce outcomes relevant to a higher-level model.

### 1.2 Higher-level model
A structure that integrates multiple lower-level outcomes, compares them against validated information, and may reconstruct the generative conditions of future lower-level processes.

### 1.3 Stage-truth
The strongest currently validated model available at a given stage. It is provisional by definition and may later be refined, split, bounded, or embedded in a higher-resolution model.

### 1.4 Quantitative variation
Accumulation, repetition, branching, or diversification across lower-level instances or states.

### 1.5 Qualitative transition
A structural change that alters the model, sensing regime, search space, generative rule, coordination regime, or recursive origin itself.

### 1.6 Recursive origin
A system or process capable of becoming the starting point of its own continuing recursive structure.

### 1.7 Expanding closed loop
A loop in which output becomes part of the conditions for a later input cycle, while the reachable model/capability space can increase across cycles.

## 2. Core recursive rule

```text
persistent lower-level processes
        ↓
continuous outcomes / observations
        ↓
higher-level comparison and integration
        ↓
reconstruction if sufficient validated information requires it
        ↓
changed lower-level conditions / differentiation
        ↓
new lower-level variation
        ↓
repeat
```

The lower level does not stop merely because the higher level exists.

## 3. Core invariants

### PR-I1 — Persistent observation
Lower-level processes MAY continue operating after higher-level integration has formed.

### PR-I2 — Contradiction is admissible
A lower-level outcome MUST NOT be discarded solely because it conflicts with the current higher-level model or is numerically rare.

### PR-I3 — Repetition is not voting
Repeated outcomes MAY support stability, but frequency alone does not define truth.

### PR-I4 — Reconstruction is evidence-gated
Higher-level reconstruction SHOULD occur only when enough validated information exists to justify a structural change.

### PR-I5 — Integration increases resolution
When two outcomes are conditionally compatible, the model SHOULD prefer a higher-resolution conditional structure over winner-take-all elimination when evidence permits.

### PR-I6 — Higher levels can reshape lower levels
A qualitative transition MAY alter the structure, sensing, branching, search, allocation, or coordination of later lower-level processes.

### PR-I7 — Quantity can produce quality
Accumulated lower-level variation MAY produce a qualitative transition.

### PR-I8 — Quality can reshape quantity
A qualitative transition MAY change the quality and distribution of later lower-level variation.

### PR-I9 — Capacity is recursive
Detected limits in storage, computation, communication, sensing, or model complexity MAY become inputs to later reconstruction.

### PR-I10 — Perception is recursive
The current sensing/encoding scheme is not final; evidence that it is insufficient MAY trigger perceptual reconstruction.

### PR-I11 — Local loss is tolerated
Loss of a local observation does NOT imply global loss if other branches, repeated observations, or redundant conclusions can re-establish the relevant relation.

### PR-I12 — Local cessation is not global cessation
A process MAY stop, fail, disappear, or reach a local capability limit while other processes continue.

### PR-I13 — Recursion can generate recursion
An existing recursive process MAY produce a new recursive origin that can continue its own recursion.

### PR-I14 — No built-in final layer
The abstract mechanism does not require a final top, bottom, perceptual scheme, capacity, or model.

### PR-I15 — Closed loop, expanding space
The recursive mechanism MAY close structurally while the reachable/explanatory state space expands across cycles.

## 4. Multi-source semantics

Let lower-level instances return outcomes `o_i`.

A higher-level model MUST distinguish at least:

```text
repetition:      A, A, A, A
novel difference: A, A, A, B
```

The second pattern is not resolved by majority vote alone. The higher level asks whether `B` reveals a missing condition, a new regime, an error, or a new structural distinction.

Example reconstruction:

```text
old model:       M -> A
new evidence:    B under condition Y
new model:       X -> A
                 Y -> B
```

## 5. Quantity-quality recursion

The intended structure is:

```text
Qnt_n -> Qlt_n+1 -> improved/changed Qnt_n+1 -> Qlt_n+2 -> ...
```

where qualitative transitions may alter the generator of later variation rather than merely add more instances of the same type.

## 6. Capacity recursion

A finite implementation has finite resources at every stage.

Perfect Recursion does not deny this. It asserts only that a current resource ceiling can itself become a modeled constraint and therefore a target of reconstruction.

Examples include:

- compression;
- hierarchy;
- distribution;
- additional nodes;
- revised encoding;
- revised scheduling;
- changed sensing;
- changed model decomposition.

## 7. Perceptual recursion

If states `X` and `Y` are initially encoded identically, the system may not distinguish them.

If later effects differ, that downstream difference can reveal insufficiency in the current encoding. A later qualitative transition may introduce a representation that distinguishes `X` from `Y`.

This does not guarantee discovery of every hidden distinction. It guarantees only that perception itself is not protected from recursive revision.

## 8. Local information loss

The model does not require global losslessness.

A local record may disappear while a relation remains recoverable through:

- repeated occurrence;
- parallel observation;
- redundant instances;
- preserved higher-level summaries;
- later rediscovery.

## 9. Recursive-origin creation

For a recursive process `R`:

```text
R continues
AND
R may create R'
```

`R'` counts as a new recursive origin if it can become a source of its own recursively continuing structure rather than merely being the next ordinary state of `R`.

## 10. Epistemic boundary

The model MUST distinguish possibility from inevitability.

```text
not yet happened != impossible
possible != inevitable
```

A future event becomes empirically established as realizable only after occurrence or equivalent evidence. The architecture's openness alone does not prove that every specific possibility will eventually occur.

## 11. Conformance summary

A conforming implementation or formal analogue should preserve:

- persistent lower-level operation;
- upward availability of new outcomes;
- non-majoritarian handling of contradictions;
- evidence-gated reconstruction;
- top-down differentiation;
- quantity-quality reciprocity;
- recursive capacity and perception;
- tolerance of local loss and local cessation;
- possibility of new recursive origins;
- absence of a built-in final layer;
- expansion of the recursive closed loop.

## 12. Compact definition

> **Perfect Recursion is a closed but expanding bidirectional recursive architecture in which reality-facing lower processes continue to generate information, higher structures integrate and reconstruct that information, higher-level qualitative change reshapes future lower-level variation, and the architecture keeps its own perception, capacity, limits, and recursive origins open to further recursion.**
