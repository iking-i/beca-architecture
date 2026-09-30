# Bidirectional Evolutionary Recursion

This document states the current minimum mechanism without implementation detail.

## 1. Core definition

**Bidirectional Evolutionary Recursion** is a recursive evolutionary mechanism with two coupled directions:

- **downward expansion** generates descendants, branches, or lower-level processes that may change and diverge;
- **upward convergence** begins when a lower-level process stops changing and transfers its processed information to its parent;
- the parent may continue changing because of that information;
- when the parent also stops changing, the same upward-transfer rule applies again;
- an improved or converged upper state may become the source of another downward expansion.

In compact form:

```text
expand downward
    -> local variation and change
    -> cessation of change
    -> processed information moves upward
    -> upper level changes
    -> upper level stops changing
    -> further upward convergence
    -> renewed downward expansion
    -> ...
```

## 2. Recursive node

For any node `X`:

```text
             parent(X)
                 ↑
                 │  X stops changing
                 │  and transfers processed information
                 │
                 X
              /  |  \
             /   |   \
           Y1   Y2   Y3 ...
```

The same rule applies to `Y1`, `Y2`, `Y3`, and to `parent(X)`.

A node can therefore be both:

- an upper layer relative to its descendants; and
- a lower layer relative to its parent.

## 3. Downward recursion

Downward recursion creates possibility.

A node may produce lower-level descendants or branches. Only some need to reproduce further, and descendants may differ from their predecessors.

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

The exact mechanisms of reproduction, branching, mutation, inheritance, and environmental interaction are intentionally left open.

## 4. Upward recursion

Upward recursion accumulates processed change.

A node does not transfer upward merely because it exists or has temporary information. The boundary is cessation of change:

```text
still changing
    -> remain at the current level

stops changing
    -> processed information becomes eligible for upward transfer
```

The parent may change after receiving information from below. When the parent itself stops changing, it becomes eligible to transfer processed information upward by the same rule.

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

## 5. Renewal

Upward convergence does not terminate the architecture.

A state improved through upward convergence may generate another downward expansion:

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

Thus the two directions recursively generate one another:

> **downward recursion produces the material for upward recursion; upward recursion produces the state from which later downward recursion can begin.**

## 6. Minimum invariants

A mechanism conforms to this minimum definition if:

1. a node can recursively generate lower-level processes or descendants;
2. lower-level descendants may differ from their predecessors;
3. only some descendants are required to continue the lineage;
4. changing local information remains local to the changing process;
5. cessation of change is the boundary for upward transfer;
6. what moves upward is information already processed by the lower-level process;
7. an upper node may change itself using information received from below;
8. when that upper node stops changing, the same transfer rule applies again;
9. an upper state formed or improved through convergence may initiate a new downward expansion.

## 7. What the concept does not yet specify

The theory does not yet fix:

- the number of descendants;
- the reproduction criterion;
- the mutation or divergence mechanism;
- the representation of transferred information;
- conflict resolution at upper levels;
- a numerical definition of cessation of change;
- maximum recursion depth;
- a specific physical or software implementation.

These may be formalized later without changing the minimal recursive core.

## 8. Working terminology

- **Bidirectional Evolutionary Recursion** — current formal working name.
- **Perfect Recursion** — informal name for the closed two-direction recursive form.

The second term is descriptive, not a claim of mathematical optimality.
