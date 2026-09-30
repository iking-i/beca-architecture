# BECA Architecture

## 1. Design objective

BECA separates four things that should not be confused:

1. **one initial root state**, from which the first differentiated agents are created;
2. **continuous branch evolution**, where those agents preserve their own histories and may differentiate further from their current states;
3. **local closure**, where some local information stops changing and becomes eligible for upward transfer;
4. **root-level second-stage integration**, where the root system uses closed information from branches to modify its own underlying structure.

The architecture is not based on agent silence, and it is not based on repeatedly recreating agents from the latest root state.

## 2. First differentiation

The initial topology is:

```text
            A
         /  |  \
        B   C   D
```

At the moment of first differentiation:

```text
state(A) = state(B) = state(C) = state(D)
```

`B`, `C`, and `D` differ only after they begin to experience different local histories.

## 3. Continuous branch evolution

After differentiation, each branch preserves continuity with its own prior state:

```text
B(t+1) derives from B(t)
C(t+1) derives from C(t)
D(t+1) derives from D(t)
```

If a branch differentiates again, the new branch is derived from that branch's current evolved state, not from the latest root state.

Example:

```text
             A
          /  |  \
         B   C   D
        / \     / \
      B1  B2  D1  D2
```

Here `B1` and `B2` continue the history accumulated in `B`; they are not resets from an updated `A`.

## 4. Why repeated reinitialization is incompatible

The following pattern is **not** the intended architecture:

```text
A0 -> B0 / C0 / D0
      closed branch information -> A1
A1 -> fresh B1 / C1 / D1
      closed branch information -> A2
A2 -> fresh ...
```

That design repeatedly resets the local environment and destroys continuity.

It erases or disrupts:

- accumulated local experience;
- relationships;
- path-dependent adaptation;
- local structural changes;
- long-term environmental history.

BECA instead requires continuity along existing lineages after the first differentiation.

## 5. Shared world and communication

All branches exist in one shared world.

They may occupy different regions and may communicate with one another.

A peer message can change a branch's local state, but the message remains part of that branch's ongoing local evolution until the relevant state stops changing.

```text
peer communication -> local input -> further local change
```

Communication does not itself create an upward integration event.

## 6. Local closure

A local state is eligible for upward integration when the relevant local process no longer changes it.

Closure does not require:

- task completion;
- correctness;
- a semantic conclusion;
- internal consistency.

A closed state can be incomplete or wrong. The only required property is that the local process has stopped changing it.

Closure may occur through:

- fixation;
- repeated experience becoming redundant;
- low effective weight of new information;
- finite lifetime;
- time/resource exhaustion;
- human or external termination.

## 7. Upward transfer

When local change stops, information from that closed state becomes available to the root-level integration process.

```text
closed state in B --+
closed state in C ---+--> root-level second-stage integration
closed state in D --+
```

The root does not need to reconstruct or preserve the source individual unless an implementation wants provenance for engineering reasons.

## 8. Root-level structural improvement

The root system `A` uses upward-transferred closed information to modify its own underlying structure.

This modification may affect:

- rules;
- default responses;
- weights;
- relations;
- information-processing structure;
- other foundational mechanisms.

The important point is that improvement is not merely appending facts to a knowledge list. It may alter the base structure itself.

## 9. Root improvement does not reset branches

Let the root change from `A0` to `A1` after second-stage integration.

This does **not** imply:

```text
B <- reset from A1
C <- reset from A1
D <- reset from A1
```

The already-evolving branches retain their own continuous histories.

The theory currently leaves open how a later structural change in `A` may influence existing branches, if at all, without destroying continuity.

That mechanism must not be assumed until defined.

## 10. Two simultaneous directions of evolution

The architecture therefore contains two simultaneous processes.

### Outward branch evolution

```text
A
├─ B
│  ├─ B1
│  └─ B2
├─ C
└─ D
   ├─ D1
   └─ D2
```

The tree grows outward by differentiation from existing branch states.

### Inward structural improvement

```text
closed branch information
        ↓
second-stage integration
        ↓
modify A's underlying structure
```

The root becomes more complete while the branch tree preserves continuity.

## 11. System view

```text
                          Root A
                    underlying structure
                           /|\
                          / | \
             first identical differentiation
                        /   |   \
                       B    C    D
                      /\         /\
                     /  \       /  \
             continuous lineage growth

closed local information from branches
              \        |        /
               \       |       /
                second-stage integration
                         |
                         v
                modify root structure

(existing branches continue; no global reset)
```

## 12. Core invariants

A BECA-like system therefore preserves the following distinctions:

1. first differentiation begins from one identical root state;
2. later branch evolution is continuous and path-dependent;
3. later differentiation extends existing lineages rather than cloning the newest root state;
4. peer communication is allowed during local evolution;
5. only information that has stopped changing locally becomes eligible for upward integration;
6. upward integration can modify the root's underlying structure;
7. root modification does not automatically reset existing branches;
8. the mechanism by which root changes may later affect ongoing branches remains a separate theoretical question.

## 13. Main trade-off

Potential benefits include:

- preservation of environmental continuity;
- retention of long-term local adaptation;
- multiple persistent evolutionary trajectories;
- root improvement from many locally evolved histories;
- separation between ongoing branch change and root-level integration.

Potential costs include:

- increasingly divergent branches;
- harder coordination across long-lived lineages;
- uncertainty about how root improvements should propagate without reset;
- possible accumulation of obsolete local structures;
- greater complexity than repeated reinitialization.

These are properties of the architecture to analyze, not reasons to replace continuity with resetting.
