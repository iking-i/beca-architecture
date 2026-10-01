# BECA — Testable Predictions and Failure Conditions for Perfect Recursion v0.7

This document defines observations and formal results that would support, narrow, or contradict the current architecture.

## 1. Persistent lower-level operation

Prediction: formation of a higher-level model does not require lower-level processes to stop.

Support pattern:

```text
lower A continues --->
lower B continues --->  higher model exists
lower C continues --->
```

If higher-level formation necessarily terminates or replaces all lower-level processes, PR-I1 must be narrowed.

## 2. Contradictory outcomes remain informative

Prediction: rare or contradictory lower-level outcomes can force higher-resolution reconstruction rather than being discarded by majority selection.

Test:

- create many lower instances producing `A`;
- introduce a reproducible condition producing `B`;
- compare majority-vote aggregation against conditional model reconstruction.

A conforming system should preserve `B` when evidence shows it reflects a real condition.

## 3. Higher-level reconstruction changes later lower-level quality

Prediction: a qualitative transition at the higher level can alter the structure or capability of later lower-level variation.

A minimal experiment should compare:

```text
quantity only:
more instances of same generator

vs.

quantity -> higher reconstruction -> changed generator -> new quantity
```

If higher-level change never affects the quality or structure of later lower processes, the bidirectional claim is weakened.

## 4. Capacity can become a recursive target

Prediction: when a resource limit becomes behaviorally relevant, a conforming system can represent that limit and alter its own organization in response.

Candidate tests:

- fixed buffer -> hierarchical compression;
- fixed compute -> task decomposition;
- fixed communication -> local summarization;
- fixed representation -> new encoding.

If capacity must remain permanently external and unmodifiable in every formalization, the current strong form must be narrowed.

## 5. Perception can become a recursive target

Prediction: if two real conditions are initially encoded identically but later produce detectably different effects, the system can in principle revise its perceptual/representational scheme.

If the sensing vocabulary is permanently fixed and can never become an object of reconstruction, the strong Perfect Recursion definition is not satisfied.

## 6. Local information loss need not be global loss

Prediction: some local observations can disappear without permanently eliminating a relation from the system, provided repeated or distributed sources can reproduce it.

Test distributed redundancy and repeated observation against a single-source baseline.

The theory does **not** predict zero information loss.

## 7. Local cessation need not terminate the whole

Prediction: one branch can stop, fail, disappear, or reach a local limit while other branches and higher recursive structures continue.

If every local cessation necessarily collapses the entire architecture, the current distributed interpretation is wrong.

## 8. Recursion can generate recursion

Prediction: an existing recursive process can produce a new recursion-capable origin without the original recursive process necessarily stopping.

```text
R continues --->
   \
    -> R' continues --->
```

If every candidate `R'` is only the next state of `R` and cannot establish its own continuing recursive structure, the new-origin claim must be narrowed.

## 9. The loop can expand

Prediction: repeated cycles can enlarge the model/capability/state space rather than merely revisit a fixed finite set of states.

This should be tested against:

- fixed-state feedback controllers;
- fixed-grammar recursive systems;
- systems capable of adding representational dimensions, generative rules, or recursive origins.

## 10. Stage-truth should increase resolution rather than merely replace conclusions

Where evidence supports conditional distinctions, later models should be able to preserve earlier locally valid relations inside a more precise model.

Example:

```text
M0: A

new evidence

M1:
X -> A
Y -> B
```

A system that only flips between `A` and `B` without representing conditions is a weaker architecture.

## 11. Boundary: unrealized possibilities

The theory explicitly does **not** predict that every structurally possible event will inevitably occur.

Therefore the following is not a falsification:

> A particular possible `X` has not occurred yet.

The theory can be challenged only by a stronger result, for example a proof that the architecture necessarily contains an immutable final ceiling contradicting its own invariants.

## 12. Strong counterexample targets

The current strong form should be narrowed if formal analysis establishes any of the following as logically unavoidable:

1. a higher level can exist only by terminating the lower level;
2. contradictory lower outcomes must be discarded by construction;
3. higher-level change can never alter future lower-level generative quality;
4. perception must be permanently fixed outside the recursive structure;
5. capacity must be permanently fixed outside the recursive structure;
6. local loss necessarily implies global irrecoverable loss;
7. local cessation necessarily terminates all recursion;
8. new recursive origins are formally impossible and always reducible to ordinary lineage continuation;
9. the model space must be fixed and cannot expand;
10. a unique final top or bottom is logically required.

## 13. Falsifiability discipline

Perfect Recursion should not protect itself by relabeling every counterexample as “another recursion.”

For each implementation or formalization, the recursive variables and reconstruction rules must be specified in advance sufficiently to distinguish:

- observation from post-hoc reinterpretation;
- model expansion from arbitrary redefinition;
- local failure from genuine architectural contradiction.

## 14. Current status

The theory is currently a conceptual architecture with testable structural claims, not an experimentally established universal law.

Its strongest unresolved empirical/formal question is whether one mechanism can realize all v0.7 invariants without hidden fixed assumptions that effectively place perception, capacity, or reconstruction outside the recursion.

## 15. Provenance discontinuity test

Prediction: a higher-level recursive structure can continue after part of its generating provenance becomes inaccessible, provided the current structure retains sufficient recursive capability.

Minimal test:

```text
L0 -> L1 -> H
```

1. construct `H` from `L0/L1`;
2. remove runtime access to `L0/L1`;
3. test whether `H` can continue generating valid later states.

If every higher-level structure necessarily requires the complete lower generating chain to remain active and accessible forever, the provenance-discontinuity extension must be narrowed.

## 16. Reconstruction-versus-replay test

Prediction: reconstructing an earlier state description and executing it in the present creates a new causal branch rather than restoring the original historical event.

Test:

```text
original: R0 -> R1 -> R2 -> C
replay:   C -> R0' -> R1' -> R2' -> C'
```

Compare `C'` with the realized `C` under controlled and perturbed current conditions.

The test should distinguish:

- state equivalence;
- causal identity;
- environmental context;
- downstream divergence.

A result showing that exact state reconstruction automatically restores the original causal position, with no new branch semantics required, would directly challenge PR-I19.

## 17. Replay-merge conflict test

Prediction: direct merging of a replayed branch into an active branch is not generically neutral.

Construct two branches with shared ancestry but divergent later state. Attempt direct merge and measure:

- identity collisions;
- incompatible object versions;
- causal inconsistencies;
- duplicate effects;
- rule conflicts;
- information overwrite.

Compare against an isolated-replay protocol in which only validated conclusions are integrated through the higher level.

If direct full-state replay merge is always lossless and conflict-free by construction across the target class of systems, PR-I20 should be narrowed.

## 18. Historical-load test

Prediction: requiring full provenance replay at every stage creates growing runtime cost that is unnecessary when historical results are compressed into current structure.

Compare:

```text
A. full-history replay before each new step
B. compressed-current-state continuation
```

Measure compute, storage, latency, and conflict frequency as history length grows.

The model predicts that recursive continuation does not require architecture A as a universal condition.
