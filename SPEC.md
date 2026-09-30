# BECA Specification v0.5

This specification defines the current minimum mechanism of BECA as **Bidirectional Evolutionary Recursion**.

## 1. Core terms

### 1.1 Node
A node is any local process that can:

- receive information from lower-level nodes;
- continue changing internally;
- produce lower-level descendants or branches;
- transfer processed information upward after its own change stops.

No node is theoretically privileged as the final root.

### 1.2 Descendant
A descendant is a lower-level process generated from an existing node.

Only some descendants need to generate further descendants.

### 1.3 Variation
A descendant may differ from its predecessor. The theory does not yet prescribe how this difference is produced.

### 1.4 Active change
A node is active while its relevant internal state is still changing.

### 1.5 Cessation of change
The boundary at which the relevant state of a node is no longer changing.

Cessation does not imply correctness, completeness, confidence, task completion, or eternal truth.

### 1.6 Processed information
Information produced, transformed, filtered, compressed, related, generalized, or otherwise processed by a node before upward transfer.

The minimum theory does not require the complete local history to be transferred.

### 1.7 Upward transfer
When a node stops changing, its processed information becomes eligible to move to its parent or higher-level node.

### 1.8 Downward expansion
A node may generate lower-level descendants or branches, creating new local trajectories and possible variation.

### 1.9 Upward convergence
Processed information from lower levels is absorbed by an upper node. The upper node may itself continue changing as a consequence.

### 1.10 Renewal
A state improved or formed through upward convergence may become the source of a new downward expansion.

## 2. Minimal recursive rule

For an arbitrary node `X`:

```text
X generates descendants
        ↓
descendants may vary
        ↓
local change continues
        ↓
change stops
        ↑
processed information moves to X
        ↑
X may change using that information
        ↑
X stops changing
        ↑
X transfers processed information to its own parent
```

The same rule can apply again at the next level.

## 3. Core invariants

### BER-I1 — Downward expansion is recursive
A node MAY generate lower-level descendants, and those descendants MAY themselves generate further descendants.

### BER-I2 — Continuation is selective
The theory does NOT require every node or descendant to reproduce further.

### BER-I3 — Descendants may vary
Lower-level descendants MAY differ from their predecessors.

### BER-I4 — Changing state remains local
Information that is still changing inside a node is not yet treated as the node's upward contribution.

### BER-I5 — Cessation of change is the upward boundary
Processed information becomes eligible for upward transfer only after the relevant node stops changing.

### BER-I6 — Upward transfer carries processed information
What moves upward is information after local processing, not necessarily raw history or every intermediate state.

### BER-I7 — Upper nodes may evolve from lower-level information
An upper node MAY modify its own state or structure using information transferred from lower levels.

### BER-I8 — Upward recursion repeats the same boundary
When an upper node later stops changing, it becomes a lower node relative to its own parent and applies the same upward-transfer rule.

### BER-I9 — Convergence may regenerate expansion
A state produced or improved by upward convergence MAY initiate a new downward expansion.

### BER-I10 — No privileged center is required
A node can simultaneously be parent to lower nodes and child to a higher node. The theory does not require one final integration center.

## 4. Two coupled recursive directions

### 4.1 Downward recursion

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

Downward recursion expands possible trajectories through descent, reproduction, branching, and variation.

### 4.2 Upward recursion

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

Upward recursion is triggered by cessation of change. Each level receives processed information from below, may change, and eventually may itself transfer upward.

## 5. Bidirectional closure

The two directions are coupled:

```text
downward expansion
    -> variation
    -> active change
    -> cessation of change
    -> upward transfer
    -> upper-level modification
    -> upper-level cessation
    -> further upward transfer
    -> renewed downward expansion
```

The theory therefore does not model downward evolution and upward aggregation as independent subsystems. Each produces the conditions for the other.

## 6. Cessation is not death

An earlier biological analogy used death as one possible finite boundary. That is not the theoretical rule.

The actual rule is:

```text
still changing -> remain local
stops changing -> upward transfer becomes possible
```

Death, timeout, exhaustion, internal fixation, or another event may cause cessation in an implementation, but none is required by the abstract theory.

## 7. What the theory does not yet prescribe

BECA does not currently require one particular answer to:

- how descendants are generated;
- how many descendants exist;
- how variation occurs;
- what information a node stores;
- how incoming information is filtered;
- how conflicting information is combined;
- how cessation is detected;
- whether communication occurs laterally between nodes;
- whether physical depth or population is finite or unbounded.

## 8. Minimal conformance

A system is minimally compatible with the present theory if:

1. lower-level descendants or branches can be generated recursively;
2. some descendants may differ from predecessors;
3. not all descendants must continue reproducing;
4. changing information remains within the active local process;
5. cessation of change gates upward transfer;
6. upward transfer contains locally processed information;
7. upper nodes can change from lower-level information;
8. the same cessation-and-transfer rule can recur upward;
9. an upward-converged state can later initiate another downward expansion.

## 9. Compact definition

> **Bidirectional Evolutionary Recursion is a self-similar mechanism in which variation expands downward, processed information converges upward only after local change stops, upper nodes evolve using that converged information, and the resulting upper state can generate a new downward expansion.**
