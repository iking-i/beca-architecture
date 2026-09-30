# BECA — Testable Predictions for Bidirectional Evolutionary Recursion

BECA is presented as a conceptual theory proposal. This document states observations that could support, narrow, revise, or contradict the current mechanism.

## 1. Theoretical setup

The current theory assumes a recursive hierarchy in which:

1. nodes may generate lower-level descendants or branches;
2. only some descendants need to continue reproducing;
3. descendants may differ from predecessors;
4. each node may continue changing while processing local information;
5. cessation of change gates upward transfer;
6. upward transfer carries processed information;
7. upper nodes may change from lower-level transferred information;
8. when an upper node later stops changing, the same upward-transfer rule applies again;
9. a converged or improved upper state may later initiate new downward expansion.

The central distinction is:

> **Downward expansion generates variation; cessation of change enables upward convergence; upward convergence can modify the state that generates the next downward expansion.**

## 2. Prediction: downward branching can create useful variation

If lower-level descendants encounter different histories or contain inherited variation, their processed states should diverge in ways that expose information unavailable to a single trajectory.

If branching never produces any useful diversity, the downward half of the architecture adds little value.

## 3. Prediction: active and closed local states should behave differently

A node may change repeatedly:

```text
V1 -> V2 -> V3 -> ... -> cessation
```

BECA predicts that treating each intermediate `Vn` as equivalent to a closed upward contribution will sometimes cause the upper layer to act on states that would later have changed materially.

If active and closed states are operationally indistinguishable in a target domain, the closure boundary contributes little.

## 4. Prediction: cessation can be defined without task completion

The theory predicts that useful upward transfer can be triggered by cessation of change rather than explicit task completion.

Possible implementation-specific causes include internal fixation, repeated redundancy, resource boundaries, time boundaries, or externally imposed termination.

If no meaningful cessation boundary can be defined, this part of the theory is weakened.

## 5. Prediction: processed information should be sufficient in some domains

BECA does not require every lower-level intermediate state to be replayed upward.

It predicts that, in at least some systems, locally processed information from a closed node is sufficient for useful higher-level change.

If higher-level improvement always requires full reconstruction of every lower-level trajectory, the abstraction is too strong.

## 6. Prediction: upward transfer can change the upper node

A defining claim is that upper nodes are not passive collectors.

They may change their own state or structure using information transferred from below.

Therefore a system implementing only:

```text
lower results -> static archive
```

would not capture the full theory.

The stronger predicted pattern is:

```text
lower closure
    -> upward processed information
    -> upper-node change
```

## 7. Prediction: upward recursion can repeat

The same boundary should remain meaningful one level higher:

```text
C stops changing -> B changes
B stops changing -> A changes
A stops changing -> higher level changes
```

If the mechanism only works once and cannot be meaningfully re-applied at the next level, the claim of self-similar recursive structure should be narrowed.

## 8. Prediction: convergence can alter future expansion

The strongest current claim is not merely that information moves upward.

It is that a state changed through upward convergence can later become the source of new downward expansion.

Therefore later descendants should, in principle, differ from those that would have been generated before convergence.

The characteristic loop is:

```text
expand
 -> vary
 -> cease
 -> converge
 -> modify upper state
 -> expand again from modified state
```

If upward convergence never affects later downward generation, the architecture reduces to a much weaker aggregation model.

## 9. Prediction: bidirectional coupling can outperform one-way inheritance in some domains

A conventional one-way lineage allows descendants to replace or continue predecessors without feeding stabilized lower-level information back into upper levels.

BECA predicts that, in some complex domains, allowing stabilized lower-level information to modify upper-level generators can preserve useful discoveries across many lineages more effectively than purely downward inheritance.

This is a comparative hypothesis, not an established result.

## 10. Prediction: no privileged final root is necessary

Because any node may be both parent and descendant, the mechanism should remain coherent even if a supposed "root" is embedded inside a larger hierarchy.

If the architecture fundamentally requires one unique top-level node that cannot itself participate in the same rule, then the current no-privileged-center claim should be revised.

## 11. What would count against the theory?

The theory should be narrowed if evidence repeatedly shows that:

- lower-level branching produces no useful variation;
- active and closed states are not meaningfully distinguishable;
- cessation of change cannot be operationalized;
- processed closed information is insufficient for useful upper-level change;
- upper nodes cannot be improved from lower-level information without replaying full trajectories;
- the cessation-and-transfer rule cannot recurse upward;
- upward convergence does not affect later downward expansion;
- a privileged final root is unavoidable.

## 12. Current status

These are falsifiable directions for a conceptual architecture. They are not claims that the predicted advantages have already been demonstrated experimentally.
