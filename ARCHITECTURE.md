# BECA Architecture

## 1. Design objective

BECA separates three layers that should not be confused:

1. **common origin**, where multiple agents inherit the same initial state;
2. **situated local evolution**, where those agents occupy different parts of the same world, communicate, and change through different local histories;
3. **higher-level integration**, where information from local states that are no longer changing is processed together.

The architecture is not based on agent silence. It is based on separating **ongoing local change** from **higher-level integration after that local change stops**.

## 2. System structure

```text
+---------------------------------------------------------+
|                    Parent / Shared Layer                |
|                                                         |
|      one common initial state M0                        |
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
 change stops          change stops          change stops
       |                    |                    |
       v                    v                    v
 closed state A        closed state B        closed state C
       \                    |                    /
        \                   |                   /
         +------------------+------------------+
                            |
                            v
+---------------------------------------------------------+
|                 Second-stage Integration                |
|                                                         |
| compare -> combine -> conflict -> abstract -> generalize|
+------------------------------+--------------------------+
                               |
                               v
                     Shared state M1
```

## 3. Same world, different positions

The agents begin from the same initial state and then experience different local parts of one coherent environment:

```text
M0 = common initial state

A(t) = M0 transformed by local history in region A + peer influence
B(t) = M0 transformed by local history in region B + peer influence
C(t) = M0 transformed by local history in region C + peer influence
```

Their value comes from the divergence of those histories.

Different agents may encounter different:

- events;
- local constraints;
- relationships;
- evidence ordering;
- failures;
- opportunities;
- messages from peers.

## 4. Why the boundary matters

The agent boundary is not a communication wall. It is a boundary around **locally mutable evolution**.

### 4.1 Mutable-state ownership
An agent may revise its own internal state repeatedly without every revision becoming higher-level state.

### 4.2 Peer influence without automatic integration
A message from Agent A can change Agent B, but the message enters B as input. It does not directly become a higher-level integration input.

### 4.3 Local interpretation
Each agent may interpret, reject, combine, reinforce, weaken, or revise information received from both the world and peers.

### 4.4 Finite local lifecycle
A local process does not need an explicit task in order to end.

It may stop changing because:

- repeated information no longer produces meaningful change;
- existing structure becomes dominant enough that new low-weight information does not alter it;
- the process reaches a practical fixed point;
- the agent reaches a finite lifetime boundary;
- a time/resource boundary is reached;
- an external controller or human ends the process.

The important point is not that the system has produced a result, but that the relevant local state is no longer changing.

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
local state V1
        |
new evidence / disagreement / peer influence
        |
        v
local state V2
        |
reframing / reinforcement / weakening / relation-building
        |
        v
local state Vn
        |
local change stops
        |
        v
closed local state
        |
        v
second-stage integration
```

The critical distinction is that `V1 ... Vn` belong to an active local process. A closed local state may still be incomplete, contradictory, or wrong. Closure only means that the source local process no longer changes it.

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

What it does not do automatically is become a higher-level integration input merely because it was sent.

```text
communication -> influence local evolution

cessation of local change -> closed local state -> higher-level integration
```

## 7. Closure does not mean truth, completion, or correctness

A closed local state is final only relative to the local process that has ended.

It may still contain:

- uncertainty;
- contradiction;
- error;
- missing information;
- unresolved structure.

A later generation or later shared state may evolve differently.

## 8. Second-stage integration

The higher layer performs a different kind of processing from local evolution.

Its task is to operate across already-closed local states:

- identify agreement;
- identify conflict;
- remove duplication;
- discover relations;
- combine partial structures;
- abstract common structure;
- generalize beyond one local history;
- produce a new shared state.

The higher layer does **not** need to reconstruct the individual that produced each closed state.

Source identity, provenance, or detailed history may be retained for debugging, auditing, trust, or analysis, but BECA does not require them as theoretical invariants.

## 9. Why multiple agents matter

If every agent began from a different base, differences could come from incompatible starting assumptions rather than local evolution.

If every agent began identically and experienced the exact same history, the population would add little exploratory value.

BECA therefore emphasizes:

```text
same initial state
        +
different local trajectories
        +
peer interaction
        +
cessation of local change
        =
multiple closed local states
```

The higher layer can then process those states into a new shared state.

## 10. Generational cycle

BECA naturally supports a repeated cycle:

```text
M0
 -> distribute same initial state
 -> differentiated local evolution
 -> local change stops
 -> closed local states
 -> second-stage integration
 -> M1
 -> distribute M1 into a later generation
 -> ...
```

This allows the whole system to evolve without requiring every local intermediate change to become global state.

## 11. Main design trade-off

Potential benefits include:

- preserving local evolutionary processes;
- preventing every provisional change from becoming global state;
- allowing communication without collapsing all local state into one shared mutable pool;
- allowing finite local lifecycles to create closed states;
- making higher-level integration operate on information that is no longer changing at its source.

Potential costs include:

- delayed higher-level updates;
- difficulty determining whether a local state has effectively stopped changing;
- possible duplication of work;
- peer influence may still correlate errors;
- some tasks may benefit more from continuous global adaptation.

BECA is therefore a theory about information lifecycle and processing boundaries, not a claim that delayed integration is universally superior.
