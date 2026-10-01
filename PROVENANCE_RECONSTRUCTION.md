# Provenance Discontinuity and Historical Reconstruction

This document adds a provenance rule to **Perfect Recursion / Bidirectional Evolutionary Recursion (BER)**.

## 1. Core distinction

Perfect Recursion distinguishes three operations that must not be conflated:

1. **theoretical reconstruction** — infer or model an earlier state from present evidence;
2. **process replay** — instantiate an earlier state and execute its dynamics again;
3. **true reversal** — make the active present system become its own earlier historical state while removing the already-realized causal consequences.

The theory permits the first, treats the second as creation of a new recursive branch, and does not assume the third is a valid operation.

Compactly:

> **Theory can be reconstructed backward; process can only be generated again. A regenerated process belongs to a new branch, not to the original past.**

## 2. Provenance discontinuity

Recursive continuity does not require continuous accessibility of provenance.

A lineage may be:

```text
R0 -> R1 -> R2 -> R3 -> R4
```

while the currently accessible history is only:

```text
? -> R3 -> R4
```

The disappearance, loss, compression, or inaccessibility of `R0..R2` does not imply that `R4` lacks a historical source. It means only that the current system cannot, or need not, continuously access the complete generating chain.

Therefore:

> **source existence != present source accessibility**

and:

> **recursive continuity != provenance continuity**

## 3. Why lower layers may disappear

Once a higher-level recursive structure becomes sufficiently autonomous, the lower structure that generated it may cease, disappear, or become inaccessible without forcing the higher level to stop.

```text
L0 -> L1 -> H1

later:
L0 disappears
L1 disappears
H1 -> H2 -> H3 -> ...
```

The lower layer is then a historical generating condition rather than a permanent runtime dependency.

This generalizes the recursive-origin rule: a generated higher structure can preserve causal consequence without preserving the generator as a continuously active object.

## 4. Historical compression

A higher-level model may preserve the operational consequence of history without preserving the full historical trajectory.

Conceptually:

```text
large historical process H
        ↓ integration / compression
current structure M
        ↓
future recursion continues from M
```

The system need not execute:

```text
M -> reconstruct all of H -> revalidate H -> resume from M
```

on every later operation.

This prevents historical cost from growing into a mandatory runtime burden.

## 5. Why complete process replay is not neutral

Suppose the realized history is:

```text
R0 -> R1 -> R2 -> C
```

At current state `C`, the system attempts to “replay the past” by instantiating an earlier state:

```text
C
└-> R0' -> R1' -> R2' -> C'
```

`R0'` is not the original `R0`. It is a new present event whose initial conditions resemble a reconstructed past state.

Therefore process replay produces a new causal branch:

> **replay is branch creation, not return.**

Even with a perfect state copy, the replay exists at a new causal position and can interact with different surroundings, timing, resources, random events, observations, or higher-level structures.

## 6. Merge conflict between realized and replayed branches

If a replayed branch `C'` is allowed to merge directly into the active branch `C`, the system may face incompatible state claims:

- different versions of the same object;
- incompatible causal dependencies;
- duplicated identities;
- obsolete rules reintroduced as active rules;
- different conclusions generated under different environments;
- duplicated or contradictory downstream effects.

Thus:

```text
realized branch C
+
replayed branch C'
-> non-trivial merge problem
```

The merge is not equivalent to restoring the past. It is an interaction between two present recursive branches.

## 7. Safe historical reconstruction rule

Historical reconstruction should be observational by default.

A safe pattern is:

```text
present state C
   ↓
reconstruct historical model H*
   ↓
(optional isolated simulation branch S)
   ↓
extract conclusions / constraints / evidence K
   ↓
higher-level validation
   ↓
possible integration of K into C
```

The system may integrate **validated conclusions about history** without directly merging the full replayed process into the active branch.

This preserves the distinction between:

- learning from a reconstructed history;
- reactivating a historical process inside the current causal system.

## 8. Provenance is optional runtime information

A conforming Perfect Recursion system MAY preserve detailed provenance, but it MUST NOT require complete provenance replay as a condition for continued recursion.

Provenance may be:

- fully preserved;
- compressed;
- partially preserved;
- externally archived;
- reconstructable only probabilistically;
- irrecoverably lost.

The recursive process can still continue if the current structure retains enough information and capability to generate the next stage.

## 9. Relationship to information loss

This mechanism extends the existing local-loss rule.

Previously:

> local data may disappear while other sources or later recurrence preserve the relevant relation.

Now additionally:

> entire portions of the generating provenance may become inaccessible while their compressed structural consequences remain active.

Loss of provenance therefore does not necessarily imply loss of recursive function.

## 10. Relationship to stage-truth

A current stage-truth may be a compression of historical processes whose full paths are no longer accessible.

That does not make the current model originless. It means its provenance may have been recursively summarized into the present structure.

This creates a distinction between:

- **historical origin** — the process that generated the structure;
- **accessible origin** — the earliest source recoverable by the current system;
- **runtime dependency** — the source that must still exist for the current structure to continue.

These three need not be identical.

## 11. Consequence for origin questions

If provenance discontinuity occurs repeatedly, a later system may be able to infer that it has a generating history while being unable to recover the first concrete origin.

Therefore:

```text
oldest recoverable origin
!= necessarily
absolute first origin
```

The theory does not conclude from this that an absolute first origin exists or does not exist. It concludes only that inability to recover an origin is not equivalent to proof that no earlier generating process existed.

## 12. Additional invariants

### PR-P1 — Provenance continuity is optional
Recursive continuation does not require continuous access to the entire generating lineage.

### PR-P2 — Generator persistence is optional after autonomy
A higher recursive structure may continue after the lower structure that generated it disappears, provided the higher structure has become sufficiently autonomous.

### PR-P3 — Historical reconstruction is descriptive by default
Reconstruction of earlier states is a present model of history, not literal recovery of the original causal event.

### PR-P4 — Process replay creates a new branch
Executing a reconstructed historical state produces a new recursive branch unless a stronger reversal mechanism is separately demonstrated.

### PR-P5 — Replayed branches must not auto-merge
A replayed branch should not automatically write into the active branch. Any transfer should occur through explicit higher-level validation or a defined merge protocol.

### PR-P6 — Complete historical replay is not a runtime requirement
Continued recursion must not depend on replaying the entire generating history at every stage.

## 13. Falsification / narrowing targets

This provenance extension should be narrowed if a formal model demonstrates that:

1. every higher-level recursive structure necessarily requires all lower generating layers to remain active forever;
2. exact process replay can be shown to restore the original historical causal position rather than create a new present branch;
3. merging a replayed branch into the active branch is always lossless and conflict-free by construction;
4. recursive continuation necessarily requires full, continuously accessible provenance.

## 14. Compact formulation

> **Perfect Recursion allows provenance discontinuity. A system may inherit the structural result of history without continuously carrying or replaying the entire history. Theoretical reconstruction can move backward descriptively; process execution moves forward causally. Replaying an earlier state therefore creates a new recursive branch rather than restoring the original past.**
