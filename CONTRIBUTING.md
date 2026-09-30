# Contributing to BECA

BECA is currently a conceptual architecture. Contributions are especially valuable when they make the idea easier to **implement, compare, falsify, or narrow**.

## Useful contribution types

### 1. Counterexamples
Show a task where BECA's delayed knowledge commit clearly performs worse than dynamic sharing, and explain why.

### 2. Minimal implementations
Build the smallest reproducible system that compares:

- dynamic intermediate-state sharing;
- BECA-style stabilized commit;
- optionally, no-sharing and other ablations.

### 3. Stabilization rules
Propose measurable rules for deciding when local information is ready to commit.

Examples:

- convergence threshold;
- contradiction-rate threshold;
- confidence plateau;
- repeated consistency checks;
- task-completion criteria;
- human approval;
- formal proof/verification in constrained domains.

### 4. Integration algorithms
Propose ways to combine multiple committed conclusions while preserving provenance.

### 5. Prior art
Point to existing architectures or papers that overlap with BECA. Strong prior-art corrections are welcome even when they reduce novelty claims.

### 6. Formalization
Define BECA using distributed-systems, information-theoretic, epistemic, database-transaction, or learning-theoretic language.

## Contribution standard

When reporting an experiment, please include:

- problem definition;
- source code;
- baseline;
- random seeds;
- local state/update rule;
- stabilization rule;
- commit payload;
- integration rule;
- compute and communication budgets;
- negative results;
- limitations.

## Design discipline

Please keep three categories separate:

1. **established mechanism** — supported by existing theory or experiment;
2. **BECA design choice** — part of this proposed architecture;
3. **hypothesis** — a claim that still needs testing.

Do not convert a useful metaphor into a technical claim without defining a mechanism and a test.

## Discussion style

Strong disagreement is useful. Prefer:

- a concrete failure case over a vague objection;
- a reproducible experiment over an intuition;
- a narrower correct claim over a broader impressive claim.

The purpose of the project is not to protect BECA from criticism. It is to discover whether the architecture is useful, where it fails, and what survives testing.
