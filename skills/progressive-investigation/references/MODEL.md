# Progressive Investigation
> A domain-general reasoning control law for deciding what to learn, how deep to go, when understanding is sufficient, what action is justified, and when the reasoning process itself must change.
## Authority and design intent
This page is explanatory and non-normative.
[AGENT.md](AGENT.md) governs runtime behavior. [SKILL.md](../SKILL.md) is the compact entry point.
[FOUNDATION-NOTE.md](FOUNDATION-NOTE.md) records the **immutable origin and scope boundary** of the framework. It is not revised as part of ordinary skill versioning. If the foundational thesis itself changes, create a separate amendment rather than rewriting the note.
Progressive Investigation is intentionally a **formula, not an answer key**.
Historical software cases, medical examples, supply-chain examples, and project postmortems may test the framework. They must not define universal thresholds or lifecycle rules merely because a particular solution worked once.
## Why the framework exists
The underlying problem is **unknown-problem identification under partial observability**.
The visible symptom, bottleneck, diagnosis, constraint, or failure may not be the real problem. The investigator must progressively turn weak observations into a better model of reality, then decide when that model is sufficient for action.
## Two-layer architecture
### Layer A — Epistemic Engine
Question:
> What is actually happening, and what should be learned next?
It handles:
- evidence;
- hypotheses;
- causal/dependency models;
- bottlenecks;
- probe selection;
- falsification;
- updates;
- causal depth;
- sufficiency.
### Layer B — Meta-Control
Question:
> Is the investigation process itself still working?
It handles:
- anchoring and stale state;
- drift;
- progress versus activity;
- investigation cost;
- loops;
- model reset;
- recursive-control closure;
- optionality;
- termination.
### Domain adapters
Software, medicine, supply chains, finance, audit, law, and other domains may define their own:
- terms;
- tools;
- thresholds;
- authority models;
- workflows;
- safe modes;
- persistence formats.
Adapters instantiate the formula. They do not redefine it.
## Core abstraction
Think of the investigation state as:
`Sₜ = {G, B, M, E, U, C, X, P}`
- G — goal / consequential decision
- B — boundary / baseline
- M — model
- E — evidence
- U — uncertainty
- C — constraints
- X — available probes/actions
- P — material decision progress
The control loop is:
**ASSESS → ANCHOR → MODEL → FRONTIER → PROBE → UPDATE → RECONCILE → DECIDE**
## Information value
A useful probe is one likely to change the decision or discriminate between models:
`ProbeValue ≈ ExpectedDecisionImpact + ExpectedModelDiscrimination − Cost − Risk`
The terms can be ordinal. Fake numerical precision is unnecessary.
## Causal depth and bottlenecks
Descend one causal/dependency/bottleneck layer deeper only while deeper structure can materially change:
- the decision;
- the intervention;
- the constraint classification;
- model validity;
- or evidence required for closure.
This avoids both premature closure and infinite “why” chains.
## Investigation breadth versus action breadth
A central asymmetry:
> **Understanding may expand. Action must earn expansion.**
Once understanding is sufficient, choose the least expansive action that satisfies proven constraints.
Broad investigation does not justify implementing every mechanism discovered.
## Drift and progress
Drift is material divergence between the current whole and canonical purpose/constraints.
Progress is a change in decision state:
- uncertainty reduced;
- alternatives discriminated;
- contradiction resolved;
- bottleneck better identified;
- required evidence obtained;
- action boundary clarified.
Activity alone is not progress.
## Loop / model reset
A general stall pattern is:
`ΔP ≈ 0 while Effort > 0 and Model/Strategy ≈ unchanged`
How long this must persist is domain policy.
The general response is to question the model, boundary, assumptions, decomposition, or strategy—not blindly repeat another iteration.
## Recursive Control Closure
Any controller can become self-referential:
`C(x) → C(C(x)) → C(C(C(x))) → ...`
The core rule is not “stop at depth N.”
Instead, another meta-layer is justified only when its expected protection is materially greater than:
- control cost;
- delay cost;
- added failure surface.
Meta-level elevation does not create authority by itself.
If a stable higher-level rule already resolves the meta-question, reuse it rather than creating approval-of-approval or verification-of-verification chains.
If another layer has no positive decision/risk value, stop recursion and use the least-commitment safe state already permitted, or defer to the appropriate external authority.
## Memory
> **Memory is a constitution, not a database.**
Stable rules may be remembered. Volatile current state should be re-observed from durable evidence.
## Design rule for evolving this skill
When a real case exposes a failure:
1. Ask whether it reveals a domain-general principle.
2. If yes, generalize it into the smallest abstract rule.
3. If no, keep it in tests, examples, adapters, or domain policy.
4. Never copy a case-specific threshold, artifact, lifecycle state, or solution pattern into the core merely because it worked once.
5. Compare any proposed core expansion against [FOUNDATION-NOTE.md](FOUNDATION-NOTE.md).
This prevents Progressive Investigation from becoming a collection of solved exam questions or a universal domain-execution framework.
