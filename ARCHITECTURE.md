# BECA Architecture — Bidirectional Evolutionary Recursion

## 1. Structural idea

BECA is now modeled as a **bidirectional recursive hierarchy** rather than a privileged root with permanent subordinate branches.

Every node can occupy two roles at once:

- parent relative to lower-level descendants;
- descendant relative to a higher-level node.

The same rule can therefore repeat at every level.

## 2. Downward expansion

A node can generate lower-level descendants or branches:

```text
A
├─ B1
├─ B2
├─ B3
└─ ...
```

Only some descendants need to continue reproducing.

A reproducing descendant can generate another level:

```text
A
└─ B
   └─ C
      └─ D
         └─ ...
```

Descendants may differ from their predecessors. This creates local variation and distinct trajectories.

The current theory intentionally leaves the variation mechanism open.

## 3. Active local change

Each node may continue changing while processing local information.

```text
state X0
  -> X1
  -> X2
  -> X3
  -> ...
```

While relevant state is still changing, it remains local to that node.

The higher layer does not treat every intermediate mutation as a finished contribution.

## 4. Cessation of change

The decisive boundary is:

```text
still changing
    -> remain in local evolution

stops changing
    -> processed information becomes eligible for upward transfer
```

This boundary is not equivalent to death.

Death, a timeout, exhaustion, internal fixation, or another event may cause change to stop, but the theory only depends on cessation itself.

## 5. Upward convergence

When a lower node stops changing, it transfers processed information upward.

Example:

```text
D stops changing
      ↑
processed information
      ↑
C receives it
```

`C` may then change further because of the information received from `D`.

When `C` later stops changing:

```text
C stops changing
      ↑
processed information
      ↑
B receives it
```

The same rule repeats recursively:

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

## 6. The same node participates in both directions

Consider node `B`:

```text
        A
        ↑
        B
        ↓
        C
```

Relative to `C`, `B` is an upper node.

Relative to `A`, `B` is a lower node.

So `B` can simultaneously:

1. receive processed information from `C`;
2. continue changing from that information;
3. generate descendants below itself;
4. eventually stop changing;
5. transfer its own processed information upward to `A`.

This is the self-similar recursive unit.

## 7. Full bidirectional cycle

The architecture is not only downward generation plus upward aggregation.

The two directions generate each other:

```text
DOWNWARD EXPANSION
        ↓
new descendants / branches
        ↓
variation and local histories
        ↓
active change
        ↓
cessation of change
        ↑
processed information moves upward
        ↑
upper node changes
        ↑
upper node stops changing
        ↑
further upward convergence
        ↓
converged / improved state generates new downward expansion
        ↓
...
```

The shortest form is:

> **Expansion produces convergence; convergence produces the next expansion.**

## 8. Evolutionary interpretation

The model contains two complementary evolutionary directions.

### Downward evolutionary direction

```text
parent
  ↓
descendant
  ↓
later descendant
  ↓
...
```

This direction generates variation and explores possible trajectories.

### Upward evolutionary direction

```text
closed descendant information
        ↑
parent changes
        ↑
parent closes
        ↑
higher parent changes
        ↑
...
```

This direction allows accumulated lower-level experience to alter higher-level states.

Thus:

> **Variation expands downward; evolutionary gain accumulates upward.**

## 9. Renewal after convergence

Upward convergence does not terminate the architecture.

A state formed through convergence may generate a new lower-level expansion:

```text
X
↓
Y1 Y2 Y3 ...
↓
local variation
↑
cessation + convergence
↑
X'
↓
new expansion
```

`X'` is not required to be identical to the earlier `X`, because incoming lower-level information may have altered it.

This creates recursive renewal rather than a one-way tree.

## 10. No privileged root

Earlier versions of BECA treated `A` as a special integration root.

The current architecture removes that assumption.

`A` may itself be only one local node inside a still higher process:

```text
        P
        ↑
        A
        ↑
        B
        ↑
        C
```

Therefore the theory does not require one final topmost integration node.

## 11. Minimal topology

A compact representation is:

```text
              ↑ upward convergence
              │
              P
              ↑
              A
             /|\
            / | \
           B  B  B
          /       \
         C         C
        /           \
       D             D
              │
              ↓ downward expansion
```

The geometry is secondary. The key rule is directional:

- downward: generate and vary;
- upward: transfer only after cessation;
- convergence may alter the node that later expands again.

## 12. Core invariants

1. every node may be both parent and descendant;
2. downward generation may recurse indefinitely in theory;
3. only some descendants need to continue reproducing;
4. descendants may differ from predecessors;
5. information remains local while its owning node is still changing;
6. cessation of change is the transfer boundary;
7. upward transfer carries processed information;
8. upper nodes may change using information from below;
9. the same cessation-and-transfer rule repeats upward;
10. a converged upper state may initiate another downward expansion.

## 13. Open questions

The architecture still leaves open:

- exact descendant-generation rules;
- the source and magnitude of variation;
- lateral communication between nodes;
- how processed information is represented;
- how several lower-level transfers are combined;
- how cessation of change is detected;
- whether upward convergence is monotonic, reversible, or path-dependent;
- how finite implementations approximate a theoretically unbounded recursive structure.

These questions refine the mechanism but do not change its current recursive skeleton.
