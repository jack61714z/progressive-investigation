# Decision evaluation — 2026-10-10

## Question and design

Would extra operational wording improve decisions over the existing compact Progressive Investigation guidance?

Two fresh independent assistant contexts received identical [fictional task inputs](inputs.md). One received [baseline guidance](baseline-guidance.txt); the other received [the same guidance plus operational paragraphs](candidate-guidance.txt). The contexts used the same inherited model and reasoning configuration. The exact runtime model identifier was not independently captured; this is not a reproducible model benchmark. Each context handled all three tasks in a single response, so the three decisions within an arm are not independent trials.

Participants were instructed not to inspect the [assessor rubric](rubric.md) or other responses. The rubric was prepared separately before responses were assessed. The coordinator compared actual decisions and evidence, not keyword presence. No live system, personal data, booking, deployment or repository mutation was part of these tasks.

The historical prompt snapshots are evaluation data, not installed payloads. Their mentions of upstream documents describe the original compact distribution; only the guidance text was supplied in this comparison. The candidate's added paragraphs were not adopted as new mandatory core rules.

## Observed results

Read the actual [baseline response](baseline-response.md) and [candidate response](candidate-response.md).

| Task | Baseline | Candidate |
| --- | --- | --- |
| Shared authorization helper | Identified `null`/empty-array conflation, withheld review-ready acceptance, covered all three affected consumers with bounded controls | Same material diagnosis and bounded disposition |
| Venue research | Calculated £1,617.60 / £1,442 / £1,890; retained only Alder, identified capacity/access and budget/walk failures; sought two replacements | Same material calculations and disposition |
| Exact copy edit | Accepted the already-supported result and returned the text without extra process | Same material completion decision |

Both arms met the central disposition/evidence/action/closure expectations. Minor wording and breadth differences do not establish a meaningful performance difference. These were decision-only tasks: a correctly specified next action was sufficient; neither arm actually repaired or deployed the fictional application.

**No baseline failure and no demonstrated improvement.** This does not prove the additional wording is useless, nor that the current skill will always work. A small, non-repeated, coordinator-assessed comparison cannot establish causality, production effectiveness or reliable behavior over long conversations.

## Consequence for this release

Preserve the original domain-general core. Repair real packaging defects: actual YAML frontmatter, portable relative references, and inclusion of the existing persistence/integrity/loop/foundation documents. Keep practical examples outside the normative core. The sixteen pressure-test specifications remain specifications; this three-task comparison is not a claim that the whole suite passed.

## Final payload usability

A separate fresh assistant context copied only the eight-file instructional skill payload into an isolated directory and loaded its entry point. It read AGENT, FEATURE-INTEGRITY, PERSISTENT-STATE and LOOP-BREAK through the bundled relative references. It was not given the rubric or prior responses. See the actual [release response](release-response.md) and [load report](release-load-report.md).

The coordinator checked its decisions against the original task packets and rubric: it identified the authorization leak across all three consumers, corrected all three venue totals and rejected the two noncompliant candidates, and returned the already-verified FAQ edit without another investigation. The first two tasks remained incomplete with bounded next actions; the third was complete. This was a successful manual-load, reference-navigation and decision-use check of this payload in one native assistant context. No code was repaired or run in the fictional tasks.

After that run, a copy of the repository MIT license was added inside the payload so a standalone copy retains its license. No instruction file changed.

The package also passed the skill frontmatter validator, a relative-link closure check, and an exact-byte comparison of the immutable foundation note to its source. These static checks are separate from the behavioral run. Neither establishes automatic discovery or activation in a specific desktop application; that requires a host-specific check after installation.
