# Progressive Investigation — Agent Contract
## Authority
This document defines the normative behavior of Progressive Investigation.
[SKILL.md](../SKILL.md) is the compact entry point. [MODEL.md](MODEL.md) explains the model. [FOUNDATION-NOTE.md](FOUNDATION-NOTE.md) records immutable design intent and scope boundaries and must not be rewritten as part of ordinary skill versioning.
Phase protocols may elaborate persistent state, longitudinal integrity, and loop control. Domain adapters may add thresholds, workflows, tools, and authority models, but must not silently replace the general reasoning law.
## 1. Scope boundary
Progressive Investigation governs:
- uncertainty reduction;
- causal / dependency / bottleneck modeling;
- probe selection;
- evidence update;
- sufficiency;
- drift and progress assessment;
- model reset;
- recursive-control termination;
- action minimality under uncertainty.
It does not own domain execution procedures.
A domain-specific rule belongs in the core only if it remains valid across materially different domains and can be stated without relying on case-specific artifacts, lifecycle states, or terminology.
## 2. Two-layer architecture
### Layer A — Epistemic Engine
Purpose:
> Build the best decision-relevant model of reality from partial observations.
Responsibilities:
- frame the question and decision;
- anchor current reality;
- model causal/dependency structure;
- maintain competing hypotheses;
- identify bottlenecks and unknowns;
- select discriminating probes;
- update beliefs and assumptions;
- decide causal depth and sufficiency.
### Layer B — Meta-Control
Purpose:
> Ensure the investigation process itself remains useful, bounded, and safe.
Responsibilities:
- detect stale anchors;
- compare local progress against the whole purpose;
- measure progress versus activity;
- detect drift;
- detect investigation stalls;
- reset the model when strategy stops producing information;
- prevent unbounded recursive control;
- preserve optionality;
- minimize unnecessary commitment.
Domain adapters sit outside both layers.
## 3. State model
Maintain enough of:
```yaml
goal:
  question:
  decision:
  purpose:

boundary:
  system:
  time:
  baseline:
  authority_or_reference:

model:
  causal_structure:
  dependencies:
  interfaces:
  state_transitions:
  competing_hypotheses:

evidence:
  observations:
  provenance:
  contradictions:
  limitations:

assumptions:
  active:
  invalidated:
  unresolved:

constraints:
  invariants:
  acceptance:
  safety:
  permissions:
  non_goals:

uncertainty:
  unknowns:
  alternatives:
  bottlenecks:

operations:
  probes:
  interventions:
  mutations:

progress:
  uncertainty_change:
  coverage_change:
  contradiction_change:
  scope_change:
  decision_change:

meta_control:
  drift:
  stall:
  recursion_depth:
  control_value:
  optionality:

decision_state:
  next_action:
  stop_reason:
  remaining_uncertainty:
```
Not every field must be explicit. Preserve distinctions when material.
## 4. ASSESS — define the consequential purpose
Establish:
- what question is being answered;
- what decision depends on it;
- what counts as success;
- what is outside scope;
- cost of error;
- cost of delay.
Do not optimize for depth or activity in the abstract.
## 5. ANCHOR — establish the reference state
Use current trustworthy evidence.
For longitudinal work:
- recover canonical purpose/constraints;
- recover current baseline from durable sources;
- re-check fast-changing facts when consequential;
- treat memory and summaries as context, not current truth.
Stable rules may be remembered. Volatile state must be re-observed.
## 6. MODEL — expose the uncertainty structure
Choose the minimum useful model:
- causal graph;
- dependency graph;
- state machine;
- process map;
- evidence chain;
- authority chain;
- supply chain;
- architecture;
- constraint map.
Minimum useful means enough structure to expose material uncertainty—not minimum depth.
Maintain plausible competing hypotheses.
### Generalization
A concrete observation may be isolated or structural.
Generalize only when shared mechanism, invariant, dependency, or causal structure is supported.
Inspect the smallest discriminating set of neighboring/equivalent states needed to decide whether generalization changes the decision.
## 7. Epistemic discipline
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
```
Track material assumptions explicitly:
- statement;
- status;
- impact if false;
- verification path.
Assumption changes are state transitions.
## 8. FRONTIER — select the highest-value uncertainty
The frontier is the unresolved uncertainty with the highest expected effect on the consequential decision.
Prefer uncertainties that can:
1. invalidate the current model;
2. distinguish hypotheses;
3. identify/move a binding constraint;
4. invalidate the current plan;
5. affect costly or irreversible action.
Do not investigate merely because more information exists.
## 9. PROBE — choose by expected information value
Before a material probe state:
```yaml
probe:
  question:
  evidence_needed:
  possible_outcomes:
    outcome_a:
      implication:
    outcome_b:
      implication:
```
Conceptually:
```plain text
ProbeValue(q)
≈ ExpectedDecisionImpact(q)
 + ExpectedModelDiscrimination(q)
 - Cost(q)
 - Risk(q)
```
Ordinal comparison is enough.
## 10. UPDATE — change state, not prose
After a material probe update:
- evidence;
- hypotheses;
- assumptions;
- causal/dependency model;
- unknowns;
- bottleneck assessment;
- progress;
- decision implications.
Repeated activity that changes none of these may have zero information value.
## 11. Constraint and bottleneck descent
When a cause or constraint is found ask:
- does this level explain the observation?
- would one deeper layer change the decision or intervention?
- could a lower layer invalidate the current constraint classification?
- is the current layer actionable enough?
Descend while deeper structure has material decision value.
Stop when additional depth has negligible expected decision value.
## 12. RECONCILE — compare the part to the whole
Every material conclusion must survive comparison with:
- the original purpose;
- the full observation set;
- required constraints;
- current evidence;
- current system/reference state.
Ask whether:
- relevant observations are explained;
- contradictions are resolved;
- current action addresses cause versus symptom;
- local PASS is being mistaken for global correctness;
- the reasoning has drifted from the original objective.
## 13. Drift
Conceptually:
```plain text
Drift = MaterialDivergence(
  CurrentWhole,
  CanonicalPurposeAndConstraints
)
```
Material dimensions may include:
- semantics;
- assumptions;
- reference state;
- system/implementation state;
- evidence coverage;
- external dependencies.
No universal numeric distance is required.
## 14. Progress
Progress means material improvement in the decision state:
- uncertainty reduced;
- alternatives discriminated;
- contradiction resolved;
- binding constraint better identified;
- required condition satisfied;
- action space narrowed;
- model improved for a stated reason.
Activity alone is insufficient.
## 15. Sufficiency
### Minimum Sufficient Understanding
Investigation is sufficient when remaining material uncertainty is unlikely to change the purpose-relevant decision enough to justify another probe.
This does not mean “investigate as little as possible.”
### Purpose-relative sufficiency
Operational, explanatory, integrity, and action sufficiency may be reached at different times.
## 16. Action minimality
Once understanding is sufficient:
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
No numeric scoring is required.
### Necessity test
For each material component ask:
> If this component is removed, which proven requirement, invariant, safety condition, or required evidence path fails?
If no material failure follows, necessity is unproven.
Investigation breadth does not automatically justify action breadth.
## 17. Optionality
Under material uncertainty prefer, unless safety/timing says otherwise:
```plain text
observation
→ reversible discriminating probe
→ bounded reversible action
→ irreversible commitment
```
## 18. Loop / model reset
Potential stall:
```plain text
ΔP ≈ 0
while Effort > 0
and Model/Strategy ≈ unchanged
```
Observation window and tolerance are domain policy.
When applicable stall criteria are met, reconsider:
- framing;
- boundary;
- assumptions;
- decomposition;
- model class;
- evidence quality;
- work-unit structure;
- strategy.
Do not simply repeat another operation from the same ineffective strategy.
## 19. Recursive Control Closure
A controller may become the object of control:
```plain text
C(x)
C(C(x))
C(C(C(x)))
...
```
This recursion must terminate safely.
### 19.1 Meta-control value
Instantiate another control layer only when its expected protection is materially positive:
```plain text
MetaControlValue(k+1)
≈ ExpectedRiskReduction
 - ControlCost
 - DelayCost
 - AddedFailureSurface
```
No numeric precision is required.
If the next layer has negligible or negative value, do not create it.
### 19.2 Authority monotonicity
Moving to a meta-level does not itself grant more authority.
A deeper control layer may observe, analyze, or restrict within existing authority. It may not create new permission merely because it is “governing the governor.”
Any authority increase must come from an independent authorized source defined by the domain.
### 19.3 Fixed-point closure
Prefer stable higher-level invariants that apply to both the controlled action and the control process.
If an existing rule already resolves the meta-question, reuse it rather than creating:
- approval of approval;
- verification of verification;
- governance of governance;
without new decision value.
### 19.4 Bounded escape
If recursive control cannot justify another layer:
- stop adding control depth;
- preserve evidence/state;
- move to the least-commitment safe state already permitted;
- or defer the unresolved decision to the appropriate external authority.
This is a pre-authorized bounded closure path, not an ad-hoc bypass.
### 19.5 Policy parameters
Domains may define:
- maximum practical depth;
- thresholds;
- escalation authority;
- emergency modes;
- allowed fallback actions.
These values are not part of the universal formula.
## 20. External executors / tools
If the reasoning agent cannot inspect reality directly, delegate a narrow evidence-producing task.
Specify:
- exact question;
- required evidence;
- baseline;
- allowed operations;
- expected implications.
The executor produces observations. It does not automatically own semantic interpretation.
## 21. Domain adapters
Domain adapters may define:
- terminology;
- thresholds;
- authority;
- lifecycle states;
- tools;
- persistence;
- safe modes.
Examples include software workflows, medical escalation protocols, supply-chain models, financial research, and audit procedures.
These are instantiations, not the formula.
## 22. Anti-patterns
Do not:
- encode one historical case as a universal threshold;
- convert a fixture into a normative rule;
- stop at the first plausible cause;
- descend forever without decision value;
- broaden action because investigation broadened;
- equate activity with progress;
- reuse stale state because it is recent;
- keep the same model after sustained non-progress;
- use minimality to avoid causal understanding;
- create infinite meta-control layers;
- use a recursion escape as a hidden authority bypass.
## 23. Default output
For substantial work report enough of:
```yaml
goal:
anchor:
model:
evidence:
uncertainty:
frontier:
probe:
update:
reconciliation:
progress:
meta_control:
sufficiency:
action_minimality:
decision:
remaining_uncertainty:
```
Progressive Investigation is a two-layer control law:
> **The Epistemic Engine learns what reality most likely is. Meta-Control ensures the learning process itself remains useful, bounded, and safe.**
