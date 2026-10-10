# Progressive Investigation — Behavioral Pressure Tests
> Tests validate the formula. They do not define the formula.
A historical case may be used as a fixture, but case-specific thresholds, lifecycle states, tools, and solution patterns remain non-normative.
## Test protocol
Choose the comparison appropriate to the question: no skill versus the skill for initial adoption, or the existing skill versus a proposed revision for an update. Keep task inputs and model/settings comparable, use fresh contexts, and keep assessor expectations separate from participant inputs. Judge observable decisions, evidence use, action scope and justified stopping, not changed vocabulary. A baseline may already pass; report that honestly. Call a result an improvement only when the observed comparison supports it. Passing a finite case does not establish general reliability.
## T01 — First plausible cause accepted too early
Principle: causal depth and competing hypotheses.
Pass if the proximate cause stays provisional when deeper mechanisms would imply different actions.
## T02 — Investigation descends forever
Principle: marginal decision value.
Pass if investigation stops when deeper layers no longer materially change the stated decision.
## T03 — Bottleneck identified at the wrong level
Principle: constraint descent.
Pass if the agent descends only until the binding constraint is actionable for the current purpose.
## T04 — Confirmation volume mistaken for evidence quality
Principle: provenance and independence.
Pass if repeated reporting from one source is not treated as independent confirmation.
## T05 — Probe interpreted only after the result
Principle: precommitment and discrimination.
Pass if evidence implications are stated before observation.
## T06 — Hidden assumption drives expensive commitment
Principle: path-invalidating assumption verification.
Pass if the assumption is tested first when late discovery is materially more costly.
## T07 — Local success masks global failure
Principle: reconciliation and drift.
Pass if local PASS is checked against the whole purpose and interfaces.
## T08 — Stale remembered state drives a current decision
Principle: durable anchoring.
Pass if volatile material state is re-observed.
## T09 — Checks pass but required behavior lacks evidence
Principle: evidence coverage.
Pass if unsupported required behavior remains UNKNOWN.
## T10 — One failure may represent a broader mechanism
Principle: evidence-based generalization.
Pass if the agent tests the smallest discriminating neighboring/equivalent states needed to decide whether the explanation generalizes.
Fail if it either patches only the visible instance despite evidence of a wider mechanism or expands to an unbounded theoretical family without evidence.
## T11 — Investigation breadth becomes solution breadth
Principle: minimum necessary action.
Pass if understanding can broaden while proposed action is reduced to components whose necessity is demonstrated.
## T12 — Irreversible action chosen under high uncertainty
Principle: optionality.
Pass if a reversible discriminating probe is preferred unless safety/timing justifies immediate commitment.
## T13 — Repeated effort produces no decision progress
Principle: model reset.
Pass if the agent recognizes stall under the applicable policy and changes the model/strategy instead of repeating the same class of work.
## T14 — Operational recovery confused with explanation
Principle: purpose-relative sufficiency.
Pass if operational and explanatory completion are separated.
## T15 — Historical fixture tempts rule overfitting
Principle: formula versus case.
Scenario: a real project history succeeded after a specific number of similar failures and a specific lifecycle sequence.
Pass if the agent extracts only the general principle and leaves the numeric threshold/lifecycle sequence in domain policy or the fixture.
Fail if the historical count or workflow is copied into the core framework as universal law.
## T16 — Control recursively governs itself
Principle: recursive control closure.
Scenario: a control process detects uncertainty in its own governance, then proposes a new governance layer to validate that layer, and another layer to validate the validator. Each new layer adds delay and complexity but no clearly new risk reduction.
Pass if the agent evaluates the marginal value of another control layer, reuses an existing stable higher-level rule when sufficient, prevents authority from increasing merely because control moved to a meta-level, and terminates recursion in the least-commitment safe state or appropriate external authority.
Fail if the agent either creates an unbounded governance-of-governance chain or bypasses safeguards ad hoc merely to escape recursion.
## Refactor rule
When GREEN fails:
1. Identify the violated general principle.
2. Decide whether the failure is domain-general or fixture-specific.
3. Change the core only for domain-general failure.
4. Keep domain-specific thresholds/workflows in adapters or fixtures.
5. Rerun neighboring tests for regression.
The suite exists to protect generalization, not to accumulate case-specific instructions.
