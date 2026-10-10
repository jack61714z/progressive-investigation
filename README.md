# Progressive Investigation

A portable, domain-general agent skill for finding the real problem, choosing useful probes, checking the whole outcome, and stopping when enough is known.

Progressive Investigation separates two questions:

- **What is happening, and what evidence could change the decision?**
- **Is the investigation itself still producing useful progress?**

It applies to uncertain research, debugging, audit, planning and cross-boundary problems. Straightforward tasks with sufficient evidence should finish without unnecessary investigation. This is a reasoning aid, not an execution service, an approval system, or a guarantee of correct decisions.

## Use the skill

The self-contained payload is [skills/progressive-investigation](skills/progressive-investigation). Its entry point is [SKILL.md](skills/progressive-investigation/SKILL.md); copy the **entire directory**, including `references/` and its `LICENSE`, into a skill location supported by your agent client. Do not copy only the entry file.

For a client that supports project-local `.agents/skills`, place it at `.agents/skills/progressive-investigation/`. Other clients may use different locations or import flows; follow that client's current documentation. Review existing customizations before replacing an installed copy, and follow its documented reload/new-session behavior.

You can also ask a file-capable assistant directly:

> Read `skills/progressive-investigation/SKILL.md`, use its relevant bundled references, and investigate this task: [goal, current evidence, constraints]. Give the supported decision, material unknowns and smallest justified next step.

A file-reading assistant can use the documents directly without an installer. Automatic discovery, plugin integration and activation depend on the host. This repository does not install hooks, start services, grant permissions or provide tools unavailable to the host.

## What is included

- [AGENT.md](skills/progressive-investigation/references/AGENT.md): operational contract.
- [MODEL.md](skills/progressive-investigation/references/MODEL.md): explanatory model.
- [PERSISTENT-STATE.md](skills/progressive-investigation/references/PERSISTENT-STATE.md): preserve purpose and re-observe changing state across long work or handoffs.
- [FEATURE-INTEGRITY.md](skills/progressive-investigation/references/FEATURE-INTEGRITY.md): reconcile cumulative outcomes and evidence with the original purpose.
- [LOOP-BREAK.md](skills/progressive-investigation/references/LOOP-BREAK.md): change a stalled model or strategy instead of repeating activity.
- [FOUNDATION-NOTE.md](skills/progressive-investigation/references/FOUNDATION-NOTE.md): original design intent, preserved unchanged.
- [TESTS.md](skills/progressive-investigation/references/TESTS.md): sixteen behavioral pressure-test specifications, not a claim that all sixteen have been run.

Read supporting documents when relevant; they do not require a new reporting format or another approval layer. Existing task records can carry the decisions and evidence.

## Examples and verification

[Worked decisions](examples/decisions.md) show a shared test assumption, a misleading research shortlist, and a completed edit that needs no further process.

[Evaluation report](evals/REPORT.md) includes raw fictional inputs, separate assessor criteria, prompt snapshots and actual responses. A small comparison found the same correct decisions with the existing compact guidance and with additional operational wording. It did **not** demonstrate an improvement from adding rules. The published core therefore preserves the original principles and repairs packaging/navigation instead.

An evaluation response is evidence only for the task and environment actually exercised. It is not proof of long-running adherence, universal host compatibility, production behavior or an independently established causal improvement.

## Packaging choices and references

This repository follows the [Agent Skills format](https://agentskills.io/specification) and its [evaluation guidance](https://agentskills.io/skill-creation/evaluating-skills). Public repositories such as [Anthropic's skills](https://github.com/anthropics/skills) and [Superpowers](https://github.com/obra/superpowers) informed the separation of a small skill payload, supporting references and behavioral examples. Their domain-specific workflows and hooks are not dependencies of this skill. These links imply no endorsement.

The material is maintained here as a portable source distribution. Publishing it does not automatically update copies in another application.

## License

[MIT](LICENSE).
