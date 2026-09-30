# BECA Architecture

## 1. Design objective

BECA separates two different kinds of computation that are often mixed together:

1. **local cognitive evolution**, where information is allowed to remain unstable and change repeatedly;
2. **cross-source knowledge integration**, where only already-stabilized outputs are compared and merged.

The architecture is built around the assumption that these two processes should not share the same mutability rules.

## 2. System layers

```text
+---------------------------------------------------------+
|                    Shared / Parent Layer                |
|                                                         |
|  common initialization   global knowledge   governance  |
+------------------------------+--------------------------+
                               |
                               v
+---------------------------------------------------------+
|                    Agent Population                     |
|                                                         |
|   +-----------+   +-----------+   +-----------+         |
|   | Agent A   |   | Agent B   |   | Agent C   |         |
|   | mutable   |   | mutable   |   | mutable   |         |
|   | local     |   | local     |   | local     |         |
|   | state     |   | state     |   | state     |         |
|   +-----+-----+   +-----+-----+   +-----+-----+         |
|         |               |               |               |
+---------+---------------+---------------+---------------+
          |               |               |
          v               v               v
        Commit A        Commit B        Commit C
          \               |               /
           \              |              /
            +-------------+-------------+
                          |
                          v
+---------------------------------------------------------+
|                 Integration Layer                       |
|                                                         |
|  compare -> validate -> detect conflict -> abstract     |
|           -> generalize -> propose shared update        |
+------------------------------+--------------------------+
                               |
                               v
                     Shared state revision
```

## 3. Why the boundary matters

The agent boundary is not merely a privacy boundary. It serves four architectural purposes.

### 3.1 Mutation isolation
An agent may change its belief many times without forcing the entire system to react to every local revision.

### 3.2 Error containment
A temporary local error remains local until it survives the agent's own processing and commit rule.

### 3.3 Independent exploration
Different agents can arrive at different conclusions without being prematurely pulled toward one another by shared provisional state.

### 3.4 Provenance preservation
The higher layer receives distinguishable conclusions from distinct information histories.

## 4. Information lifecycle

```text
Environment
   |
   v
Raw observation
   |
   v
Local interpretation V1
   |
   v
Contradiction / new evidence
   |
   v
Local interpretation V2
   |
   v
Reframing / compression / relation-building
   |
   v
Local interpretation Vn
   |
   v
Stabilization criterion satisfied
   |
   v
COMMIT Cn
   |
   v
Second-stage integration
```

A key design decision is that `V1 ... Vn` are not global knowledge objects. They are local working states.

## 5. Stable does not mean permanent

A commit is stable relative to one completed local processing cycle, not necessarily correct forever.

Future local work may produce a later commit. The later commit should supersede the earlier one rather than mutate it in place.

This gives BECA a history of stable states without requiring knowledge to stop evolving.

## 6. Integration is not replay

The higher layer should not need to replay each agent's entire cognitive history. Its task is narrower:

- identify agreement across independent sources;
- identify disagreement and scope differences;
- determine whether two conclusions are duplicates, refinements, or contradictions;
- decide which information is globally useful;
- produce a higher-level abstraction when possible.

This makes the agent a first-stage processor rather than a raw-data relay.

## 7. Two channels

A practical system can separate traffic into two channels.

### Operational channel
Fast, mutable, non-authoritative messages used for coordination.

Examples:

- task assignment;
- liveness;
- resource negotiation;
- safety interrupts;
- routing metadata.

### Knowledge channel
Slower, versioned, provenance-preserving messages used to modify shared learned state.

Examples:

- stabilized local conclusions;
- validated local model deltas;
- compressed rules;
- reusable solution patterns.

BECA constrains the knowledge channel, not necessarily the operational channel.

## 8. Relation to lifecycle

For long-lived agents, a commit can happen many times.

For bounded agents, one useful interpretation is:

```text
create -> explore -> evolve -> stabilize -> final commit -> terminate
```

In that form, an agent lifecycle behaves like a transaction boundary: local state is mutable while the transaction is active, then a final result becomes immutable at commit.

This lifecycle interpretation is optional. BECA does not require biological metaphors or a single final commit.

## 9. Main design trade-off

BECA deliberately trades some immediacy for isolation.

Potential benefits:

- reduced propagation of provisional errors;
- lower global churn;
- stronger source independence;
- easier provenance tracking;
- clearer conflict handling.

Potential costs:

- delayed useful information;
- duplicated work across agents;
- difficulty defining stabilization;
- possible loss of beneficial early collaboration;
- lower performance in tasks that require continuous shared adaptation.

The architecture should therefore be evaluated empirically rather than assumed to dominate dynamic-sharing systems.
