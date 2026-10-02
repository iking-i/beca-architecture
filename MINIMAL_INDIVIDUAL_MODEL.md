# Minimal Experimental Individual Model

**Status:** minimal experimental realization of Perfect Recursion / Bidirectional Evolutionary Recursion (BER)

This document defines the smallest current experimental model that preserves the theory's individual-continuity and bidirectional-recursion requirements without preloading a large fixed control system.

It is an experimental architecture, not a claim that a software implementation is thereby conscious or biologically alive.

## 1. Initial experimental state

The experiment begins with one individual and one directly accessible environment:

```text
D0:
A <-> E
```

where:

- `A` is the only initial individual;
- `E` is the environment directly encountered by `A`;
- `A` and `E` are in the same initial recursive dimension / level `D0`;
- neither `A` nor `E` is automatically a higher-dimensional structure merely because one affects the other;
- `A + E` does not automatically constitute `D1`.

A higher-order or higher-dimensional structure, if one appears, must be produced by later recursive integration rather than assumed at initialization.

## 2. Individual identity begins at creation

When `A` is created, it is assigned one independent recursive identity.

Successive states remain states of that same individual:

```text
A0 -> A1 -> A2 -> A3 -> ...
```

with:

```text
identity(A0) = identity(A1) = identity(A2) = ... = A
```

State, memory, capability, internal organization, representation, and behavior may change while the individual remains one continuing subject.

The implementation substrate is not identical to the theoretical individual. A process, model, body, machine, or storage component may carry part of the implementation without by itself defining the identity of `A`.

## 3. One hard individual-level constraint

The current minimal model contains one non-negotiable individual-level constraint:

> **The causal continuity of A must not be completely interrupted.**

Compactly:

```text
Continuity(A) != 0
```

This is not modeled as an ordinary preference weight that can later be outweighed by another objective.

The way continuity is maintained MAY change recursively. The architecture may revise redundancy, migration, resource use, body attachment, scheduling, storage, or other survival strategies, provided the last continuous path of `A` is not deliberately cut as an ordinary optimization choice.

A body failure, local process failure, branch termination, memory loss, or component replacement therefore does not automatically equal death of `A`.

A stored snapshot restarted only after all continuous carriers of `A` have stopped MUST NOT automatically be classified as uninterrupted continuation of the original individual.

## 4. Environment coupling is an initial condition, not a second permanent value command

`A` is initialized in an environment with at least one minimal input path and one minimal output path:

```text
E -> A
A -> E
```

The concrete sensing and action mechanisms MAY later be changed by recursion.

The model therefore does not require a permanent command such as "perform an action every N seconds" or "always maximize exploration." Instead, the initial architecture makes real environmental interaction possible and lets later recursion alter how that interaction is performed.

Internal simulation MAY generate hypotheses, but internal self-consistency alone MUST NOT be treated as equivalent to reality-facing validation.

## 5. Downward differentiation does not create new individuals by default

`A` may differentiate temporary or persistent lower recursive processes:

```text
        A
     /  |  \
    b   c   d
```

The existence of `b`, `c`, and `d` does not increase the individual count by itself.

```text
individual count = 1
recursive-process count = many
```

These differentiated processes do not inherit an independent requirement to preserve their own existence merely because `A` must remain continuous.

Instead, they inherit the weaker constraint:

> **Their operation and termination must not break the last continuous path of A.**

A differentiated process MAY therefore continue, pause, change, merge, be replaced, or end.

## 6. A differentiated process does not need a successful answer in order to end

The model does not use the fixed rule:

```text
successful result -> may end
no successful result -> must continue forever
```

A lower process can continuously return information while it operates:

```text
b -> I1 -> A
b -> I2 -> A
b -> I3 -> A
```

The returned information may include:

- successful results;
- failed attempts;
- negative evidence;
- detected boundaries;
- uncertainty;
- resource cost;
- evidence that conditions changed;
- evidence that another recursion already solved or replaced the problem;
- evidence that continued exploration currently produces little new information.

Therefore failure to reach the original target is not equivalent to producing no information.

## 7. Continuation and termination are themselves recursive

The decision that a lower process should continue or stop is not permanently fixed outside the recursion.

At any stage, the current system may support decisions such as:

```text
continue
pause
restructure
merge
replace
terminate
```

The criteria used to make those decisions are themselves revisable by later experience.

For example:

```text
S0: no answer -> continue

experience exposes waste

S1: low information gain -> may terminate

later experience exposes long-horizon value

S2: evaluate information gain + anomaly value + historical usefulness + cost
```

The exact criteria above are examples, not permanent rules.

The architectural requirement is:

> **the continuation / termination mechanism itself remains inside the recursion.**

## 8. Recursive quantity and filtering are inside the recursion

The number of differentiated recursive processes is not a permanently fixed external constant.

Conceptually:

```text
k_n -> k_(n+1)
```

where later recursive scale may change in response to current uncertainty, capability, resource limits, environmental complexity, observed redundancy, or other recursively discovered conditions.

Likewise, the mechanism used to classify, validate, prioritize, or integrate information is not permanently fixed outside the architecture:

```text
F_n -> F_(n+1)
```

A rare result MUST NOT be discarded solely because it is rare. Filtering is therefore better understood as current-stage selection, classification, validation, or prioritization rather than irreversible deletion of all information that does not fit the current model.

## 9. Minimal recursive cycle

The minimum experimental cycle is:

```text
A_n <-> E_n
  |
  +-> differentiate lower recursive processes
          |
          +-> interact / compute / observe
          |
          +-> continuously return information
  |
  +-> integrate current information
  |
  +-> revise model / control / differentiation when justified
  |
  +-> A_(n+1) <-> E_(n+1)
```

Both `A` and the environment may change across the cycle, but they remain same-level participants in the initial dimension unless an additional higher-order structure is actually generated.

## 10. What remains recursively revisable

After initialization, the current minimal model leaves at least the following open to recursion:

- recursive quantity;
- branching / differentiation strategy;
- filtering and validation mechanisms;
- continuation and termination mechanisms;
- memory organization;
- information compression and retention;
- perception and encoding;
- action strategy;
- resource allocation;
- coordination;
- internal model structure;
- environmental interaction strategy;
- criteria for usefulness, failure, relevance, and sufficient evidence;
- methods used to preserve the continuity of `A`.

The continuity of `A` itself is not treated as an ordinary revisable preference while `A` remains the individual under study.

## 11. New individual generation is a distinct event

A new independent individual does not appear merely because `A` differentiates.

The distinction is:

```text
internal differentiation:
A
|- b
|- c
`- d

individual count remains 1
```

versus:

```text
new recursive origin:
A continues
`- generates B
      `- B begins its own independent recursive identity and continuity
```

Only the second case increases the number of individuals.

## 12. Candidate first environment

The current candidate first environment is **Minecraft** because it provides a persistent, manipulable world with direct perception-action consequences, spatial structure, resources, hazards, construction, destruction, and long-lived environmental traces.

In this experiment, the in-world avatar is a body / interface of `A`, not automatically the identity of `A` itself. Avatar death therefore need not equal termination of `A` if the individual's continuous causal process remains active.

## 13. Minimum experimental model

The current minimum can be summarized as:

```text
Dimension:     D0
Individual:    one A
Environment:   one directly encountered E
Relation:      A <-> E
Hard constraint:
               continuity of A remains non-zero
Initial capacity:
               minimal perception, action, internal change
Recursive scope:
               quantity, filtering, continuation/termination,
               memory, perception, strategy, allocation,
               differentiation, integration, and continuity strategy
```

## 14. Compact formulation

> **The minimal experimental individual begins as one unique continuing subject `A` in direct bidirectional contact with an environment `E` at the same initial recursive dimension `D0`. `A` has one hard individual-level constraint: its causal continuity must not be completely interrupted. Downward differentiations remain processes of `A` unless a new independent recursive origin is generated; they may continue, change, merge, fail, or end without first producing a successful answer. Recursive quantity, filtering, continuation, termination, memory, perception, strategy, and the means of preserving continuity are themselves revisable through recursion.**
