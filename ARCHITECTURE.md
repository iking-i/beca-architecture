# BECA Architecture

## 1. Design objective

BECA separates three layers that should not be confused:

1. **common origin**, where agents inherit the same or mutually compatible initial worldview;
2. **situated local evolution**, where agents occupy different parts of the same world, communicate, and change through different local histories;
3. **higher-level knowledge integration**, where stabilized conclusions from multiple evolved sources are compared and synthesized.

The architecture is not based on agent silence. It is based on separating **communication during evolution** from **authoritative integration after stabilization**.

## 2. System structure

```text
+---------------------------------------------------------+
|                    Parent / Shared Layer                |
|                                                         |
|  common worldview   inherited rules   shared ontology  |
+------------------------------+--------------------------+
                               |
                               v
+---------------------------------------------------------+
|                    Shared World                         |
|                                                         |
|   region A             region B             region C    |
|      |                    |                    |         |
|   Agent A <----------> Agent B <----------> Agent C     |
|      |       peer communication / influence    |        |
|      |                    |                    |         |
|   local evolution     local evolution      local evolution
+------+--------------------+--------------------+---------+
       |                    |                    |
       v                    v                    v
    Commit A             Commit B             Commit C
       \                    |                    /
        \                   |                   /
         +------------------+------------------+
                            |
                            v
+---------------------------------------------------------+
|                 Integration Layer                       |
|                                                         |
| compare -> validate -> scope -> conflict -> abstract    |
|             -> generalize -> shared update              |
+---------------------------------------------------------+
```

## 3. Same world, different positions

The agents are not intended to inhabit unrelated worlds.

They begin with a common baseline and then experience different local parts of one coherent environment:

```text
M0 = common initial worldview

A(t) = M0 + history in region A + received peer influence
B(t) = M0 + history in region B + received peer influence
C(t) = M0 + history in region C + received peer influence
```

Their value comes from the divergence of those histories.

Different agents may encounter:

- different events;
- different local constraints;
- different relationships;
- different evidence ordering;
- different failures;
- different opportunities;
- different messages from peers.

They remain comparable because they share a common origin and world model.

## 4. Why the boundary matters

The agent boundary is not a communication wall. It is a boundary of **state ownership and authority**.

### 4.1 Mutable-state ownership
An agent may revise its own internal state repeatedly without every revision becoming parent-level knowledge.

### 4.2 Peer influence without automatic fusion
A message from Agent A can change Agent B, but the message enters B as input. It does not directly overwrite the parent system.

### 4.3 Local processing
Each agent decides how to interpret, reject, combine, or revise information received from both the world and peers.

### 4.4 Source preservation
When a conclusion is eventually committed, the integration layer can still distinguish which local trajectory produced it.

## 5. Information lifecycle

```text
common initialization
        |
        v
local position in shared world
        |
        v
observation / peer communication
        |
        v
local interpretation V1
        |
new evidence / disagreement / peer influence
        |
        v
local interpretation V2
        |
reframing / compression / relation-building
        |
        v
local interpretation Vn
        |
stabilization criterion satisfied
        |
        v
COMMIT Cn
        |
        v
second-stage integration
```

The critical distinction is that `V1 ... Vn` remain local working states even when some of their contents are communicated to peers.

## 6. Communication during evolution

BECA permits rich peer interaction.

Agents may exchange:

- observations;
- partial hypotheses;
- questions;
- critiques;
- warnings;
- requests for verification;
- coordination messages;
- provisional interpretations.

A peer message can cause substantial local change.

What it cannot do automatically is become a finalized higher-level knowledge contribution merely because it was sent.

This creates the distinction:

```text
communication -> influence local evolution

commit -> enter higher-level integration
```

## 7. Stable does not mean permanent

A commit is stable relative to one completed local processing cycle, not necessarily correct forever.

Future local work may produce a later commit. The later commit should supersede the earlier one rather than mutate it in place.

This preserves historical source states while allowing long-term knowledge to change.

## 8. Second-stage integration

The higher layer does not need to replay every internal thought of every agent.

Its task is to operate on already stabilized source contributions:

- identify agreement across different local trajectories;
- identify disagreement caused by scope or context;
- distinguish duplicate, refined, and contradictory conclusions;
- preserve provenance;
- decide which information is useful at the shared level;
- produce abstractions that no single local agent necessarily formed alone.

This is **second-stage processing**, not raw-data processing.

## 9. Why multiple agents matter

If every agent began differently, it would be difficult to determine whether divergent conclusions came from local experience or from incompatible starting assumptions.

If every agent began identically and experienced the exact same path, the population would add little exploratory value.

BECA therefore emphasizes:

```text
common initial state
        +
different local trajectories
        +
peer interaction
        =
differentiated evolved sources
```

The higher layer can then integrate what those sources learned.

## 10. Lifecycle interpretation

For long-lived agents, commits may happen repeatedly.

For bounded agents, one possible lifecycle is:

```text
initialize -> enter world -> evolve -> communicate -> stabilize -> final commit -> terminate
```

The lifecycle metaphor is optional. The architectural requirement is simply that local mutability and higher-level integration use different rules.

## 11. Main design trade-off

Potential benefits include:

- preserving local interpretive processes;
- preventing every provisional change from becoming global state;
- maintaining distinguishable source trajectories;
- allowing communication without collapsing all agents into one mutable knowledge pool;
- making higher-level integration operate on more mature source outputs.

Potential costs include:

- delayed parent-level updates;
- difficulty defining stabilization;
- possible duplication of work;
- peer influence may still correlate errors;
- some tasks may benefit more from continuous global shared adaptation.

BECA is therefore a theory about information boundaries and knowledge lifecycle, not a claim that delayed integration is universally superior.
