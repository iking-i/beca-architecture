# BECA Experiments

This document defines a first set of experiments intended to **test and potentially falsify** BECA rather than merely demonstrate it.

## 1. Core hypothesis

> In some multi-agent knowledge systems, allowing unfinished local information to participate in global fusion causes avoidable contamination, stale-version conflicts, premature consensus, and global churn. Delaying learned-knowledge transfer until a local stabilization condition is met can reduce those failures.

BECA should be rejected or narrowed if controlled experiments show that delayed stable commits provide no meaningful benefit, or systematically harm performance, compared with dynamic sharing.

## 2. Experimental design

Use the same task distribution, base model, agent count, local observations, compute budget, and integration budget across conditions.

### Condition A — Dynamic sharing baseline
Agents periodically expose intermediate learned state while their local reasoning or learning process is still changing.

### Condition B — BECA
Agents retain intermediate learned state locally. They publish only when a predeclared stabilization criterion is satisfied.

### Optional Condition C — No sharing
Agents never update a global knowledge layer. This provides a lower/alternative baseline for isolating the value of any integration at all.

## 3. Minimal synthetic task

Start with a deliberately small problem before using LLM agents.

### Environment
Each agent observes a noisy subset of rules mapping context features to outcomes.

Example:

```text
true rule set:
R1: if X and C -> Y
R2: if X and not C -> Z
R3: if D -> exception E
```

Each agent receives:

- incomplete observations;
- a controlled percentage of mislabeled examples;
- different local sample distributions;
- delayed contradictory evidence.

### Local learner
Any learner capable of revising a hypothesis over time can be used, for example:

- decision-rule learner;
- Bayesian updater;
- small neural classifier with interpretable snapshots;
- LLM reasoning agent with structured belief output.

### Stabilization rule
For the first BECA implementation, use a simple measurable rule rather than a vague semantic judgment.

Example:

```text
commit when:
- validation accuracy has not changed by more than epsilon
- for K consecutive local update rounds
- and contradiction count is below threshold T
```

This rule can later be replaced with confidence-, task-, or model-specific criteria.

## 4. Metrics

### 4.1 Knowledge contamination rate
How often does a globally accepted belief originate from a local belief that the source agent later retracts or supersedes?

Suggested measure:

```text
contamination_rate =
  globally_integrated_commits_later_retracted_by_source
  ---------------------------------------------------
  total_globally_integrated_source_updates
```

For dynamic-sharing systems, an intermediate update may count as a source update even if not explicitly called a commit.

### 4.2 Global churn
How often must the shared model or knowledge base revise previously integrated state because local sources changed?

### 4.3 Stale-version conflict
How often are two global operations performed using mutually inconsistent versions of the same source's local knowledge?

### 4.4 Recovery after local error
Inject a temporary but strong local false belief. Measure:

- whether it reaches the global layer;
- how many other agents become affected;
- how long the global system takes to recover.

### 4.5 Premature consensus
Give several agents correlated but incomplete early evidence pointing toward a wrong rule, then later reveal disconfirming evidence independently.

Measure whether early sharing causes agents to converge on the wrong rule before independent evidence is processed.

### 4.6 Final task performance
Evaluate accuracy/reward on held-out environments.

### 4.7 Communication volume
Measure bytes/messages/tokens sent on the knowledge-sharing channel.

### 4.8 Time-to-useful-global-knowledge
BECA may reduce contamination while delaying useful discoveries. Measure the latency from first local discovery to globally usable knowledge.

### 4.9 Diversity retention
Measure how long genuinely different hypotheses survive across agents before global integration collapses them into one shared view.

## 5. Critical falsification cases

BECA should not be treated as generally useful if one or more of the following repeatedly occurs across controlled tasks:

1. dynamic sharing achieves equal or lower contamination while converging faster;
2. BECA stabilization delay causes important information to arrive too late to be useful;
3. locally stabilized conclusions are no more reliable than intermediate states;
4. independence causes redundant exploration costs larger than any gain from isolation;
5. the integrator cannot meaningfully combine stable conclusions without needing the full local process history;
6. early cross-agent interaction consistently improves reasoning quality enough that isolation becomes a net loss.

## 6. LLM-agent experiment

After the synthetic experiment, evaluate with reasoning agents.

### Task family
Use tasks where evidence arrives sequentially and initial evidence is intentionally misleading.

Examples:

- diagnosis from staged evidence;
- debugging with misleading early logs;
- scientific hypothesis selection;
- mystery/inference tasks;
- classification with hidden context exceptions.

### Dynamic baseline
Every N reasoning steps, each agent publishes its current hypothesis to a shared workspace visible to all other agents.

### BECA condition
Agents reason independently. They may use an operational channel for task allocation but cannot see other agents' learned hypotheses until they locally commit.

After all commits, an integrator agent receives only:

- final conclusion;
- evidence summary;
- confidence;
- scope/assumptions.

### Main test
Determine whether the dynamic baseline exhibits stronger anchoring or correlated error when one early agent makes a persuasive but wrong provisional claim.

## 7. Ablations

BECA is not one indivisible mechanism. Test which part matters.

### A1 — Boundary only
Agents do not see each other's beliefs, but the global layer receives all intermediate updates.

### A2 — Commit only
Agents can see each other's beliefs, but only stabilized results update global learned state.

### A3 — Immutable versioning only
All updates may be shared, but every version remains source-labelled and immutable.

### A4 — Full BECA
Independent local dynamic state + stable immutable commit + second-stage source-aware integration.

These ablations can show whether the claimed benefit comes from independence, delayed commit, provenance, or their combination.

## 8. Reporting standard

Any implementation claiming evidence for or against BECA should publish:

- task/environment definition;
- source code;
- random seeds;
- agent initialization;
- local update rule;
- stabilization rule;
- commit schema;
- integration rule;
- communication budget;
- compute budget;
- all baselines;
- negative results.

## 9. First implementation target

The preferred first implementation is intentionally small:

```text
5-20 agents
simple rule-learning environment
controlled label noise
controlled delayed evidence
three sharing strategies
reproducible Python simulation
```

A small falsifiable result is more useful than a large demonstration whose mechanism cannot be isolated.
