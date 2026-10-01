# Provenance Discontinuity and Historical Reconstruction

This document adds a provenance and reversal rule to **Perfect Recursion / Bidirectional Evolutionary Recursion (BER)**.

## 1. Core distinction

Perfect Recursion distinguishes three operations that must not be conflated:

1. **theoretical reconstruction** — infer or model an earlier state from present evidence;
2. **historical replay / regeneration** — instantiate an earlier-like state in the present and let it execute again;
3. **true reversal** — return the active system itself to an earlier state by giving up the present state that came after it.

The first is descriptive. The second is generative and therefore remains part of the forward recursion. The third, if physically meaningful at all, is not branch creation: it would require the current state itself to be returned.

Compactly:

> **Theory may be reconstructed backward. A past-like process may be regenerated forward. True reversal would require the present state itself to be returned.**

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

## 5. Historical replay is recursion, not reversal

Suppose the realized history is:

```text
R0 -> R1 -> R2 -> C
```

At current state `C`, the system reconstructs an earlier-like state and executes it:

```text
C
└-> R0' -> R1' -> R2' -> C'
```

`R0'` is a new present event whose state may resemble `R0`, but its creation occurred after `C`.

Therefore:

> **replay is branch creation, not return.**

The important correction is that this new branch is not a paradoxical conflict with recursion. It is itself a normal recursive event:

```text
R -> R'
```

where `R'` happens to use a historical state as its template or initial condition.

If a second history can be created while the first remains present, then the operation has generated another recursive branch rather than reversed the first history.

## 6. True reversal means returning the present state

A true reversal is conceptually different from replay.

If the active system has evolved:

```text
S1 -> S2 -> S3
```

then true reversal to `S1` would require:

```text
S3 -> S1
```

not:

```text
S3 -> S3 + S1'
```

The defining condition is that the later active state is no longer retained as the active state.

This means a complete reversal would have to return not only ordinary object state, but also every part of the reversed system that encodes the later state, including where applicable:

- memory of `S2` and `S3`;
- internal records that `S2` and `S3` occurred;
- observations made only after `S1`;
- causal consequences that belong exclusively to the later state.

Therefore:

> **True reversal does not bring the past forward; it returns the present state backward.**

## 7. Internal observability criterion

A complete reversal has a strict observational consequence.

If, after an alleged reversal to `S1`, the reversed system still internally retains information that depends on having passed through `S2` or `S3`, then the system has not completely returned to the original `S1`.

That information makes the resulting state different:

```text
S1' = S1 + retained later-state information
```

Hence:

> **If pre-reversal state information remains internally observable after the operation, the operation was not a complete reversal.**

This makes complete reversal internally self-erasing with respect to the reversed interval: the evidence that the later state was reached must itself be among the returned state if that evidence belongs to the reversed system.

## 8. External-observer boundary

The internal-observability rule applies to the system whose state is being fully returned.

A larger external system may remain unreversed and observe a subsystem being reset or returned:

```text
external E1 -> E2
             |
             └─ subsystem S3 -> S1
```

From the external level, that local reversal/reset is still an ordinary forward event in the larger recursion.

Therefore the theory distinguishes:

- **complete-system reversal** — no internal later-state evidence can remain inside the fully reversed system;
- **local reversal/reset observed externally** — the external observer remains outside the reversed domain and can retain evidence.

This distinction prevents local reset from being confused with global reversal.

## 9. Branch conflicts belong to replay, not true reversal

Branch conflicts can occur only when multiple branches coexist.

If replay creates:

```text
active branch C
+
replayed branch C'
```

then merging them may be non-trivial because both are present recursive structures.

Possible problems include:

- duplicated identities;
- incompatible object versions;
- obsolete rules reactivated as current rules;
- contradictory causal dependencies;
- duplicated downstream effects.

But these are **replay/merge problems**, not properties of true reversal.

A true reversal, by definition, does not preserve the unreversed active branch alongside the returned state.

## 10. Safe historical reconstruction rule

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

The system may integrate **validated conclusions about history** without mistaking a regenerated history for literal return to the original past.

## 11. Provenance is optional runtime information

A conforming Perfect Recursion system MAY preserve detailed provenance, but it MUST NOT require complete provenance replay as a condition for continued recursion.

Provenance may be:

- fully preserved;
- compressed;
- partially preserved;
- externally archived;
- reconstructable only probabilistically;
- irrecoverably lost.

The recursive process can still continue if the current structure retains enough information and capability to generate the next stage.

## 12. Relationship to information loss

This mechanism extends the existing local-loss rule.

Previously:

> local data may disappear while other sources or later recurrence preserve the relevant relation.

Now additionally:

> entire portions of the generating provenance may become inaccessible while their compressed structural consequences remain active.

Loss of provenance therefore does not necessarily imply loss of recursive function.

## 13. Relationship to stage-truth

A current stage-truth may be a compression of historical processes whose full paths are no longer accessible.

That does not make the current model originless. It means its provenance may have been recursively summarized into the present structure.

This creates a distinction between:

- **historical origin** — the process that generated the structure;
- **accessible origin** — the earliest source recoverable by the current system;
- **runtime dependency** — the source that must still exist for the current structure to continue.

These three need not be identical.

## 14. Consequence for origin questions

If provenance discontinuity occurs repeatedly, a later system may be able to infer that it has a generating history while being unable to recover the first concrete origin.

Therefore:

```text
oldest recoverable origin
!= necessarily
absolute first origin
```

The theory does not conclude from this that an absolute first origin exists or does not exist. It concludes only that inability to recover an origin is not equivalent to proof that no earlier generating process existed.

## 15. Additional invariants

### PR-P1 — Provenance continuity is optional
Recursive continuation does not require continuous access to the entire generating lineage.

### PR-P2 — Generator persistence is optional after autonomy
A higher recursive structure may continue after the lower structure that generated it disappears, provided the higher structure has become sufficiently autonomous.

### PR-P3 — Historical reconstruction is descriptive by default
Reconstruction of earlier states is a present model of history, not literal recovery of the original causal event.

### PR-P4 — Historical replay creates a recursive branch
Executing a reconstructed earlier-like state while the current state remains produces a new recursive branch. That branch is itself part of ongoing recursion.

### PR-P5 — Branch creation is not true reversal
If the original current branch remains present while a past-like state is generated, the operation is replay/regeneration rather than true reversal.

### PR-P6 — True reversal requires return of the current state
A complete reversal to an earlier state requires all reversed-system state that depends on the later interval to be returned, including internal evidence of that interval.

### PR-P7 — Complete reversal is internally non-retentive
If later-state information remains internally observable after the claimed reversal, the result is not identical to the earlier state and the reversal is incomplete.

### PR-P8 — Replay branches must not auto-merge
A replayed branch should not automatically write into the active branch. Any transfer should occur through explicit higher-level validation or a defined merge protocol.

### PR-P9 — Complete historical replay is not a runtime requirement
Continued recursion must not depend on replaying the entire generating history at every stage.

## 16. Falsification / narrowing targets

This provenance and reversal extension should be narrowed if a formal model demonstrates that:

1. every higher-level recursive structure necessarily requires all lower generating layers to remain active forever;
2. generation of a past-like state while preserving the present can restore the original historical causal identity without constituting a new branch;
3. a state can be fully identical to an earlier state while still internally retaining information that exists only because the later state occurred;
4. branch replay and true reversal are formally the same operation under the adopted state definition;
5. recursive continuation necessarily requires full, continuously accessible provenance.

The theory does **not** claim that true global reversal is physically achievable. It only defines what would have to be true for an operation to count as true reversal rather than replay, reset, reconstruction, or branch creation.

## 17. Compact formulation

> **Perfect Recursion allows provenance discontinuity. A system may inherit the structural result of history without continuously carrying or replaying the entire history. Theoretical reconstruction models the past. Historical replay regenerates a past-like process as a new recursive branch and therefore remains part of forward recursion. True reversal, if meaningful, would require the current state itself to be returned, including internal information produced only after the target state. If that later-state information remains, the operation was not complete reversal.**
