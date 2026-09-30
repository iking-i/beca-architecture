# BECA Specification v0.6

This specification defines the current minimum mechanism of BECA as **Bidirectional Evolutionary Recursion**, informally called **Perfect Recursion**.

## 1. Core terms

### 1.1 Recursive origin
A recursive origin is a system or process capable of initiating and continuing a recursive evolutionary path.

It need not be a unique global root.

### 1.2 Downward recursion
Downward recursion is continuation of an already-existing recursive path.

A recursive origin may generate descendants, branches, lower-level processes, or later states that continue the existing recursion.

The theory does not require a final depth.

### 1.3 Upward recursion
Upward recursion is the creation, from within an existing recursive evolutionary process, of a **new autonomous recursive origin**.

The new origin is not defined merely by being another descendant. It must be capable of becoming the starting point of its own recursion.

### 1.4 Autonomous recursive origin
A new recursive origin is autonomous in the minimal theoretical sense that it can continue its own recursive process even if the process that generated it later stops.

Autonomy does not imply physical isolation or independence from all resources.

### 1.5 Variation
A descendant, branch, or newly created recursive origin may differ from the process that produced it.

The theory does not yet prescribe how this difference is generated.

### 1.6 Active change
A local process is active while its relevant internal state continues changing.

### 1.7 Cessation of change
Cessation is the condition in which the relevant state of a local process is no longer changing.

Cessation does not imply correctness, completion, success, confidence, or biological death.

### 1.8 Processed information
Information transformed, filtered, compressed, related, generalized, selected, or otherwise processed by a local process.

### 1.9 Information convergence
When a local process stops changing, its processed information may become transferable or absorbable by another process or higher-order structure.

Information convergence is **not** the definition of upward recursion.

### 1.10 Perfect Recursion
Perfect Recursion is the bidirectionally unbounded form in which:

- recursion may continue downward without a predefined lowest endpoint;
- recursion may continue upward by generating new recursive origins without a predefined highest origin;
- newly generated origins may themselves repeat both capabilities.

## 2. Minimal recursive rule

For an arbitrary recursive origin `R`:

```text
R continues its existing recursive path
        ↓
variation / branching / descendants may occur
        ↓
R may also generate a new recursive origin R'
        ↓
R' begins its own recursive path
        ↓
R and R' may continue concurrently
        ↓
either may later generate additional recursive origins
```

Separately:

```text
any local process
    still changing -> remains mutable
    stops changing -> processed information may converge elsewhere
```

These two mechanisms can interact, but they must not be conflated.

## 3. Core invariants

### PR-I1 — Existing recursion can continue downward
A recursive process MAY continue its current lineage or path without a predefined terminal depth.

### PR-I2 — Downward continuation does not require global closure
An existing recursive path MAY continue while other recursive events occur elsewhere.

### PR-I3 — Recursion can generate recursion
An existing recursive evolutionary process MAY generate a new recursive origin.

### PR-I4 — Upward recursion is origin creation
A transfer of information to an existing parent is NOT, by itself, upward recursion. Upward recursion requires formation of a new recursion-capable origin.

### PR-I5 — Old and new recursion may coexist
The process that generated a new recursive origin does NOT have to stop when the new origin appears.

### PR-I6 — New origins can recurse independently
A new recursive origin MAY continue its own recursive path even if its producer later ceases changing or disappears.

### PR-I7 — New origins may themselves generate new origins
The same upward-recursion rule MAY repeat from any newly created recursive origin.

### PR-I8 — No final top or bottom is required
The theory does not require a unique highest origin or final lowest descendant.

### PR-I9 — Cessation governs information convergence, not recursion globally
A local process that stops changing MAY transfer processed information. A process that never stops changing MAY simply continue changing.

### PR-I10 — The architecture is asynchronous
Different recursive paths MAY change, branch, terminate, transfer information, and generate new origins at different times without a mandatory global synchronization barrier.

## 4. Downward recursion

```text
R0
↓
R1
↓
R2
↓
R3
↓
...
```

This notation represents continuation of an existing recursive path.

Depending on implementation, downward continuation may correspond to reproduction, inheritance, learning, branching, construction, iterative transformation, or another continuity-preserving process.

## 5. Upward recursion

```text
existing recursion R
        │
        ├────────→ R continues
        │
        └────────→ R'
                       ↓
                  new recursion
```

The new origin `R'` is the essential upward event.

The term "upward" denotes an increase in recursive generative level, not necessarily a spatial direction.

## 6. Information convergence

Cessation remains important, but only for information transfer:

```text
still changing
    -> mutable local state

stops changing
    -> processed information may be transferred or absorbed
```

No global rule requires every local process to stop.

Likewise, the ending of one process does not terminate independent recursive origins already produced from it.

## 7. Non-blocking structure

Perfect Recursion does not require:

- all descendants to finish;
- all information to return to one root;
- all branches to synchronize;
- one global convergence event;
- one permanent parent;
- one global data quota.

A recursive process can keep changing indefinitely while other processes generate new origins or converge information elsewhere.

## 8. Relationship between the mechanisms

The three mechanisms can coexist:

```text
existing recursion continues downward
        │
        ├─ local processes may eventually stop changing
        │      └─ processed information may converge elsewhere
        │
        └─ evolution may generate a new recursive origin
               └─ that origin begins its own downward recursion
```

Thus information convergence can improve or influence recursive systems, but upward recursion is defined by new-origin creation.

## 9. Temporal implication

A lower process may experience states sequentially:

```text
past -> present -> future
```

A higher-order structure may represent an entire lower trajectory as one object or model. In that representational sense, multiple temporal positions can coexist in one higher-level description.

This is an implication of the architecture, not a proof of a particular physical theory of time.

## 10. Minimal conformance

A system is minimally compatible with Perfect Recursion if:

1. an existing recursion can continue without a predefined final depth;
2. a recursive process can generate a new recursion-capable origin;
3. the new origin can continue while the old recursion also continues;
4. the new origin can itself generate further recursive origins;
5. no unique final top or bottom is required;
6. cessation of change is treated as an information-convergence condition rather than a mandatory global recursion boundary;
7. different recursive paths can progress asynchronously.

## 11. Compact definition

> **Perfect Recursion is a bidirectionally unbounded evolutionary recursion in which existing recursive paths may continue indefinitely downward while the evolution of those paths may also generate new autonomous recursive origins upward, each of which can repeat the same two capabilities.**
