# Provenance Discontinuity and Historical Reconstruction

This document adds a provenance and reversal rule to **Perfect Recursion / Bidirectional Evolutionary Recursion (BER)**.

## 1. Core distinction

Perfect Recursion distinguishes four operations or relations that must not be conflated:

1. **theoretical reconstruction** — infer or model an earlier state from present evidence;
2. **historical replay / regeneration** — generate a historically reconstructed condition as a new recursive branch and let that branch execute forward;
3. **true reversal** — return the active system itself to an earlier state by giving up the present state that came after it;
4. **subject continuity through transformation** — the same subject becomes a later state while retaining historical continuity.

The first is descriptive. The second is generative and therefore remains part of forward recursion. The third, if physically meaningful at all, is not branch creation: it would require the current state itself to be returned. The fourth is neither replay nor reversal: it is ordinary identity-preserving continuation of one subject through changing states.

Compactly:

> **Theory may be reconstructed backward. A historical condition may be regenerated forward as new recursion. A subject may become a later state while remaining the same subject. True reversal would require the present state itself to be returned.**

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

## 3. Disappearance is not the only reason an origin is not separately present

One possibility is provenance discontinuity: once a higher-level recursive structure becomes sufficiently autonomous, the lower structure that generated it may cease, disappear, or become inaccessible without forcing the higher level to stop.

```text
L0 -> L1 -> H1

later:
L0 disappears
L1 disappears
H1 -> H2 -> H3 -> ...
```

The lower layer is then a historical generating condition rather than a permanent runtime dependency.

But Perfect Recursion now distinguishes a second possibility: an earlier state may no longer exist as a separate present object because the same subject transformed into a later state.

```text
a0 -> a1 -> a2 -> ... -> a_n
```

In this case, `a0` is no longer current, but the subject that occupied `a0` may still be present as `a_n`.

Therefore:

> **earlier state no longer present != originating subject disappeared**

and:

> **an origin may persist through transformation rather than through preservation of its original state.**

This distinction prevents a category error in which the system searches for the original state as though it should survive as a separate object beside its own later state.

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

At current state `C`, the system reconstructs a historical condition and uses it to generate a new recursive branch:

```text
C
└-> R0' -> R1' -> R2' -> C'
```

`R0'` is not the original `R0` and is not a return to it. It is a new present event whose generation occurs after `C`.

The new branch has its own recursive identity. Its state, history, memory, and causal continuity belong to that branch. Historical structure may supply a template, constraint, or initial condition, but this does not make the new branch a direct continuation of the earlier historical event.

Therefore:

> **replay is branch generation, not return.**

The important correction is that this new branch is not a paradoxical conflict with recursion. It is itself a normal recursive event:

```text
R -> R'
```

where `R'` uses reconstructed historical structure as part of its generative condition.

If a second history can be generated while the first remains present, then the operation has created another recursive branch rather than reversed the first history.

Replay therefore does not require a separate defensive "isolation" rule in order to become a distinct branch. Branch distinction follows from recursive identity itself.

## 6. Subject continuity is not replay

Suppose one subject passes through:

```text
a0 -> a1 -> a2
```

At `a2`, the subject's earlier state `a0` belongs to its history. The current subject does not need to regenerate `a0` in order to remain continuous with it.

The relation is:

```text
subject(a0) = subject(a1) = subject(a2)
state(a0) != state(a1) != state(a2)
```

Memory of earlier states may be retained in compressed, partial, or reorganized form along the subject sequence.

If `a2` instead generates:

```text
a2
└-> a0' -> a1' -> a2'
```

then `a0'` begins a new recursive branch. It is not the historical `a0` restored and does not become the original subject's past.

Therefore:

> **having been an earlier state and regenerating an earlier state are different operations.**

See [`INDIVIDUAL_CONTINUITY.md`](INDIVIDUAL_CONTINUITY.md).

## 7. True reversal means returning the present state

A true reversal is conceptually different from replay and from ordinary subject continuity.

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

## 8. Internal observability criterion

A complete reversal has a strict observational consequence.

If, after an alleged reversal to `S1`, the reversed system still internally retains information that depends on having passed through `S2` or `S3`, then the system has not completely returned to the original `S1`.

That information makes the resulting state different:

```text
S1' = S1 + retained later-state information
```

Hence:

> **If pre-reversal state information remains internally observable after the operation, the operation was not a complete reversal.**

This makes complete reversal internally self-erasing with respect to the reversed interval: the evidence that the later state was reached must itself be among the returned state if that evidence belongs to the reversed system.

## 9. External-observer boundary

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

## 10. Replay branches preserve recursive identity

If replay generates:

```text
active branch C
+
replayed branch C'
```

then `C` and `C'` are coexisting recursive structures, not two copies of one active state.

Their branch-local state, memory, history, and causal continuity remain distinct. The existence of a historical relation between them does not collapse that distinction into direct causal continuity or shared identity.

The branches may later be compared, interact, exchange information, or participate in a higher-level integration if the architecture defines such a relation. Any such event is a later recursive operation; it is not an automatic consequence of replay and does not retroactively turn replay into reversal.

A direct identity merge, if an implementation defines one, can introduce practical conflicts such as:

- duplicated identities;
- incompatible object versions;
- obsolete rules reactivated as current rules;
- contradictory causal dependencies;
- duplicated downstream effects.

These are **interaction or merge problems between distinct recursive structures**, not the reason the branches are distinct in the first place.

A true reversal, by definition, does not preserve the unreversed active branch alongside the returned state.

## 11. Historical reconstruction and branch interaction rule

Historical reconstruction should be observational by default.

A general pattern is:

```text
present recursive state C
   ↓
reconstruct historical model H*
   ↓
(optional derived recursive branch R')
   ↓
branch-local outcomes / constraints / evidence K
   ↓
higher-level comparison or validation
   ↓
possible later integration into ongoing recursion
```

The system may integrate **validated conclusions about history** without mistaking regenerated history for literal return to the original past.

If information from a replayed branch later influences another branch or a higher-level structure, that influence is a new recursive relation. It does not erase the replayed branch's provenance or make its memory and state part of the original historical event.

## 12. Provenance is optional runtime information

A conforming Perfect Recursion system MAY preserve detailed provenance, but it MUST NOT require complete provenance replay as a condition for continued recursion.

Provenance may be:

- fully preserved;
- compressed;
- partially preserved;
- externally archived;
- reconstructable only probabilistically;
- irrecoverably lost.

The recursive process can still continue if the current structure retains enough information and capability to generate the next stage.

Subject continuity does not require lossless provenance either. A subject may remain continuous while detailed historical memory becomes partial or compressed, provided the adopted subject-identity relation remains satisfied.

## 13. Relationship to information loss

This mechanism extends the existing local-loss rule.

Previously:

> local data may disappear while other sources or later recurrence preserve the relevant relation.

Now additionally:

> entire portions of the generating provenance may become inaccessible while their compressed structural consequences remain active.

Loss of provenance therefore does not necessarily imply loss of recursive function.

## 14. Relationship to stage-truth

A current stage-truth may be a compression of historical processes whose full paths are no longer accessible.

That does not make the current model originless. It means its provenance may have been recursively summarized into the present structure.

This creates a distinction between:

- **historical origin** — the process or earlier subject-state from which the current structure emerged;
- **accessible origin** — the earliest source recoverable by the current system;
- **runtime dependency** — the source that must still exist for the current structure to continue;
- **continuing subject** — where applicable, the same subject that has transformed through successive states.

These need not be identical.

## 15. Consequence for origin questions

If provenance discontinuity occurs repeatedly, a later system may be able to infer that it has a generating history while being unable to recover the first concrete origin.

Therefore:

```text
oldest recoverable origin
!= necessarily
absolute first origin
```

But there is now an additional identity case:

```text
original state a0
-> a1
-> a2
-> ...
-> current state a_n
```

Searching for `a0` as a separate current object can fail even if the subject that was in state `a0` remains continuously present as `a_n`.

Therefore inability to recover an origin must be classified before it is interpreted:

```text
A. source disappeared / became inaccessible
B. source persists only through compressed provenance
C. originating subject persisted by becoming the current subject
D. source is genuinely unknown
```

The theory does not conclude from any one of these cases that an absolute first origin exists or does not exist.

## 16. Additional invariants

### PR-P1 — Provenance continuity is optional
Recursive continuation does not require continuous access to the entire generating lineage.

### PR-P2 — Generator persistence is optional after autonomy
A higher recursive structure may continue after the lower structure that generated it disappears, provided the higher structure has become sufficiently autonomous.

### PR-P3 — Historical reconstruction is descriptive by default
Reconstruction of earlier states is a present model of history, not literal recovery of the original causal event.

### PR-P4 — Historical replay creates a recursive branch
Executing a historically reconstructed condition while the current state remains produces a new recursive branch. That branch has its own state, history, memory, and causal continuity and is itself part of ongoing recursion.

### PR-P5 — Branch creation is not true reversal
If the original current branch remains present while a historically reconstructed state is generated, the operation is replay/regeneration rather than true reversal.

### PR-P6 — True reversal requires return of the current state
A complete reversal to an earlier state requires all reversed-system state that depends on the later interval to be returned, including internal evidence of that interval.

### PR-P7 — Complete reversal is internally non-retentive
If later-state information remains internally observable after the claimed reversal, the result is not identical to the earlier state and the reversal is incomplete.

### PR-P8 — Replay branches preserve recursive identity
A replayed branch is not the same recursive state as the branch from which replay was initiated. Its state, memory, history, and causal continuity belong to the new branch. Any later interaction or higher-level integration is a new recursive relation and MUST preserve the provenance distinction rather than be treated as literal continuation of the original historical event.

### PR-P9 — Complete historical replay is not a runtime requirement
Continued recursion must not depend on replaying the entire generating history at every stage.

### PR-P10 — Earlier state and originating subject are distinct concepts
An earlier state may cease to be current while the subject that occupied that state remains continuous with the present subject.

### PR-P11 — Origin may persist by becoming the present
Failure to locate an origin as a separate current object MUST NOT by itself be treated as evidence of disappearance when identity-preserving transformation can account for continuity.

## 17. Falsification / narrowing targets

This provenance and reversal extension should be narrowed if a formal model demonstrates that:

1. every higher-level recursive structure necessarily requires all lower generating layers to remain active forever;
2. generation of a historically reconstructed state while preserving the present can restore the original historical causal identity without constituting a new branch;
3. a state can be fully identical to an earlier state while still internally retaining information that exists only because the later state occurred;
4. branch replay and true reversal are formally the same operation under the adopted state definition;
5. recursive continuation necessarily requires full, continuously accessible provenance;
6. identity-preserving subject transformation cannot be distinguished from generation of a new recursive origin under the adopted identity model.

The theory does **not** claim that true global reversal is physically achievable. It only defines what would have to be true for an operation to count as true reversal rather than replay, reset, reconstruction, branch creation, or ordinary subject continuation.

## 18. Compact formulation

> **Perfect Recursion allows provenance discontinuity, but disappearance is not the only reason an earlier origin may no longer be separately present. A system may inherit the structural result of history without continuously carrying or replaying the entire history, and a continuing subject may preserve identity by becoming later states rather than by preserving its original state as a separate object. Theoretical reconstruction models the past. Historical replay generates a new recursive branch with its own state, memory, history, and causal continuity. True reversal, if meaningful, would require the current state itself to be returned. An origin that cannot be found as a separate present object may therefore have disappeared, become inaccessible, been compressed into provenance, or remained continuously present by becoming the current subject.**
