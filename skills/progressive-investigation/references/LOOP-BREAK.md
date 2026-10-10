# Loop / Model-Reset Protocol
> Deep specification for **DECIDE** when continued work may be repeating the same ineffective reasoning strategy.
## Role
LOOP_BREAK is a general model-reset mechanism.
It is not defined by a universal number of failures, reviews, attempts, or cycles.
[AGENT.md](AGENT.md) governs.
## 1. Loop concept
A process is potentially looping when:
```plain text
ΔP ≈ 0
while Effort > 0
and Model/Strategy ≈ unchanged
```
Where **P** is material decision progress, not activity volume.
Examples of progress:
- uncertainty reduction;
- hypothesis discrimination;
- contradiction resolution;
- better constraint identification;
- required coverage gain;
- clearer action boundary.
Examples of activity:
- more documents;
- more searches;
- more tests;
- more edits;
- more reviews;
- more findings.
## 2. Policy parameters
A domain may define:
- observation window;
- tolerance for negligible progress;
- acceptable repeated failure classes;
- cost threshold;
- escalation authority.
These are policy parameters.
The core framework must not hard-code a universal “second”, “third”, or “two-cycle” rule from one historical case.
## 3. Stall diagnosis
Before resetting, ask:
- Is the progress measure wrong?
- Is the current model unable to explain new evidence?
- Is the boundary too narrow or too broad?
- Are assumptions stale or contradicted?
- Is the decomposition hiding a shared cause?
- Are probes non-discriminating?
- Is evidence quality too low?
- Is the action strategy repeating without learning?
- Should the work unit be split?
## 4. Reset
When the applicable stall policy is met:
1. restore the original purpose;
2. re-anchor current reality;
3. replay material state/model transitions;
4. identify where the current model stopped explaining or reducing uncertainty;
5. generate alternative model classes or decompositions;
6. choose a discriminating probe between alternatives;
7. resume only when the reasoning strategy materially changes.
Possible outcomes:
- CONTINUE with a revised model;
- REFRAME the question/boundary;
- SPLIT the problem;
- ROLLBACK an assumption/decision;
- REDESIGN the intervention;
- STOP because the remaining uncertainty is irreducible or low-value;
- ABANDON the current path.
## 5. Minimality after reset
Reset is not permission for a larger solution.
After model revision:
- re-evaluate Minimum Sufficient Understanding;
- re-run the necessity test on proposed actions;
- preserve optionality where material uncertainty remains.
## 6. Re-admission condition
Continue consequential action only when:
- the purpose/boundary is explicit;
- the revised model explains the stall better than the prior model;
- the next probe/action has materially positive expected value;
- the action is bounded by proven constraints;
- the relevant state is current.
## 7. Required output
A loop/reset decision should state:
- observed stall;
- progress measure;
- applicable policy threshold;
- why the prior model/strategy is insufficient;
- what changed in the revised model;
- next discriminating step;
- what remains blocked or uncertain.
The principle is general:
> When effort stops producing information or closure, change the model or strategy—not merely the amount of effort.
