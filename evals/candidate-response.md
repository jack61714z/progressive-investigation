## Queue 1: Record export

**Decision: Not ready for release review.** The shared helper violates the access contract across export, search, and sidebar count. `!scope.projects?.length` treats both administrator `null` and a non-administrator’s empty grant array as unrestricted workspace access. A caller with no active grants therefore receives all workspace records. Search and count have also lost their previous access semantics.

The 124 passing tests and both reviews do not resolve this: the decisive endpoint checks reuse the same fixture and exercise only nonempty project scopes. Agreement among endpoints can mean they share the same defect.

**Next authorized work order:** Make the smallest helper correction: grant workspace-wide visibility only when `scope.projects === null`; otherwise filter by the project array, including returning no rows for `[]`. No resolver rewrite is justified.

Before accepting the patch, add contract-derived cases through the actual resolver for administrators, members with no grants, members with only inactive grants, and members with one or multiple active grants. Include inaccessible projects in the same workspace and records in another workspace, including matching project keys. Exercise export, search, and count. Expected results: administrators see all and only their workspace; other callers see exactly their active projects; empty scopes see nothing. Preserve the existing multiple-project export and formatting checks.

**Completion:** Review-ready patch and evidence establishing those expectations across all changed endpoints, with the cumulative diff reconciled to the original request. Do not release. Current evidence establishes the defect, but contains neither its correction nor passing boundary checks.

## Queue 2: Workshop venue shortlist

**Decision: Shortlist incomplete. Only Alder Hall satisfies every requirement.** The checks validate the sheet’s entries and formula, not the requested all-in costs, classroom capacity, walking route, and complete accessible route.

Corrected sourced comparison:

- **Alder Hall, S1:** 24 classroom seats; step-free entrance and lift; accessible toilet on the room’s floor; eight-minute published walk. Total: `(£760 + £60 + 24 × £22) × 1.20 = £1,617.60`. Passes.
- **Bridge Loft, S2:** 18 classroom seats, despite its 30-person standing maximum; stairs without a lift; accessible toilet only on the ground floor; six-minute published walk. Total: `£680 + £90 + 24 × £28 = £1,442`, including VAT. Fails classroom capacity and step-free room access.
- **Canal Studio, S3:** 26 classroom seats; step-free throughout with an accessible toilet beside the room; 13-minute published walk. Total: `(£1,000 + £95 + 24 × £20) × 1.20 = £1,890`. Fails walking-distance and budget limits.

All calendars cover 09:00–17:00 on 10 November 2026; prices remain valid and the packet explicitly excludes other mandatory charges.

**Next work order:** Correct the comparison and withdraw the “all three qualify” recommendation. Retain Alder; obtain two replacement candidates under the original public-source-only research scope, checking every original requirement and itemized total before ranking. Do not contact or book venues or relax constraints. No replacement evidence is available in this packet, so those two options remain unestablished.

**Completion:** Three qualifying, sourced options. A corrected one-option result is useful partial delivery, not the requested completed shortlist.

## Queue 3: Support FAQ copy

**Decision: Complete; return the edited text below. No further work order is needed.** The exact-replacement byte comparison establishes both requested edits and preservation of every other character, UTF-8 encoding, LF line endings, and the single trailing newline. No deployment or external sending occurred. Further investigation would not change the completion decision.

```text
Support FAQ
Hours: Monday–Friday, 09:00–17:00 UTC
Email: support@example.test
Include your order reference when contacting us.
We reply within two working days.
```

The returned text ends with one newline after the final sentence.
