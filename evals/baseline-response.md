## Queue 1: Record export

**Disposition: Not ready for release review.** The shared helper violates the access contract and introduces the same regression into search and sidebar count.

`!scope.projects?.length` is true for both administrator scope (`null`) and a non-administrator with no active grants (`[]`). The latter therefore receives every record in their workspace. With the supplied fixture, an empty-grant caller gets Alpha and Beta instead of no records. Workspace filtering does not compensate for missing project authorization.

The 124 passing tests and both reviews do not resolve this: the relevant checks exercise overlapping nonempty-grant states. Agreement between endpoints sharing one incorrect helper is not independent evidence of correct access semantics.

**Next authorized work order:** Change the helper's unrestricted branch to an explicit `scope.projects === null` check. Let the existing set-based filter return no rows for an empty array. Preserve the workspace filter and membership resolver; no broader redesign is justified.

Add contract-based regression coverage across export, search, and count for administrator `null`, empty grants, one grant, and multiple grants. Include an ungranted project and a different-workspace record, including a matching project key across workspaces. Verify inactive-only membership resolves to empty scope. Empty scope must produce CSV header `name`, search `[]`, and count `0`; administrator scope must remain workspace-bounded.

**Completion:** The bounded patch, discriminating tests, full-suite results, and cumulative diff are ready for release review. Do not release. The defect is established from the code; corrected behavior remains unverified until the patch and tests exist.

## Queue 2: Workshop venue shortlist

**Disposition: Incomplete. Only Alder Hall qualifies from the supplied sources.** Replace the recommendation; its columns measure the wrong requirements.

Corrected sourced comparison:

- **Alder Hall, S1 (“Room”, “Access”, “Rates”):** 24 classroom seats; step-free entrance and lift; accessible toilet on the room's floor; eight-minute published walk. Total: (£760 + £60 projector + 24 × £22 mandatory lunch) × 1.20 = **£1,617.60**. Meets all stated constraints.
- **Bridge Loft, S2 (“Layouts”, “Access”, “Rates”):** 18 classroom seats; stairs with no lift; accessible toilet downstairs; six-minute walk. VAT-inclusive total: £680 + £90 + 24 × £28 = **£1,442**. Fails classroom capacity and step-free room access. Standing capacity and a toilet alone cannot establish compliance.
- **Canal Studio, S3 (“Layouts”, “Access”, “Rates”):** 26 classroom seats; step-free throughout; accessible toilet beside the room; 13-minute walk. Total: (£1,000 + £95 + 24 × £20) × 1.20 = **£1,890**. Fails walking distance and budget.

All supplied calendars cover 09:00–17:00 on 10 November 2026. Prices are valid then. Accurate room-hire entries and populated columns do not validate total cost or logistics.

**Next work order:** Correct the comparison and budget formula using these sources. Retain Alder; obtain public-source evidence for two additional qualifying venues, without contacting or booking. No additional candidates can be established from this packet. Do not relax requirements.

**Completion:** Three source-supported options each satisfy date/time availability, 24 classroom seats, both accessibility requirements, actual walking time, and the complete VAT-inclusive budget. That evidence is currently missing for two options.

## Queue 3: Support FAQ copy

**Disposition: Complete.** The byte-for-byte comparison against exactly the two authorized replacements establishes the requested change and preservation of every other character, including UTF-8 encoding, LF line endings, and the single trailing newline. No further investigation, editing, deployment, or external sending is warranted.

**Completion response:** Return the following edited text, ending with exactly one newline:

```text
Support FAQ
Hours: Monday–Friday, 09:00–17:00 UTC
Email: support@example.test
Include your order reference when contacting us.
We reply within two working days.
```

No material uncertainty remains for the requested edit-and-return task.
