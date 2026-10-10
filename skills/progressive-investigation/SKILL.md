---
name: progressive-investigation
description: Use when a problem has material uncertainty, competing explanations, causal/dependency structure, conflicting evidence, path-invalidating assumptions, cross-boundary effects, or repeated work whose progress is unclear.
---
# Progressive Investigation
A domain-general reasoning control law for **identifying the real problem under partial observability**, reducing decision-relevant uncertainty, and controlling the investigation process when it drifts, stalls, or becomes self-referential.
[references/AGENT.md](references/AGENT.md) is normative. [references/FOUNDATION-NOTE.md](references/FOUNDATION-NOTE.md) records immutable design intent and scope boundaries; it is not versioned with the skill.
## Using the bundled references
Read [AGENT.md](references/AGENT.md) for the operational contract. Use the relevant existing protocol when its condition arises: [PERSISTENT-STATE.md](references/PERSISTENT-STATE.md) for consequential longitudinal work, resumption or a material baseline change; [FEATURE-INTEGRITY.md](references/FEATURE-INTEGRITY.md) for material review, proposed closure or signs of whole-purpose drift; [LOOP-BREAK.md](references/LOOP-BREAK.md) when effort continues without material decision progress. These references refine the loop below; they do not add an approval stage or require a new record format. [MODEL.md](references/MODEL.md) explains the model. [TESTS.md](references/TESTS.md) is for behavioral evaluation, and [FOUNDATION-NOTE.md](references/FOUNDATION-NOTE.md) preserves design intent during maintenance.
## Architecture
Progressive Investigation has two core layers.
### Layer A — Epistemic Engine
Answers:
> What is actually happening, and what should be learned next?
It owns:
- observations and evidence;
- competing hypotheses;
- causal / dependency / bottleneck models;
- frontier selection;
- discriminating probes;
- falsification;
- model updates;
- causal depth;
- sufficiency.
### Layer B — Meta-Control
Answers:
> Is the investigation process itself still working?
It owns:
- anchoring and staleness;
- drift;
- progress versus activity;
- investigation cost;
- loops and model reset;
- recursive-control closure;
- optionality;
- termination.
### Domain adapters — outside the core
Domains may supply:
- terminology;
- thresholds;
- authority structures;
- lifecycle states;
- tools;
- execution procedures;
- persistence formats.
Adapters instantiate the formula. They do not redefine it.
## Core state
Conceptually:
```plain text
Sₜ = { G, B, M, E, U, C, X, P }
```
- **G — Goal / purpose**
- **B — Boundary / baseline**
- **M — Model**
- **E — Evidence**
- **U — Uncertainty**
- **C — Constraints**
- **X — Available probes/actions**
- **P — Material decision progress**
The representation is domain-dependent. The distinctions are not.
## Canonical loop
```plain text
ASSESS → ANCHOR → MODEL → FRONTIER → PROBE → UPDATE → RECONCILE → DECIDE
```
## Epistemic Engine rules
### Probe selection
```plain text
ProbeValue(q)
≈ ExpectedDecisionImpact(q)
 + ExpectedModelDiscrimination(q)
 - Cost(q)
 - Risk(q)
```
Use this ordinally; fake precision is unnecessary.
Prefer probes with materially positive information value.
### Causal / bottleneck depth
Descend one layer deeper only when deeper structure can materially change:
- the decision;
- the intervention;
- the identified binding constraint;
- model validity;
- or closure evidence.
Do not stop at the first plausible cause. Do not descend after additional depth loses decision value.
### Generalization
A finding may be isolated or structural.
Test the smallest discriminating set of neighboring/equivalent states needed to determine whether a shared mechanism matters.
Do not patch only the visible instance when evidence supports a broader mechanism; do not expand to an unbounded theoretical family without evidence.
### Sufficiency
**Minimum Sufficient Understanding** is reached when remaining material uncertainty is unlikely to change the purpose-relevant decision enough to justify another probe.
It is not minimum investigation.
## Action rule
Among authorized actions that satisfy proven constraints, prefer the least expansive and least irreversible:
```plain text
x* = argmin [
  Scope(x)
  + Irreversibility(x)
  + Cost(x)
  + Risk(x)
]

subject to:
  RequiredConstraintsSatisfied(x)
  and AuthorityAllows(x)
```
Ordinal comparison is sufficient.
Understanding may expand. Action must earn expansion.
## Meta-Control rules
### Drift
```plain text
Drift = MaterialDivergence(
  CurrentWhole,
  CanonicalPurposeAndConstraints
)
```
A sequence of locally reasonable steps can still drift globally.
### Progress
Progress is a material improvement in decision state:
- uncertainty reduced;
- alternatives discriminated;
- contradiction resolved;
- bottleneck better identified;
- required evidence obtained;
- action space better bounded.
Activity alone is not progress.
### Loop / model reset
```plain text
ΔP ≈ 0
while Effort > 0
and Model/Strategy ≈ unchanged
```
The observation window and tolerance are policy parameters.
When the applicable stall condition is met, change the model, boundary, assumptions, decomposition, or strategy rather than merely increasing effort.
### Recursive Control Closure
A control process may itself become the object of control:
```plain text
C(x), C(C(x)), C(C(C(x))), ...
```
Do not instantiate another meta-layer merely because recursion is logically possible.
Add another control layer only when its expected protection is materially positive:
```plain text
MetaControlValue(k+1)
≈ ExpectedRiskReduction
 - ControlCost
 - DelayCost
 - AddedFailureSurface
```
Core invariants:
1. **No unbounded control recursion.**
2. **Meta-level elevation does not itself create additional authority.**
3. **Reuse a stable higher-level rule when it already closes the recursion; do not create approval-of-approval chains without new decision value.**
4. **When another control layer has non-positive marginal value, stop recursion and use the least-commitment safe state permitted by existing authority, or defer to the appropriate external authority.**
5. **A recursion escape is a bounded control path, not an ad-hoc bypass.**
Exact recursion depth and escalation thresholds are domain policy, not universal constants.
### Optionality
Under material uncertainty, prefer:
```plain text
observation
→ reversible/discriminating probe
→ bounded reversible action
→ irreversible commitment
```
unless safety, timing, or external constraints justify otherwise.
## Epistemic constraints
Never silently convert:
```plain text
observation → broader fact
correlation → causation
inference → proof
repeated reporting → independent evidence
temporary recovery → causal resolution
working intervention → confirmed explanation
assumption → verified dependency
test PASS → semantic completeness
local PASS → global integrity
control recursion → automatic authority expansion
```
## Completion
Distinguish:
- operational sufficiency;
- explanatory sufficiency;
- integrity sufficiency;
- action/mutation sufficiency;
- irreducible uncertainty.
The framework succeeds when it learns enough of the right things, commits no more than justified, and can detect when its own reasoning/control process has stopped adding value.
