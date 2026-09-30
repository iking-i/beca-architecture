# BECA — Bounded Evolutionary Commit Architecture

> A conceptual architecture in which multiple agents share a common initial worldview, evolve in different local regions of the same world, communicate during that evolution, and expose only stabilized conclusions to higher-level knowledge integration.

**Status:** v0.1 conceptual specification — open for critique, implementation, and falsification.

## Core idea

BECA separates three things that are often mixed together:

1. **shared origin** — agents begin from the same or compatible initial state, rules, ontology, and world model;
2. **local evolution** — each agent occupies a different position in the same world and develops through its own local experience;
3. **higher-level integration** — the parent system integrates stabilized conclusions from multiple evolved agents rather than continuously fusing every temporary internal change.

The key rule is:

> **Dynamic information may evolve and be communicated between agents, but it does not become authoritative shared knowledge until it is stabilized and committed.**

Communication is therefore not forbidden. The boundary protects ownership and mutability of local cognition; it is not a wall that prevents interaction.

## Shared world, different local trajectories

BECA does not assume that agents live in unrelated environments. A stronger formulation is:

```text
                 Common initial state M0
        shared rules / ontology / worldview
                          |
          +---------------+---------------+
          |               |               |
          v               v               v
      Agent A         Agent B         Agent C
      region A        region B        region C
          |               |               |
          +<---- peer communication ----->+
          |               |               |
       local            local            local
      evolution        evolution        evolution
          |               |               |
      Final A         Final B         Final C
          \               |               /
           \              |              /
            +------ stable COMMIT --------+
                          |
                          v
                Second-stage integration
             compare / validate / dedupe /
          resolve conflict / abstract / generalize
                          |
                          v
                    shared-state update
```

The agents are not copies performing the same computation. They are common-origin systems exposed to different parts, events, relations, and histories within one larger world.

## Why the boundary matters

An agent boundary does **not** mean "do not talk to other agents." It means:

- the agent owns its mutable internal state;
- outside messages enter as new input and may change that state;
- the agent may send provisional messages to peers;
- provisional peer messages are not automatically treated as global truth;
- only an explicit commit makes a conclusion eligible for higher-level integration.

This preserves local evolution without requiring social or informational isolation.

## Information lifecycle

Inside one agent, information may change repeatedly:

```text
observation
  -> provisional interpretation
  -> peer message / contradiction / new evidence
  -> revision
  -> new relation
  -> compression
  -> locally stabilized conclusion
```

That entire changing process can be rich, interactive, and social.

The higher layer receives a different kind of object:

```text
Agent A -> committed conclusion A
Agent B -> committed conclusion B
Agent C -> committed conclusion C
                 |
                 v
        second-stage integration
```

The point is not to eliminate communication. The point is to prevent **unfinished local change from being fused as if it were already a settled cross-source conclusion**.

## Five principles

### 1. Common initial worldview
Agents begin from the same or mutually compatible baseline: shared rules, ontology, inherited knowledge, protocols, and basic model of the world.

### 2. Situated local evolution
Agents experience different local parts of the same world. Their histories therefore diverge even though their origin is shared.

### 3. Communicating boundaries
Agents may exchange observations, questions, hypotheses, warnings, and provisional interpretations. Communication becomes input to local evolution; it does not erase local state ownership.

### 4. Stable commit
Only a locally stabilized conclusion is eligible for higher-level knowledge integration. A commit is versioned and immutable for that completed processing cycle.

### 5. Second-stage integration
The parent/integration layer compares multiple committed sources, resolves conflicts, removes duplication, identifies scope, abstracts common structure, and decides what should modify shared knowledge.

## Data, experience, and shared knowledge

BECA distinguishes:

- **data** — observations or messages that can be transmitted directly;
- **experience** — information transformed through a local agent's changing history;
- **committed conclusion** — a locally stabilized result;
- **shared knowledge** — the result of second-stage processing across multiple committed sources.

This gives a two-stage knowledge process:

```text
same world
   |
   +--> local agent evolution --> stable conclusion --+
   +--> local agent evolution --> stable conclusion --+--> second-stage integration --> shared knowledge
   +--> local agent evolution --> stable conclusion --+
```

## What BECA is not

BECA is **not** an architecture of isolated agents.

Agents may communicate frequently. They may influence one another. They may cooperate on tasks. They may exchange unfinished ideas.

The restriction is narrower:

> **A changing local cognitive state must not be mistaken for a finalized source contribution to the higher-level shared knowledge base.**

A message from Agent A can change Agent B. But that message does not directly overwrite the parent system. Agent B still processes it within B's own evolving state; A and B later submit their stabilized results as distinguishable sources.

## Central hypothesis

> A multi-agent system can preserve rich interaction while reducing cross-source fusion errors by separating **peer communication during local evolution** from **stable knowledge commits used for higher-level integration**.

BECA therefore treats the agent as both:

- a participant in a shared world, and
- a bounded evolutionary processor whose internal state remains locally mutable.

## Open questions

BECA v0.1 intentionally leaves several mechanisms open:

- how much of the common initial worldview must be identical;
- how agents should represent local position or perspective in the shared world;
- which peer messages should be retained, ignored, trusted, or challenged;
- how an agent decides that a conclusion is stable enough to commit;
- whether a commit should contain a conclusion, evidence, confidence, scope, model delta, or some combination;
- how the higher layer should integrate individually stable but mutually incompatible conclusions;
- how integrated knowledge should influence future generations or future initialization states.

## Repository map

- [`SPEC.md`](SPEC.md) — normative concepts, invariants, and terminology
- [`ARCHITECTURE.md`](ARCHITECTURE.md) — system structure and information lifecycle
- [`EXPERIMENTS.md`](EXPERIMENTS.md) — optional ways others could test the theory
- [`PRIOR_ART.md`](PRIOR_ART.md) — adjacent architectures and distinctions
- [`CONTRIBUTING.md`](CONTRIBUTING.md) — how to critique, implement, or extend BECA
- [`paper/BECA_v0.1.md`](paper/BECA_v0.1.md) — conceptual paper draft

## Invitation

BECA is presented as a theory and architecture proposal. Others are welcome to implement it, challenge it, formalize it, or test where it fails.

The intended contribution is the architectural separation itself:

> **common origin + shared world + local evolutionary boundaries + peer communication + stable commit + second-stage multi-source integration**.
