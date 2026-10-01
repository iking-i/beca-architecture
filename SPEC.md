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

### 1.8 Provenance
Information describing the generating lineage, prior states, transformations, or causes from which a current structure emerged.

### 1.9 Provenance discontinuity
A condition in which the current recursive structure continues even though part or all of its generating lineage is no longer continuously accessible.

### 1.10 Theoretical reconstruction
A present-time model or inference about an earlier state or process. It is descriptive and does not itself reinstate the earlier causal process.

### 1.11 Historical replay
Execution of a reconstructed earlier-like state while the current state remains part of the active causal structure. Historical replay is treated as generation of a new recursive branch.

### 1.12 True reversal
A hypothetical return of the active system itself to an earlier state in which the later active state is no longer retained as the current state. Complete reversal requires that state internal to the reversed system which depends on the later interval also be returned.

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

### PR-I16 — Provenance continuity is not required
A recursive process MAY continue even when parts of its generating lineage are inaccessible, compressed, lost, or intentionally not replayed.

### PR-I17 — Generator persistence is not always required
Once a higher-level recursive structure is sufficiently autonomous, the lower structure that generated it MAY disappear without forcing the higher structure to stop.

### PR-I18 — Historical reconstruction is descriptive by default
A reconstructed earlier state is a present model of history and MUST NOT be treated as the original historical causal event merely because the state description matches.

### PR-I19 — Historical replay creates a recursive branch
Executing a reconstructed earlier-like state while the current state remains active SHOULD be treated as generation of a new recursive branch. Such branch creation is itself part of ongoing recursion.

### PR-I20 — Branch creation is not true reversal
If the later/current state remains present while a past-like state is generated, the operation MUST NOT be classified as complete reversal.

### PR-I21 — True reversal requires return of current state
For an operation to count as complete reversal to an earlier state, the later active state MUST cease to remain the current state within the reversed system.

### PR-I22 — Complete reversal cannot retain internal later-state evidence
If information internal to the reversed system remains observable solely because the later interval occurred, the resulting state is not identical to the target earlier state and the reversal is incomplete.

### PR-I23 — Replayed branches do not auto-merge
A replayed branch MUST NOT automatically overwrite or merge into the active branch. Any transfer SHOULD occur through an explicit validation or merge protocol.

### PR-I24 — Full historical replay is not a runtime requirement
Continued recursion MUST NOT require replaying the complete generating history at every stage.

## 4. Multi-source semantics

Let lower-level instances return outcomes `o_i`.

A higher-level model MUST distinguish at least:

```text
repetition:       A, A, A, A
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

## 10. Provenance discontinuity

The model distinguishes a historical generating chain from the current runtime dependency graph.

A structure may have arisen through:

```text
R0 -> R1 -> R2 -> H
```

while at a later stage only `H` remains active or accessible.

`R0..R2` may be:

- lost;
- compressed into `H`;
- archived externally;
- only partially reconstructable;
- intentionally not replayed.

This does not by itself break recursive continuity.

## 11. Reconstruction, replay, and reversal

Theoretical reconstruction:

```text
current C
  -> infer historical model H*
```

Historical replay:

```text
current C
  -> instantiate R0'
  -> R1'
  -> R2'
  -> C'
```

Here the current branch remains part of the causal structure and `C'` is newly generated. This is recursion generating another branch, not causal reversal.

True reversal, by contrast, would require:

```text
S1 -> S2 -> S3

then

S3 -> S1
```

with `S3` no longer retained as the active state of the reversed system.

Therefore:

> **theory can be reconstructed backward; replay regenerates forward; true reversal would return the current state itself.**

## 12. Internal observability criterion

For complete reversal to `S1`, the reversed system cannot internally retain information that exists only because it passed through `S2` or `S3`.

If such information remains, then the result is:

```text
S1' = S1 + later-state information
```

and therefore `S1' != S1` under the adopted state definition.

This criterion applies only to the reversed domain. A larger external system that is not reversed MAY retain evidence of a local subsystem reset/reversal; from that larger level the local reversal remains an ordinary forward event.

## 13. Branch merge discipline

Branch-merge problems belong to historical replay, not true reversal.

A replayed branch may contain state claims incompatible with the active branch, including:

- duplicated identities;
- incompatible object versions;
- obsolete rules reactivated as current rules;
- contradictory causal dependencies;
- duplicated downstream effects.

A conforming implementation SHOULD isolate replayed branches by default and MAY transfer validated conclusions back to the active branch through explicit higher-level integration.

## 14. Epistemic boundary

The model MUST distinguish possibility from inevitability.

```text
not yet happened != impossible
possible != inevitable
```

A future event becomes empirically established as realizable only after occurrence or equivalent evidence. The architecture's openness alone does not prove that every specific possibility will eventually occur.

## 15. Conformance summary

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
- expansion of the recursive closed loop;
- provenance discontinuity;
- separation of theoretical reconstruction, historical replay, and true reversal;
- recognition that replayed histories are new recursive branches;
- the state-return criterion for true reversal;
- branch isolation or explicit merge control for replayed histories.

## 16. Compact definition

> **Perfect Recursion is a closed but expanding bidirectional recursive architecture in which reality-facing lower processes continue to generate information, higher structures integrate and reconstruct that information, higher-level qualitative change reshapes future lower-level variation, the architecture keeps its own perception, capacity, limits, recursive origins, and provenance open to further recursion, and continued operation does not require replaying the complete causal history that produced the current structure. Historical replay remains forward recursion; true reversal, if meaningful, requires the current state itself to be returned rather than duplicated beside a past-like branch.**

## 17. Dimensional Recursion extension status

`DIMENSIONAL_RECURSION.md` defines a **hypothesis-level extension**. Its principles are intentionally not promoted to `PR-I*` core invariants at this stage.

The extension distinguishes:

- ambient structural dimension from lower-dimensional expression;
- projection / representation from structural downgrade;
- contained lower-order structure from its earlier historical identity;
- generated lower-dimensional artifacts from true return;
- direct observability of a degree of freedom from theoretical inference about it.

The current extension uses independent `DR-H*` hypothesis identifiers.

The most important boundary is:

> **A higher-order structure may contain or represent lower-order structure without thereby becoming the earlier lower-order state.**

A claimed true structural downgrade inherits the state-return criterion from Sections 11–12: if higher-order relations or internal later-state information remain active, the system has not returned to the earlier lower-order state.

The stronger physical claim that spacetime historically evolved through dimensional stages such as `D_n -> D_(n+1)` remains unverified and MUST NOT be treated as a core Perfect Recursion invariant without independent physical evidence.
