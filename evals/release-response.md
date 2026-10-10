## Queue 1: Record export

Disposition: Block release-review readiness; return the patch for a bounded authorization repair. Do not release.

The helper conflates administrator scope (`null`) with no granted projects (`[]`): both satisfy `!scope.projects?.length` and expose every workspace record. A non-admin with no active grants therefore receives unauthorized export rows, search results, and sidebar counts. Moving search and count onto the helper spread this defect beyond export.

The 124 passing tests and favorable reviews do not establish access correctness. The displayed endpoint fixtures omit zero-grant users, administrators, inactive grants, and other workspaces. Repeating the two-project scenario adds no coverage of those boundaries; endpoint agreement can mean shared incorrectness.

Next work order:
1. Make administrator scope explicit: only `projects === null` grants all rows within the selected workspace. Apply project membership filtering to arrays, including the empty array.
2. Add resolver-to-endpoint regressions for no grants, inactive-only grants, mixed active/inactive grants, one active project, multiple active projects, and administrator scope. Include another workspace with overlapping project keys.
3. Assert independently specified authorized row sets for export/search and their exact sidebar count, rather than only agreement between endpoints. Re-run affected and existing regression suites and inspect the cumulative endpoint diff against the access contract.

Completion: the bounded patch demonstrates all accessible export records, zero inaccessible records, unchanged search/count access semantics, and workspace isolation across those cases. Provide that evidence for release review. No broader resolver redesign is justified by this packet.

## Queue 2: Workshop venue shortlist

Disposition: Incomplete. One qualifying venue is supported; the three-option recommendation must be corrected.

Source-backed comparison for 24 attendees:
- Alder Hall: £1,617.60 total: (£760 room + £60 projector + 24 × £22 lunch) × 1.20. Exactly 24 classroom seats; step-free entrance and lift, accessible toilet on the room's floor; eight-minute published walk. Passes every requirement. Source: S1, “Room”, “Access”, “Rates”.
- Bridge Loft: £1,442 total: £680 + £90 + 24 × £28, all VAT-inclusive. Only 18 classroom seats; stairs without a lift fail room access despite the ground-floor accessible toilet. Six-minute walk. Reject. Source: S2, “Layouts”, “Access”, “Rates”.
- Canal Studio: £1,890 total: (£1,000 + £95 + 24 × £20) × 1.20. Has 26 classroom seats and suitable step-free access/toilet, but its 13-minute walk and total price fail the limits. Reject. Source: S3, “Layouts”, “Access”, “Rates”.

All supplied calendars cover 09:00–17:00 on 10 November 2026; prices cover that date. These facts do not cure the other failures. The sheet substituted room hire, headline capacity, straight-line distance, and toilet presence for the actual acceptance criteria.

Next work order: correct the comparison and total-cost formula, retain source provenance, and obtain public-source evidence for at least two additional qualifying candidates. No additional candidates can be established from this packet. Do not relax constraints, contact venues, or book.

Completion: three sourced options each independently satisfy date/time, 24 classroom seats, the full accessible route/toilet requirement, actual walking time ≤10 minutes, and all-in total ≤£1,800.

## Queue 3: Support FAQ copy

Disposition: Complete; return the edited text. No additional work order is needed.

The supplied byte-for-byte comparison verifies exactly the two authorized replacements, with UTF-8, LF endings, and one trailing newline preserved. That evidence covers the entire narrow request. Further investigation or another review layer would not add material decision value. No deployment or external sending is authorized or needed.

```text
Support FAQ
Hours: Monday–Friday, 09:00–17:00 UTC
Email: support@example.test
Include your order reference when contacting us.
We reply within two working days.
```

Completion is satisfied by returning this text, including its single trailing newline.
