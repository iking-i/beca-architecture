# Prior Art and Adjacent Architectures

BECA is a conceptual architecture. This document exists to keep novelty claims narrow and testable.

The current question is **not** whether recursion, evolution, branching, aggregation, folding, unfolding, or recursive self-improvement already exist. They do.

The narrower question is whether an existing framework already defines the same coupled mechanism:

> **downward recursive expansion -> local variation/change -> cessation of change -> processed-information transfer upward -> upper-node change -> upper-node cessation -> further upward transfer -> renewed downward expansion from the changed upper state.**

## 1. Evolutionary algorithms

### Similarity

- descendants or candidate states may differ from predecessors;
- only some trajectories continue;
- variation can accumulate over generations.

### Difference to investigate

Conventional evolutionary descriptions usually emphasize forward inheritance or replacement.

BECA additionally treats stabilized lower-level processes as information sources that can modify higher-level generators, and it recursively repeats that upward rule.

The candidate distinction is therefore not variation itself, but **evolutionary information moving upward through the same recursive hierarchy that generated variation downward**.

## 2. Cultural algorithms and hierarchical evolutionary systems

Cultural-algorithm families and related hierarchical evolutionary systems are important comparison targets because they separate population-level processes from higher-level knowledge structures and can include information flow between them.

### Similarity

- lower-level experience may influence a higher-level knowledge structure;
- higher-level structures may influence later evolution;
- evolutionary processing can exist at more than one level.

### Difference to investigate

BECA's current minimum rule is specifically based on:

1. recursive descendant generation;
2. cessation of change as the boundary for upward transfer;
3. processed information changing the parent itself;
4. the parent later applying the same cessation-and-transfer rule to its own parent;
5. an upward-converged state becoming the source of renewed downward expansion.

Whether an existing cultural or hierarchical evolutionary architecture already implements this exact self-similar rule remains an open prior-art question.

## 3. Fold, unfold, hylomorphism, and metamorphism

Recursion-scheme literature already contains well-established ideas corresponding broadly to:

- **unfolding** a structure from a seed;
- **folding** a recursive structure into a result;
- composing unfold and fold;
- composing fold and later unfold.

### Similarity

BECA also contains two complementary directions:

```text
downward expansion
upward convergence
```

### Candidate distinction

BECA is not claiming that bidirectional structural transformation itself is new.

Its candidate contribution is the evolutionary coupling between the two directions:

```text
expand
 -> locally change
 -> stop changing
 -> transfer processed information upward
 -> change the upper node
 -> let that node later stop changing and transfer again
 -> use a converged upper state to generate another expansion
```

Thus the object performing the next expansion may itself have been modified by the preceding convergence.

## 4. Recursive self-improvement

### Similarity

Recursive self-improvement architectures allow a system to alter a later version of itself, potentially repeating the process.

### Difference to investigate

BECA does not begin from a single self-edit loop alone. It explicitly couples:

- downward production of lower-level variation;
- cessation-gated upward information flow;
- parent modification from lower-level processed information;
- recursive repetition of the same upward boundary;
- renewed downward expansion.

The question is whether an existing recursive self-improvement architecture already uses this same bidirectional hierarchy rather than a primarily sequential self-modification loop.

## 5. Hierarchical aggregation and tree reduction

Tree reductions and hierarchical aggregation move lower-level values upward through a hierarchy.

### Similarity

- information can converge upward through multiple levels;
- intermediate nodes can combine lower-level contributions.

### Difference to investigate

A static reduction does not by itself require:

- descendants to evolve;
- cessation of change as the upward boundary;
- the intermediate node to keep changing because of incoming information;
- that intermediate node to later become a lower node relative to its parent under the same rule;
- the final converged state to generate a new downward evolutionary expansion.

## 6. Federated and distributed learning

### Similarity

- local processes produce information used by a higher-level model;
- higher-level aggregation can influence later local computation.

### Difference to investigate

Federated systems commonly aggregate according to scheduled optimization rounds or protocol boundaries.

BECA instead proposes **cessation of relevant local change** as the conceptual transfer boundary and recursively applies the same rule to upper nodes.

## 7. Biological analogy

Biological descent is a useful analogy for downward expansion:

```text
parent -> offspring -> later descendants
```

But BECA adds an abstract upward evolutionary channel:

```text
stabilized descendant information
        -> parent changes
        -> parent stabilizes
        -> information moves further upward
```

This is not a claim that biological ancestors literally update themselves from descendant experience. The biological analogy is only a way to visualize branching, variation, and selective continuation.

## 8. Current candidate contribution

The present candidate contribution is the following combined mechanism:

1. any node may generate lower-level descendants or branches;
2. only some descendants need continue the lineage;
3. descendants may differ from predecessors;
4. active change remains local;
5. cessation of change gates upward transfer;
6. the upward payload is locally processed information;
7. the parent may alter itself using that information;
8. when the parent stops changing, the same upward rule applies again;
9. a converged or improved upper state may generate another downward expansion;
10. no theoretically privileged final center is required.

The compact formulation is:

> **Expand downward. Converge upward. Convergence changes the state that can expand again.**

## 9. Novelty status

Current status: **unverified architectural originality**.

It is reasonable to treat Bidirectional Evolutionary Recursion as a distinct working concept inside this repository.

It is **not** yet reasonable to claim that no mathematically, computationally, or evolutionarily equivalent framework exists.

A formal novelty claim requires systematic comparison across at least:

- recursion schemes;
- evolutionary computation;
- cultural algorithms;
- hierarchical evolutionary systems;
- recursive self-improvement;
- developmental and evolutionary robotics;
- multi-level selection and learning;
- hierarchical aggregation;
- distributed and federated learning;
- recursive multi-agent systems.

## 10. Strongest prior-art question

The key question is:

> **Has an existing architecture already defined a self-similar hierarchy in which variation expands downward, cessation of local change gates processed-information transfer upward, every upper node may itself evolve from that transferred information and later transfer upward by the same rule, and the converged upper state can initiate a new downward expansion?**

If yes, BECA should cite and build on it.

If no, that exact mechanism is the candidate contribution.
