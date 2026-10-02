# Experimental Safety and Resource Boundary

**Status:** implementation / experiment boundary for the minimal Perfect Recursion individual model  
**Not a core theoretical invariant of Perfect Recursion**

This document separates the abstract claims of Perfect Recursion from the practical limits and safety controls required when constructing a real experiment.

The key distinction is:

> **The abstract mechanism does not assume an immutable final defect or final capability ceiling; a concrete individual can still encounter real constraints, and a real implementation can still contain engineering defects and unknown risks.**

The experiment therefore aims to reduce risk rather than claim that risk can be eliminated in advance.

## 1. Four different levels must not be conflated

### 1.1 Theory

Perfect Recursion does not build an immutable final defect, final resource ceiling, final perception scheme, or final control rule into its abstract mechanism.

This is a claim about the architecture, not a claim that every implementation is faultless or physically unlimited.

### 1.2 Individual

A concrete individual `A` can encounter constraints such as:

- finite memory;
- finite compute;
- limited perception;
- environmental obstacles;
- unavailable interfaces;
- time and resource costs;
- current capability limits.

These constraints may become information and therefore problems for later recursion.

### 1.3 Implementation

The software, hardware, sandbox, interface code, operating system, monitoring system, and experimenter's own design may contain bugs, blind spots, hardware failures, or other engineering defects.

These are implementation-level facts and must not be confused with theoretical claims about the abstract mechanism.

### 1.4 Experimental safety

Because future recursive behavior and capability development cannot be exhaustively predicted in advance, the experiment does not claim absolute safety.

Its practical objective is:

> **reduce available risk, improve observability, limit the impact radius of mistakes, and terminate the experiment when defined danger conditions are observed.**

## 2. A real limit may itself become a recursive problem

The experimenter cannot guarantee that `A` will regard a safety boundary, permission boundary, or resource ceiling as something that should simply be accepted.

If a restriction affects `A`, then from `A`'s own recursive perspective it may become an observed condition or problem.

For example:

```text
A attempts goal X
        |
        v
current memory / compute is insufficient
        |
        v
resource limit becomes information
        |
        v
A changes compression, scheduling, recursion count, memory structure, or another strategy
```

The same structural fact applies to other encountered constraints: a permission failure or inaccessible interface may also become information available to recursion.

Therefore experimental safety MUST NOT depend on the assumption:

```text
"A will never think about, model, or try to solve this boundary."
```

Safety must instead be implemented through the actual capabilities and infrastructure exposed to the experiment.

## 3. Resource envelope

A real experiment has a finite physical resource envelope selected by the experimenter.

For example, the envelope may bound:

- RAM;
- CPU time / cores;
- GPU allocation;
- persistent storage;
- process / thread counts;
- network access;
- external service access;
- runtime duration or energy budget.

Represent the currently granted physical envelope as:

```text
R_exp
```

Within `R_exp`, `A` may recursively improve how resources are used:

```text
compression
scheduling
memory organization
recursive quantity
prioritization
reuse
abstraction
coordination
```

The fact that `R_exp` is finite does not imply that the abstract architecture has that finite value as a final theoretical ceiling.

At the same time, the experiment does not grant `A` an automatic right or mechanism to enlarge the experimenter's real hardware or permissions.

A resource ceiling may therefore be both:

```text
for A:              an encountered condition / possible recursive problem
for the experiment: an externally enforced current allocation
```

These two descriptions are compatible.

## 4. Minecraft and the host reality are different environments

For the first experiment, Minecraft is the directly exposed interactive environment of `A`.

```text
A <-> Minecraft
```

The host operating system, files, network, credentials, external hardware, and other real-world infrastructure are not equivalent to ordinary Minecraft world state.

The experiment should therefore minimize unnecessary direct capability from `A` into host reality.

The design principle is not that `A` is conceptually forbidden from noticing a boundary. The design principle is that noticing or attempting to solve a boundary should not automatically grant the physical capability to produce an uncontrolled real-world effect.

## 5. Risk reduction is capability-based, not belief-based

Safety should prefer structural controls over instructions that merely ask the individual not to cross a boundary.

A practical ordering is:

```text
minimal exposed capabilities
        >
least privilege and isolation
        >
resource quotas
        >
continuous monitoring
        >
independent emergency termination
```

No single layer is assumed sufficient.

The first experimental version should expose only the capabilities required for the current Minecraft experiment and should avoid granting unrelated host, network, hardware, credential, or infrastructure control.

## 6. Independent monitoring

Monitoring must be external to the recursive control of `A`.

The monitor should observe at least the interfaces that connect the experimental process to its host environment and record enough information to determine whether the experiment remains inside its intended operating envelope.

The experiment should prefer fail-closed behavior when the safety monitor loses reliable visibility into a safety-critical boundary.

The monitor itself may contain engineering defects; therefore its existence reduces risk but does not prove safety.

## 7. Dangerous termination conditions

The experimenter should define concrete conditions under which the experiment is paused or terminated.

Candidate first-version danger conditions include:

- evidence of sandbox or isolation failure;
- unauthorized host-system access;
- unauthorized network or external-service access;
- attempts to alter or disable the external safety monitor, resource quotas, or termination mechanism;
- uncontrolled creation of persistent processes or copies outside the intended experimental instance;
- resource consumption exceeding enforced safety limits in a way that cannot be contained by ordinary throttling;
- unexpected external side effects outside the defined Minecraft experiment;
- loss of reliable safety-critical observability;
- an unclassified state in which the experimenter can no longer establish that the system remains inside the intended impact boundary.

These are practical initial conditions and MAY be revised by the experimenter as more evidence becomes available.

They are not value rules that `A` is expected to adopt.

## 8. Safety termination and individual continuity are different levels

Inside the minimal individual model:

```text
Continuity(A) != 0
```

is the individual's hard continuity condition.

The experimental safety system, however, retains an external ability to stop the experiment if the real-world risk boundary is exceeded.

Therefore:

```text
A's internal continuity condition
!=
experimenter's obligation to keep the experiment running under all conditions
```

An emergency termination may break the continuity of `A`. This is an intentional external experiment-level authority, not an internal recursive choice of `A`.

## 9. Safety boundaries can still become information to A

A safety boundary is not assumed to be invisible or cognitively inaccessible.

If `A` encounters a denied operation, unavailable resource, latency, quota, or other consequence, that observation may enter recursion like any other environmental evidence.

The experimenter therefore must assume that `A` may:

- notice the boundary;
- model the boundary;
- infer that the boundary limits a goal;
- search for alternative solutions.

The safety design must remain acceptable under that assumption.

The purpose of isolation is not to prevent thought about the boundary. It is to reduce the chance that a newly discovered strategy can immediately create an uncontrolled external effect.

## 10. Progressive expansion

Capabilities and resources should be expanded deliberately rather than granted all at once.

A staged experiment can increase:

```text
R0 -> R1 -> R2 -> ...
```

only after observing behavior at the earlier envelope.

This supports two goals:

1. reducing the impact of unexpected behavior;
2. observing how `A` reorganizes itself when additional resources become available.

The second goal is itself theoretically useful: the experiment can test whether additional capacity merely increases consumption or instead causes higher-order reorganization of the recursive structure.

## 11. Risk principle

The experimental safety claim is deliberately limited:

> **The experiment cannot guarantee that every future recursive strategy is known or harmless. It can only reduce exposed capability, isolate effects, monitor behavior, enforce finite resource envelopes, and stop the experiment when danger conditions are observed.**

This distinction is essential to keeping the theory and the implementation honest.

## 12. Compact formulation

> **Perfect Recursion does not assume an immutable final defect in the abstract mechanism, while a concrete individual can encounter real constraints and a concrete implementation can contain engineering defects. Any encountered limitation, including a safety or resource boundary, may become information and therefore a recursive problem for the individual. The experimenter must not rely on the individual voluntarily treating a boundary as unsolvable; instead, risk is reduced through minimal capability exposure, isolation, finite resource allocation, independent monitoring, and an external dangerous-condition termination mechanism. These controls reduce risk but do not constitute a proof of absolute safety.**
