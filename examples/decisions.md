# Worked decisions

These fictional examples illustrate how to use the existing contract. They are not mandatory templates, new approval gates or universal test matrices. The full raw packets and responses are in [evals](../evals/REPORT.md).

## 1. A passing test suite shares the implementation's mistake

The goal is a correctly permissioned CSV export. The cumulative change also routes search and sidebar counts through a helper. The helper interprets both an administrator's `null` project scope and a member's empty `[]` scope as unrestricted workspace access. Tests and reviewers exercised only nonempty grants.

The useful decision is to withhold acceptance: a no-grant member receives records, contrary to the original access contract. Agreement between consumers of the same faulty helper is not independent corroboration.

A bounded next step fixes the distinction in that helper and tests the affected consumers through representative actual scope-resolution paths, including empty/inactive grants, administrator and granted-member controls, and workspace isolation. It does not rebuild the permission system or demand every theoretical combination.

Completion requires evidence of the repaired contract across the changed paths. Identifying the bug is not evidence that the patch has already been made. An UNKNOWN overall outcome does not make a demonstrated component defect harmless.

## 2. Accurate fields do not establish the requested outcome

The goal is three venues for a 24-person classroom session, within the all-in budget, walking limit and step-free access requirements. The comparison sheet instead checks room-only price, standing capacity, straight-line distance and whether any toilet exists.

Recomputing from the supplied source facts leaves one qualifying option. The appropriate next step preserves that valid work, corrects the comparison and researches two replacements under the original constraints. It neither invents missing options nor silently relaxes the budget or accessibility requirement.

One supported option is useful partial delivery, not completion of a three-option request. If authorized research cannot establish three, report that limitation rather than manufacturing success.

## 3. Sufficient evidence should end the work

The goal is exactly two text replacements while preserving all other bytes. The supplied final text and exact replacement comparison meet that goal.

Return the text and stop. A new interview, extra approval form, independent model review or deployment would add work without changing this decision.

## Applying the lesson in ongoing work

At a consequential delegation, acceptance or completion decision, use the existing task record to connect the original required outcome with the cumulative actual artifacts. Check decisive original inputs or producer facts when implementation and tests may share assumptions. Assign the smallest evidence-changing next step, or close when the evidence is already sufficient. Preserve genuine unknowns and historical drift without turning either into an unlimited repair mandate.
