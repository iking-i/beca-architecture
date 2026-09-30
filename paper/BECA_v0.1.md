# BECA — Bidirectional Evolutionary Recursion
## Downward Expansion, Cessation-Gated Upward Convergence, and Recursive Renewal

**Draft version:** 0.4  
**Status:** Conceptual architecture / theory proposal

## Abstract

We propose **Bidirectional Evolutionary Recursion (BER)** as the current core mechanism of BECA.

The architecture contains two coupled recursive directions. In the downward direction, a node generates descendants or lower-level processes. Only some descendants need to continue the lineage, and descendants may differ from their predecessors. In the upward direction, a node transfers processed information to its parent only after the relevant local process stops changing. The parent may itself change because of that information. When the parent later stops changing, the same upward-transfer rule applies again at the next level.

Upward convergence is not the terminal stage. A state formed or improved through convergence may become the origin of another downward expansion. The two directions therefore recursively generate one another:

> **downward recursion produces the material for upward recursion; upward recursion produces the state from which later downward recursion can begin.**

The proposal intentionally separates **cessation of change** from correctness, task completion, confidence, death, or a predetermined iteration count. Cessation is treated as an information-boundary condition: while a local state is still changing it remains local; after change stops, processed information becomes eligible for upward transfer.

This paper defines the recursive skeleton, identifies its candidate distinction from adjacent ideas, and leaves implementation details open.

## 1. Introduction

Most evolutionary descriptions emphasize one principal direction:

```text
parent -> descendant -> later descendant -> ...
```

Variation is generated forward through a lineage. Later descendants may differ from predecessors, but the evolutionary description does not normally require stabilized descendant experience to recursively modify higher-level generators.

BECA proposes a different abstract structure.

A recursive hierarchy can contain both:

```text
DOWNWARD
upper node -> descendants -> further descendants -> ...
```

and:

```text
UPWARD
... -> closed lower node -> parent -> higher parent -> ...
```

The important claim is not merely that both directions exist. The claim is that they are **causally coupled**.

Downward expansion generates changing local processes. When one of those processes stops changing, its processed information can move upward. The upper node may then continue changing. When it too stops changing, it becomes a lower node relative to its own parent and applies the same rule again. A state improved through this upward convergence can later generate another downward expansion.

The full loop is:

```text
expand downward
 -> generate variation
 -> local change
 -> cessation of change
 -> processed information moves upward
 -> upper node changes
 -> upper node stops changing
 -> further upward transfer
 -> improved upper state
 -> renewed downward expansion
 -> ...
```

This paper calls that mechanism **Bidirectional Evolutionary Recursion**.

## 2. The recursive node

Let `X` denote any node in the hierarchy.

`X` is not assumed to be a privileged root.

```text
             parent(X)
                 ↑
                 │
                 X
              /  |  \
             /   |   \
           Y1   Y2   Y3 ...
```

Relative to `Y1`, `Y2`, and `Y3`, `X` is an upper node.

Relative to `parent(X)`, `X` is itself a lower node.

This dual role is what allows the same rule to apply recursively at every level.

A minimal node can:

1. generate descendants or lower-level branches;
2. receive processed information from below;
3. continue changing because of that information;
4. stop changing;
5. transfer its processed information upward.

## 3. Downward recursion: expansion

The downward direction creates possibility and variation.

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

A node may generate one or many descendants. Only some descendants need to continue reproducing. Descendants may change relative to predecessors.

The current theory deliberately does not prescribe:

- the number of descendants;
- a reproduction criterion;
- a mutation operator;
- an inheritance rule;
- one mandatory environment;
- one mandatory learning algorithm.

Those are implementation choices.

The minimum requirement is only that lower-level trajectories can be generated recursively and may differ from their predecessors.

## 4. Local change

A node may continue processing and changing locally:

```text
X0 -> X1 -> X2 -> X3 -> ...
```

During this interval, its local information remains mutable.

BECA therefore distinguishes between:

- a state that is still changing; and
- a state owned by a process that has stopped changing.

This distinction is structural rather than semantic.

A changing state is not considered ready for upward convergence merely because it already contains useful information.

## 5. Cessation of change

The central boundary is:

```text
still changing
    -> remain local

stops changing
    -> processed information becomes eligible for upward transfer
```

Cessation of change does **not** mean:

- correct;
- complete;
- optimal;
- high-confidence;
- internally consistent;
- successful at a task;
- biologically dead.

A node may stop changing while still being incomplete or wrong.

The theory only requires that the relevant local process no longer changes the state being transferred.

Death, resource exhaustion, timeout, internal fixation, or an external stop condition may cause cessation in a particular implementation, but none of them defines the abstract rule.

## 6. Upward recursion: convergence

When a lower node stops changing, it transfers processed information upward.

For example:

```text
D stops changing
      ↑
processed information
      ↑
C receives it
```

`C` may change because of that information.

Later:

```text
C stops changing
      ↑
processed information
      ↑
B receives it
```

And again:

```text
B stops changing
      ↑
processed information
      ↑
A receives it
```

Thus:

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

The same transfer boundary is applied recursively at every level.

## 7. Processed information

The upward payload is not defined as a full replay of the lower node's history.

It is **processed information**: information that has already been transformed by the lower process.

An implementation may represent this as:

- selected state;
- compressed state;
- rules;
- relations;
- abstractions;
- learned parameters;
- summaries;
- another structured representation.

The theory does not require one representation.

The important distinction is that upward transfer follows local processing and cessation of change.

## 8. Upper-level evolution

An upper node is not merely an archive.

Information received from lower levels can change the upper node itself:

```text
lower-level cessation
        ↓
processed information
        ↓
upper node changes
```

This is a central part of the evolutionary interpretation.

Variation is produced downward, but stabilized lower-level experience can alter the structures that sit above it.

In compact form:

> **Possibility expands downward; evolutionary gain accumulates upward.**

## 9. Recursive renewal

Upward convergence does not end the process.

Suppose `X` has changed because of lower-level information and eventually reaches a new cessation state `X'`.

`X'` may later generate descendants again:

```text
X
↓
Y1, Y2, Y3 ...
↓
local variation
↑
cessation and upward convergence
↑
X'
↓
new descendants
```

Therefore:

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

This coupling is the core of the proposed bidirectional recursion.

## 10. Why this is recursive

The mechanism is not recursive merely because a tree exists.

It is recursive because the same rule can be applied to a node regardless of its level:

```text
receive from below
 -> continue changing
 -> stop changing
 -> transfer upward
```

That same node can also:

```text
generate descendants
 -> descendants change
 -> descendants stop changing
 -> receive from them
```

Each node may therefore be simultaneously:

- a parent;
- a descendant;
- a generator;
- an integrator;
- a local changing process;
- a future upward contributor.

No theoretically privileged final center is required.

## 11. Why this is more than fold/unfold

Existing recursion theory already contains established ideas analogous to unfolding a recursive structure and folding a recursive structure back into a result.

BECA does not claim that having both directions is itself new.

The candidate distinction is narrower:

```text
unfold / expand
 -> evolutionary local change
 -> cessation-gated upward transfer
 -> upper-node self-modification
 -> recursively repeated convergence
 -> renewed expansion from the modified upper state
```

The state performing the next expansion may therefore be different because of the prior convergence.

## 12. Why this is more than one-way evolution

A one-way lineage can be represented as:

```text
A -> B -> C -> D
```

BECA overlays a recursive return channel:

```text
A
↓ ↑
B
↓ ↑
C
↓ ↑
D
```

The downward direction generates lineage and difference.

The upward direction allows processed lower-level change to alter increasingly higher-level states.

The model is therefore not a simple reversal of evolution. It is a **coupled two-direction evolutionary recursion**.

## 13. Minimal invariants

The current minimum theory contains nine invariants:

1. a node can recursively generate lower-level descendants or branches;
2. descendants may differ from predecessors;
3. only some descendants need continue the lineage;
4. changing information remains local while the owning process is still changing;
5. cessation of change is the boundary for upward transfer;
6. upward transfer carries locally processed information;
7. upper nodes may change because of information from below;
8. when an upper node stops changing, the same upward-transfer rule applies again;
9. an upward-converged or improved state may initiate a new downward expansion.

## 14. Candidate novelty boundary

Many relevant ideas already exist separately or in partially overlapping combinations, including:

- evolutionary computation;
- hierarchical evolutionary systems;
- cultural algorithms;
- recursion schemes;
- fold/unfold compositions;
- recursive self-improvement;
- hierarchical aggregation;
- distributed learning.

Therefore BECA does not claim that recursion, bidirectionality, branching, aggregation, or self-improvement are individually new.

The candidate contribution to investigate is the exact combined mechanism:

> **a self-similar hierarchy in which variation expands downward, cessation of local change gates processed-information transfer upward, each upper node may itself evolve from that information and later transfer upward by the same rule, and an upward-converged state can initiate another downward expansion.**

Current novelty status: **unverified architectural originality**.

## 15. Open questions

Important unresolved questions include:

- How should cessation of change be formalized?
- What information must be retained for useful upward transfer?
- How should conflicting lower-level information affect an upper node?
- How does branching factor affect convergence?
- Can upward convergence destabilize a previously stable upper node?
- When should a converged upper state begin another downward expansion?
- Can a finite implementation approximate an unbounded recursive hierarchy?
- Which existing formal systems are mathematically equivalent to this mechanism?

## 16. Conclusion

BECA's current core can be summarized as:

> **Expand downward. Converge upward. Let convergence change the state that expands again.**

The full sequence is:

> **downward expansion -> descendant variation -> local change -> cessation of change -> processed-information transfer upward -> upper-node change -> upper-node cessation -> further upward convergence -> renewed downward expansion.**

The theory is intended as a compact recursive skeleton that can later be formalized, implemented, criticized, compared with prior art, or falsified.
