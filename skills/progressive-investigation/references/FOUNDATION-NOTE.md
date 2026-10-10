
> **IMMUTABLE ORIGIN NOTE — not versioned with the evolving skill.**
This page records why Progressive Investigation exists and where its boundary is. It is intentionally **not** a changelog, implementation guide, or current best-practice document.
Future versions of `SKILL.md`, `AGENT.md`, protocols, adapters, and tests may evolve. This note should not be rewritten merely because the framework evolves.
If the foundational thesis itself must change, create a separate dated amendment or decision record. Do not silently rewrite this page and erase the original design intent.
## Why this skill exists
The original problem is **unknown-problem identification under partial observability**.
In many important situations, the visible problem is not the true problem:
- a software symptom may be several layers above the structural cause;
- symptoms may cross specialties and only make sense when integrated;
- an apparent supply-chain bottleneck may be constrained by a lower-level process, component, material, facility, logistics route, or lead time;
- public signals may indirectly reveal hidden state that no single source exposes directly;
- the first plausible explanation may be correct, incomplete, or merely convenient.
When the true problem is not known in advance, a fixed checklist or direct solution is insufficient. The investigator must progressively build a model of reality, choose discriminating observations, update beliefs, and decide how far to descend.
Progressive Investigation therefore exists to answer:
> **When the real problem is initially unknown, how should an agent progressively reduce decision-relevant uncertainty until it can identify the right problem and justify the next action?**
## The original thesis
The framework should help an investigator:
1. avoid anchoring on the first plausible explanation;
2. integrate evidence across domains, interfaces, and hidden dependencies;
3. descend causal / dependency / bottleneck chains only while deeper structure can change the decision;
4. choose observations for information value rather than volume;
5. distinguish evidence, inference, hypothesis, and proof;
6. preserve important uncertainty instead of hiding it;
7. stop when understanding is sufficient for the stated purpose;
8. act only as broadly as the proven problem requires.
The framework is not intended to know the answer beforehand.
It is intended to make blind exploration progressively less blind.
## Why Meta-Control belongs in the skill
An iterative investigation can itself fail.
It can:
- drift away from the original purpose;
- repeat work without gaining information;
- rely on stale state;
- confuse activity with progress;
- stop too early;
- investigate forever;
- recursively apply control to control without a termination condition.
These are not new application domains. They are failure modes of the investigation process itself.
Therefore Progressive Investigation may govern **the quality and termination of its own uncertainty-reduction process**.
This is Meta-Control.
## The boundary
Progressive Investigation owns:
- uncertainty reduction;
- causal / dependency / bottleneck modeling;
- hypothesis discrimination;
- probe selection;
- evidence update;
- sufficiency and stopping;
- drift / progress assessment;
- model reset;
- recursive-control termination;
- action minimality and optionality under uncertainty.
Progressive Investigation does **not** own:
- domain execution procedures;
- domain-specific authority structures;
- software merge workflows;
- medical treatment protocols;
- investment position sizing;
- legal authorization;
- supply-chain purchasing decisions;
- arbitrary lifecycle thresholds;
- case-specific escalation counts.
Those belong in domain expertise, domain adapters, policy, or execution systems.
## Anti-expansion rule
A new idea belongs in the core only if it is genuinely about **uncertainty reduction or control of the uncertainty-reduction process**.
Before adding a core rule, ask:
1. Does it remain valid across materially different domains?
2. Can it be expressed without case-specific nouns, artifacts, or workflow states?
3. Does omitting it create a general failure in investigation or meta-control?
4. Does it compose naturally with the existing state / probe / update / reconcile / decide model?
5. Can it be tested in multiple domains?
If not, keep it in a domain adapter, policy, example, or regression fixture.
## Formula, not answer key
Historical cases may reveal weaknesses in the formula.
They may motivate:
- a new variable;
- a missing invariant;
- a better stop condition;
- a better distinction between state and evidence.
They must not directly dictate universal thresholds or workflows.
A case is a **sample from the problem space**, not the definition of the problem space.
## Immutable design principle
The framework should remain small enough to preserve a stable mathematical idea:
> **Model reality under uncertainty, acquire the most decision-relevant information, deepen the model only while depth matters, reconcile local conclusions against the whole, act with the smallest justified commitment, and change the reasoning process when it stops producing information or closure.**
This note exists so later improvements do not accidentally turn Progressive Investigation into a collection of domain-specific solutions.
