# Bounded Evolutionary Commit Architecture
## Same-Origin Agents, Situated Evolution, Local Closure, and Second-Stage Integration

**Draft version:** 0.3  
**Status:** Conceptual architecture / theory proposal

## Abstract

We propose **Bounded Evolutionary Commit Architecture (BECA)**, a conceptual architecture in which multiple agents begin from the same initial state, evolve in different local regions of one shared world, communicate during that evolution, and pass only the results of completed local evolutionary processes into a higher-level integration stage.

The central distinction is not between communicating and non-communicating agents. Agents may exchange observations, provisional hypotheses, critiques, warnings, and partial interpretations throughout their evolution. Such communication becomes input to the receiving agent's own local state.

BECA instead separates **active local evolution** from **second-stage integration**. While a local process remains active, its information may continue to change. When that process ends—through internal fixation, diminishing informational change, finite lifetime, resource limits, time limits, or external termination—it yields a determinate result. The higher layer integrates these completed results rather than every intermediate local mutation.

Source identity is not a theoretical requirement. Provenance may be retained for engineering reasons, but BECA only requires the higher layer to receive the results of completed local evolution.

The architecture can repeat generationally: a shared state `M0` is distributed into multiple agents, their local histories diverge, completed results are integrated, and the resulting state `M1` can become the shared initial state of a later generation.

## 1. Introduction

A population of intelligent agents can be understood as more than parallel workers.

BECA begins from a stronger premise: multiple agents are instantiated from **the same initial state** and then placed in different local regions of one shared world.

They do not remain identical because they do not share identical histories.

One agent may encounter evidence another never sees. One may fail where another succeeds. One may receive a peer message and interpret it differently because its local history has already shaped its internal structure.

This divergence is not an implementation error. It is the mechanism by which one common starting state explores multiple trajectories.

The architectural question is:

> How should a higher-level system learn from several evolving local processes without treating every temporary local change as already-finished shared knowledge?

BECA's answer is:

> **Allow local information to remain dynamic while the local process is alive. Allow agents to communicate during that evolution. When a local process ends, pass its determinate result upward for second-stage integration.**

## 2. Same origin, different local histories

Let `M0` denote one common initial state.

```text
A0 = M0
B0 = M0
C0 = M0
```

The agents then occupy different local regions and accumulate different histories:

```text
A(t) = M0 + HA(t) + peer influence
B(t) = M0 + HB(t) + peer influence
C(t) = M0 + HC(t) + peer influence
```

The differences between `HA`, `HB`, and `HC` arise from position, event order, relationships, opportunities, failures, constraints, and communication.

The purpose of the population is therefore not duplication. It is **differentiated evolution from one shared origin**.

## 3. Communication is part of evolution

BECA does not require agents to remain isolated before producing a result.

Agents may exchange:

- observations;
- questions;
- warnings;
- hypotheses;
- critiques;
- partial interpretations;
- requests for verification;
- coordination signals.

A message from Agent A may immediately change Agent B.

However, the message does not automatically become a completed input to the higher-level integration layer. It becomes part of B's continuing local evolution.

The distinction is:

```text
peer communication
    -> local input
    -> further local evolution

local evolutionary closure
    -> determinate result
    -> second-stage integration
```

## 4. Dynamic local information

Inside an active local process, information may remain incomplete and change repeatedly.

```text
observation
  -> interpretation V1
  -> contradiction
  -> peer message
  -> interpretation V2
  -> new evidence
  -> reinforcement / weakening
  -> relation-building
  -> interpretation V3
  -> ...
```

These intermediate states are useful precisely because they are allowed to change.

BECA therefore treats them as belonging to an active process rather than as final contributions to the higher layer.

## 5. Local evolutionary closure

A local process does not require one explicit life task in order to end.

Its evolution may close for several reasons:

- repeated experience produces no meaningful new change;
- existing structure dominates low-weight new information;
- new evidence becomes redundant with already-formed experience;
- the system reaches a practical fixed point;
- finite lifetime ends;
- time or resource budget ends;
- a human or external controller terminates the process.

This is analogous to a biological lifespan: a person does not need one explicit life objective for life to be finite. A finite lifetime itself defines a boundary after which that individual's local evolution stops.

The important architectural fact is simply:

> **the local process has ended.**

## 6. Determinate result

When local evolution ends, the state produced by that process becomes a **determinate result**.

Determinate does not mean eternally true.

It means:

- the local process that produced it is no longer changing it;
- it can now be treated as the output of that completed process;
- later change belongs to another process, another generation, or another shared state.

A finite process therefore converts dynamic information into a result by ending.

## 7. Result commit

A commit is the transfer of that determinate result into the higher-level integration stage.

At theoretical minimum, the upper layer needs only:

```text
Result {
  conclusion
}
```

An implementation may attach metadata such as evidence, confidence, scope, source identity, or history, but these are not required by BECA itself.

The theory does not require the local agent to remain available after the result has been submitted.

## 8. Second-stage integration

The higher layer performs a different process from local evolution.

Local evolution asks:

- What did this local history produce?
- Which inputs were reinforced or weakened?
- How did interaction change the local structure?
- What state remained when the process ended?

Second-stage integration asks:

- Which completed results agree?
- Which conflict?
- Which are duplicates or complementary?
- Which relations appear only when several results are considered together?
- What abstraction or generalization can be formed from them?

The structure is:

```text
same initial state M0
        |
   shared world
  /     |      \
 A      B       C
 <--- peer communication --->
 |      |       |
local  local   local
 evolve evolve evolve
 |      |       |
close  close   close
 |      |       |
RA     RB      RC
  \     |      /
   second-stage integration
            |
            v
           M1
```

The higher layer does not need to replay each local process in order to use its result.

## 9. Source identity is optional

Many distributed architectures emphasize provenance. BECA does not make provenance a theoretical requirement.

Source identity can be useful for:

- debugging;
- auditing;
- trust management;
- security;
- research analysis.

But the conceptual model only requires that the higher layer receives multiple determinate results.

If an individual local agent disappears after its process ends, the integration stage can still use the result it produced.

## 10. Generational evolution

BECA naturally supports a repeated cycle:

```text
M0
 -> same-origin agents
 -> different local histories
 -> peer communication
 -> local closure
 -> determinate results
 -> second-stage integration
 -> M1
 -> later generation begins from M1
 -> ...
```

This allows the whole system to evolve without globally ingesting every local intermediate mutation.

The shared system changes through **differentiation followed by reintegration**.

## 11. Relation to adjacent architectures

### 11.1 Federated learning
Federated learning also distributes a shared model and aggregates local outputs. BECA differs in the semantic boundary it proposes: the relevant transfer happens after a local evolutionary process has ended, rather than simply after a scheduled optimization round.

### 11.2 Blackboard systems
Blackboard systems use a shared evolving workspace. BECA permits provisional ideas to circulate among agents, but distinguishes that circulation from second-stage integration of completed local results.

### 11.3 Actor-style systems
Actor models preserve local state ownership while allowing message passing. BECA adds a lifecycle distinction between an active local process and the result produced when that process ends.

### 11.4 Event sourcing
Event sourcing preserves state-changing events. BECA does not require the upper layer to retain the sequence of local mutations. It may receive only the final result of the completed process.

## 12. Central theoretical claims

BECA proposes the following claims:

1. **multiple agents should begin from the same initial state if their later differences are intended to reflect local evolution**;
2. **agents can communicate while retaining locally mutable state**;
3. **peer influence does not require direct higher-level fusion**;
4. **a local process can end through internal fixation or finite external boundaries even without an explicit life task**;
5. **the result of an ended local process is categorically different from an intermediate state of an active process**;
6. **the higher layer can integrate completed results without requiring permanent reconstruction of the individuals that produced them**;
7. **second-stage integration is a distinct processing stage rather than a continuation of one local agent's unfinished cognition**;
8. **the integrated state can become the common initial state of a later generation**.

## 13. Open theoretical questions

Several mechanisms remain intentionally open:

- How should internal fixation be detected?
- How should finite lifetime or resource boundaries be chosen in artificial systems?
- When does peer communication enrich diversity, and when does it collapse trajectories into correlated copies?
- How should the higher layer combine mutually incompatible completed results?
- How much information must a determinate result contain for useful second-stage integration?
- Can the same architecture recurse, with an integrated system itself acting as a local process inside a larger system?

These are future theory questions, not implementation obligations for the original proposal.

## 14. Conclusion

BECA can be summarized as:

> **One initial state is distributed into multiple agents. They evolve in different parts of one shared world and may communicate throughout that evolution. Their local information remains dynamic while their local processes are active. When those processes end, their determinate results are passed upward. A higher layer performs second-stage integration across those results and may form a new shared state for a later generation.**

Its core sequence is:

> **same origin -> situated divergence -> communication -> local evolution -> local closure -> determinate result -> second-stage integration -> shared-state evolution**

This repository presents that sequence as a theory and architecture proposal for others to formalize, implement, criticize, or test.

## References (initial)

1. H. Brendan McMahan, Eider Moore, Daniel Ramage, Seth Hampson, Blaise Agüera y Arcas. *Communication-Efficient Learning of Deep Networks from Decentralized Data.* AISTATS, 2017.
2. L. D. Erman, F. Hayes-Roth, V. R. Lesser, D. R. Reddy. *The Hearsay-II Speech-Understanding System: Integrating Knowledge to Resolve Uncertainty.* ACM Computing Surveys.
3. *Transactional blackboards.* Artificial Intelligence in Engineering, 1(2), 1986.
4. Martin Fowler. *Event Sourcing.* 2005.
