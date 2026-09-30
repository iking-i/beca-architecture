# BECA — Testable Predictions

BECA is presented here as a **theoretical architecture**. The author is not claiming that this repository contains an implementation or experimental validation.

This document exists so that others can identify observations that would support, narrow, revise, or contradict the theory.

## 1. Theoretical setup

BECA assumes a population of agents with:

1. the same initial state;
2. participation in the same larger world;
3. different local positions, histories, observations, and interactions;
4. the ability to communicate with one another during evolution;
5. locally mutable internal states;
6. a finite or otherwise terminable local evolutionary process;
7. determinate results transferred to a higher-level integration layer after local closure.

The crucial distinction is:

> **Peer communication is allowed during evolution. Higher-level integration receives the result only after the relevant local evolutionary process has ended.**

A message from Agent A may change Agent B. That message becomes part of B's local experience. It does not automatically become a completed higher-level result merely because it was communicated.

## 2. Prediction: one origin can produce useful divergence

If agents begin from the same initial state but encounter different local regions of the same world, their internal structures should diverge in ways that contain information about those local histories.

BECA therefore predicts that differentiated local experience can produce useful variation that a single trajectory would not generate.

## 3. Prediction: communication and local evolution are compatible

BECA does not predict that useful agents must be isolated.

Agents can exchange observations, hypotheses, questions, warnings, and provisional ideas while preserving locally mutable state.

The relevant distinction is not whether communication occurs, but whether communicated information remains part of ongoing local evolution or is prematurely treated as a completed higher-level result.

## 4. Prediction: active local states and completed results should behave differently

A local state may change many times:

```text
V1 -> V2 -> V3 -> ... -> local closure -> result
```

BECA predicts that treating every `Vn` as equally eligible for higher-level integration will create cases in which the upper system acts on information that would have changed if the local process had been allowed to continue.

The architecture therefore expects a meaningful distinction between:

- an active local state;
- the determinate output of an ended local process.

If no such distinction matters in a target domain, BECA adds little value there.

## 5. Prediction: local processes can end without explicit task completion

BECA predicts that a local process can become effectively complete even without one explicit life task.

Closure may arise because:

- repeated experience becomes redundant;
- existing structure dominates new low-weight information;
- new information no longer produces material change;
- the system reaches a practical fixed point;
- finite time, lifetime, or resources terminate the process;
- a human or external controller ends the process.

This is analogous to a finite organism whose lifetime ends even though its life was not organized around one explicit task.

If open-ended local processes must remain indefinitely active for useful integration to occur, this part of BECA would be weakened.

## 6. Prediction: second-stage integration is a distinct process

Local evolution asks questions such as:

- What did this local history produce?
- Which inputs were reinforced, weakened, ignored, or reinterpreted?
- What structure remained when the local process ended?

Second-stage integration asks different questions:

- Which completed results agree?
- Which conflict?
- Which are duplicates or complementary?
- What relation appears only when several results are processed together?
- What higher-level state can be formed from them?

BECA predicts that separating these two stages is useful in at least some complex systems.

## 7. Prediction: source identity is not theoretically necessary

BECA predicts that the higher layer can perform its essential role using completed results even if the individual source no longer exists or cannot be reconstructed.

Provenance may still be useful in an implementation for debugging, auditing, trust, security, or research. But the theory itself does not require permanent source identity.

If higher-level integration fundamentally cannot work without reconstructing and preserving every source agent, then BECA's result-only abstraction would be too strong.

## 8. Prediction: integrated knowledge can become a new common starting point

BECA naturally allows a generational cycle:

```text
common state M0
    -> multiple situated local evolutions
    -> local closure
    -> determinate results
    -> second-stage integration
    -> revised common state M1
    -> new local evolutions
    -> ...
```

Local divergence produces candidate changes; integration turns useful results into a new shared basis for later evolution.

## 9. What would count against BECA?

The theory should be narrowed if evidence repeatedly shows that, for a given class of systems:

- different local trajectories from one initial state produce no useful variation;
- active local states and completed results are operationally indistinguishable;
- local closure cannot be defined meaningfully even with finite lifetime/resource boundaries;
- immediate higher-level fusion performs equally well without semantic or revision problems;
- second-stage integration cannot operate without replaying every mutable local state;
- permanent source reconstruction is indispensable to the integration process.

## 10. What BECA does not require

BECA does **not** require:

- agents to stop communicating;
- agents to hide provisional ideas from peers;
- a fixed number of agents;
- a single implementation technology;
- one universal closure rule;
- one specific learning algorithm;
- permanent source tracking;
- the original proposer to implement the theory.

It proposes a structural distinction:

> **same origin + shared world + situated local evolution + peer communication + local closure + determinate results + second-stage integration**.
