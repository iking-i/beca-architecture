# Bounded Evolutionary Commit Architecture
## Shared-Origin Agents, Local Evolution, and Stable Knowledge Integration

**Draft version:** 0.2  
**Status:** Conceptual architecture / theory proposal

## Abstract

We propose **Bounded Evolutionary Commit Architecture (BECA)**, a conceptual architecture for systems composed of multiple agents that begin from the same or mutually compatible initial worldview, evolve in different local regions of one shared world, communicate during that evolution, and expose only stabilized conclusions to higher-level knowledge integration.

The central distinction is not between communicating and non-communicating agents. It is between **dynamic local cognition** and **authoritative higher-level knowledge integration**. Agents may exchange observations, provisional hypotheses, critiques, warnings, and partial interpretations. Such communication becomes input to the receiving agent's own evolving local state. It does not automatically become shared authoritative knowledge.

When a local processing cycle reaches a stabilization criterion, the agent publishes a versioned immutable commit. A higher integration layer then performs second-stage processing across multiple source-preserving commits, including comparison, scope analysis, conflict resolution, deduplication, abstraction, and generalization.

BECA therefore combines six ideas: **common origin, one shared world, different situated trajectories, peer communication, stable commit, and second-stage integration**. The intended contribution is architectural: to distinguish the mutable evolution of local experience from the later integration of stabilized source conclusions.

## 1. Introduction

A population of intelligent agents can be understood in more than one way.

One design treats agents mainly as parallel workers. Another treats them as isolated reasoners. BECA proposes a different interpretation: agents are **common-origin systems situated in different parts of the same world**.

They share a baseline worldview, but they do not share identical histories.

One agent may encounter evidence that another never sees. One may experience a failure that another avoids. One may receive a warning from a peer and reinterpret it differently because of its own history. Over time, agents that began from the same baseline can become meaningfully different.

This divergence is not a defect. It is the source of new information.

BECA asks a specific architectural question:

> How should a higher-level system learn from multiple evolving agents without collapsing every temporary local change into one continuously mutating shared state?

The proposed answer is:

> **Allow rich communication during local evolution, but reserve higher-level integration for stabilized source conclusions.**

## 2. Common origin and divergent evolution

Let `M0` denote a common initial worldview. It may include shared rules, ontology, prior knowledge, protocols, and a basic model of the world.

Agents begin from this baseline:

```text
A0 = M0
B0 = M0
C0 = M0
```

They then occupy different positions or histories in a shared world:

```text
A(t) = M0 + HA(t) + peer influence
B(t) = M0 + HB(t) + peer influence
C(t) = M0 + HC(t) + peer influence
```

where `HA`, `HB`, and `HC` differ because the agents encounter different local events, evidence, constraints, and relations.

The system therefore seeks differentiated experience without losing a common frame of reference.

## 3. Communication is part of evolution

BECA does not prohibit agent-to-agent communication.

Agents may exchange:

- observations;
- warnings;
- questions;
- critiques;
- hypotheses;
- partial interpretations;
- requests for verification;
- coordination signals.

A peer message can substantially change another agent's local trajectory.

This is important: BECA is not based on sealed agents. Social and informational interaction can itself be part of the environment through which an agent evolves.

The architectural boundary instead determines **what a message is allowed to become**.

A message from Agent A to Agent B may immediately affect B's local state. However, it does not automatically become an authoritative update to the parent/shared knowledge base.

The distinction is:

```text
peer communication
      -> local input
      -> local revision

stable commit
      -> higher-level source input
      -> cross-source integration
```

## 4. Dynamic local information

Inside an agent, information may remain incomplete and change repeatedly.

A local cognitive trajectory may look like:

```text
observation
  -> interpretation V1
  -> contradiction
  -> peer message
  -> interpretation V2
  -> new evidence
  -> relation-building
  -> interpretation V3
  -> compression
  -> stabilized conclusion
```

The intermediate states are useful precisely because they are allowed to change.

Prematurely treating them as parent-level conclusions creates a semantic problem: the larger system may integrate a state that its source itself later rejects.

BECA therefore treats the agent as a bounded environment in which information is allowed to evolve before becoming a source contribution to higher-level knowledge.

## 5. Stable commit

A local conclusion becomes eligible for higher-level integration only after an explicit stabilization condition is satisfied.

The architecture does not prescribe one universal stabilization rule. A domain may use repeated consistency, task completion, bounded deliberation, confidence thresholds, contradiction reduction, human approval, or another criterion.

Once stabilized, the agent publishes a commit.

A commit should be:

- source-attributed;
- versioned;
- immutable as a historical result;
- scoped;
- capable of being superseded later by a new commit.

A later change does not modify the old commit in place. It creates a new source result.

This allows the higher layer to integrate well-defined versions rather than moving targets.

## 6. Second-stage integration

The parent/integration layer solves a different problem from local cognition.

Local cognition asks:

- What does this local history imply?
- Which signals were noise?
- How should peer input be interpreted?
- What conclusion survives local revision?

Second-stage integration asks:

- Which evolved sources agree?
- Which disagreements are caused by different local conditions?
- Which conclusions are duplicates, refinements, or contradictions?
- What knowledge is transferable beyond one local region?
- What higher-level abstraction emerges only after comparing several sources?

The structure is:

```text
common initial worldview
          |
          v
     shared world
   /      |       \
Agent A Agent B Agent C
  <---- peer communication ---->
   |       |       |
 local   local   local
 evolve  evolve  evolve
   |       |       |
 Final A Final B Final C
    \      |      /
     \     |     /
   second-stage integration
            |
            v
      shared knowledge update
```

The integration layer works on stabilized source contributions, not on every local mutation that occurred during evolution.

## 7. Why the boundary exists

The boundary serves several roles.

### 7.1 State ownership
Each agent owns its currently mutable local state.

### 7.2 Local interpretation
The same peer message may lead to different changes in different agents because their histories differ.

### 7.3 Source differentiation
Different conclusions remain attributable to different evolved trajectories.

### 7.4 Controlled authority
Communication can influence agents without instantly becoming globally authoritative.

### 7.5 Higher-quality integration inputs
The parent layer receives conclusions that have already undergone one stage of local interpretation and revision.

## 8. Data, experience, and shared knowledge

BECA distinguishes four stages:

### Data
Raw observation or transmitted information.

### Local experience
Data transformed through the history and dynamic state of one agent.

### Stabilized conclusion
A result the source agent currently considers complete enough to commit.

### Shared knowledge
A higher-level result produced by integrating several source commits.

Thus:

```text
world data
   -> local evolving experience
   -> stable source conclusion
   -> cross-source integration
   -> shared knowledge
```

This is a two-stage processing architecture: first within individuals, then across individuals.

## 9. Relation to adjacent architectures

### 9.1 Federated learning
Federated learning also begins with common model structure and aggregates results from distributed participants. BECA differs in emphasis: its central object is not merely a locally computed parameter update, but the lifecycle of information from mutable local interpretation to stabilized source conclusion.

### 9.2 Blackboard systems
Blackboard systems allow multiple knowledge sources to post partial results to a shared workspace. BECA places a stronger semantic distinction between peer interaction and parent-level learned knowledge. Partial local states may circulate among agents without automatically entering the authoritative shared knowledge layer.

### 9.3 Actor-style isolation
Actor models preserve local state ownership while allowing message passing. BECA is compatible with this idea but adds a knowledge lifecycle distinction between ordinary messages and stabilized commits intended for higher-level integration.

### 9.4 Event sourcing
Event sourcing preserves immutable historical events. BECA similarly avoids rewriting past committed source results, but it does not require every internal local state change to become a shared event. Much of the dynamic evolution may remain local.

## 10. Central theoretical claims

BECA proposes the following conceptual claims:

1. **common initial state and different local histories are complementary, not contradictory**;
2. **communication does not require shared mutable authority**;
3. **peer influence can occur without direct parent-level fusion**;
4. **local information should be allowed to change before it is treated as a finalized source contribution**;
5. **higher-level integration is a distinct processing stage that operates across stabilized conclusions from multiple evolved sources**;
6. **the useful output of a population is the differentiated knowledge produced by its trajectories, not simple duplication of the initial system**.

## 11. Open theoretical questions

Several mechanisms remain intentionally open:

- How identical must the initial worldview be?
- How should local position or perspective be represented?
- When does communication enrich diversity, and when does it collapse agents into correlated copies?
- What makes a conclusion stable enough to commit?
- How much provenance from peer influence should a commit preserve?
- How should the higher layer integrate conclusions that are each locally stable but mutually incompatible?
- Should integrated knowledge become the initialization of a later generation of agents?
- Can the same architecture recurse, with higher-level integrations themselves acting as local agents in a larger system?

These are part of the theory's future development rather than implementation obligations for the original proposal.

## 12. Conclusion

BECA is best summarized as:

> **The same initial worldview is distributed into multiple agents that evolve in different parts of one shared world. They may communicate throughout that evolution. Their mutable states remain locally owned. Once an agent reaches a stabilized conclusion, it commits that result to a higher layer, where multiple source conclusions undergo second-stage integration.**

The theory therefore does not seek isolated intelligence. It seeks **differentiated intelligence with a common origin**.

Its core architectural sequence is:

> **common origin -> situated divergence -> communication -> local evolution -> stable commit -> second-stage integration -> shared knowledge evolution**

This repository presents that sequence as a theory and architecture proposal for others to formalize, implement, criticize, or test.

## References (initial)

1. H. Brendan McMahan, Eider Moore, Daniel Ramage, Seth Hampson, Blaise Agüera y Arcas. *Communication-Efficient Learning of Deep Networks from Decentralized Data.* AISTATS, 2017.
2. L. D. Erman, F. Hayes-Roth, V. R. Lesser, D. R. Reddy. *The Hearsay-II Speech-Understanding System: Integrating Knowledge to Resolve Uncertainty.* ACM Computing Surveys.
3. *Transactional blackboards.* Artificial Intelligence in Engineering, 1(2), 1986.
4. Martin Fowler. *Event Sourcing.* 2005.
