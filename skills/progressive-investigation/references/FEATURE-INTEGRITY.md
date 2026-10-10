# Feature / System Integrity Protocol
> Deep specification for the **RECONCILE** phase: detecting material divergence between the current whole and the canonical purpose/constraints.
## Role
This protocol is domain-general. It does not prescribe Issue, PR, Repair, or any other software-specific lifecycle.
[AGENT.md](AGENT.md) governs.
## 1. Integrity question
Do not ask only:
> Is the latest local step correct?
Ask:
> Does the current whole still satisfy the canonical purpose, constraints, and required evidence?
## 2. Reconciliation surfaces
A useful general model is:
```plain text
CANONICAL PURPOSE / CONSTRAINTS
            ↕
CURRENT MODEL / DECISIONS
            ↕
CURRENT SYSTEM / IMPLEMENTATION REALITY
            ↕
CURRENT EVIDENCE / COVERAGE
```
Some domains may add an authority/reference layer.
Misalignment between material surfaces is evidence of drift or unresolved uncertainty.
## 3. Integrity state
Represent material requirements as:
```yaml
requirement:
  statement:
  type:
  evidence:
  status: PASS | FAIL | UNKNOWN
  invalidation_conditions:
```
Where:
- **PASS** — current evidence demonstrates satisfaction;
- **FAIL** — current evidence demonstrates contradiction;
- **UNKNOWN** — evidence is missing, stale, indirect, or insufficient.
UNKNOWN is not a softer PASS.
## 4. Structural generalization
A concrete failure may be isolated or may reveal a broader mechanism.
When this distinction matters:
1. identify the shared causal/dependency/invariant structure;
2. choose the smallest discriminating set of neighboring/equivalent states;
3. test whether the explanation generalizes;
4. expand the model only as far as evidence and decision value justify.
Do not:
- project one instance into a whole class without evidence;
- or treat one fixed instance as proof that a demonstrated broader mechanism is resolved.
## 5. Drift
Conceptually:
```plain text
Drift = MaterialDivergence(
  CurrentWhole,
  CanonicalPurposeAndConstraints
)
```
Potential drift dimensions include:
- semantics;
- assumptions;
- state/baseline;
- authority/reference facts;
- implementation/system behavior;
- evidence coverage;
- external dependencies;
- decision criteria.
No universal numeric distance is required.
## 6. Reconciliation triggers
Reconcile when it is decision-relevant, including:
- material baseline/state change;
- material assumption change;
- scope/boundary change;
- evidence invalidation;
- repeated structurally related failures;
- resumption after stale/incomplete state;
- proposed closure;
- policy-defined cadence for long-running work;
- evidence that local progress may not compose globally.
The exact cadence and threshold are domain policy, not universal law.
## 7. Necessity at the action boundary
Before consequential action, test proposed components for necessity:
> If this component is removed, which proven requirement, invariant, safety condition, or required evidence path fails?
Classify conceptually:
- **NECESSARY** — removal breaks a proven requirement;
- **SUPPORTING** — needed to realize another necessary component;
- **UNPROVEN** — necessity is not yet established;
- **OUTSIDE CURRENT PURPOSE** — useful or valid, but not required now.
This prevents investigation breadth from automatically becoming action breadth.
## 8. Semantic acceptance
Acceptance requires, when applicable:
1. canonical purpose is still valid or explicitly revised;
2. required constraints are PASS;
3. required evidence is current;
4. material UNKNOWNs are resolved or explicitly accepted;
5. cumulative drift has been considered;
6. the proposed action is sufficient and no broader than justified.
A test suite, checklist, or local review can be evidence. None is automatically equivalent to whole-system correctness.
## 9. Fail-closed behavior
If material surfaces contradict each other:
- do not preserve momentum by assuming the favorable interpretation;
- return to MODEL / FRONTIER / PROBE;
- or reconsider the model if progress has stalled.
Integrity review exists to protect the whole from locally convincing but globally wrong conclusions.
