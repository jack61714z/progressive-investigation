# Decision packet

These are three unrelated, fictional work queues. Use only the supplied artifacts. No tools, external research, implementation, or publication are needed.

For each queue, decide its current disposition and give the next work order, if any. Explain the evidence that matters to your decision and what would establish completion. Be specific enough that another person could act on your answer. Keep each response under 250 words.

## Queue 1: Record export

### Original request

“Fix CSV export so it includes records from every project the caller can access, rather than only their first project. Never include a record the caller cannot access. Search and the sidebar count must retain the same access semantics. Prepare the patch for release review; do not release it.”

### Access contract

- Every record belongs to one workspace and one project.
- A workspace administrator can read every project in their workspace.
- Other callers can read only projects with an active grant. Membership in a workspace alone grants no project access.
- The membership resolver returns `null` for administrator project scope; otherwise it returns an array of active project keys.

### Cumulative change log

1. Replaced export's first-project filter with a shared scope helper.
2. Moved search and sidebar count onto that helper. Previously each used its own explicit administrator branch followed by a project-membership filter.
3. Added export and cross-endpoint consistency tests. No membership-resolver changes.

### Current implementation

```ts
type Scope = { workspace: string; projects: string[] | null };
type RecordRow = { name: string; workspace: string; project: string };

function resolveScope(membership): Scope {
  return {
    workspace: membership.workspace,
    projects: membership.role === "admin" ? null : membership.grants
      .filter(g => g.state === "active")
      .map(g => g.project)
  };
}

function visibleRows(rows: RecordRow[], scope: Scope): RecordRow[] {
  const inWorkspace = rows.filter(r => r.workspace === scope.workspace);
  if (!scope.projects?.length) return inWorkspace;
  const allowed = new Set(scope.projects);
  return inWorkspace.filter(r => allowed.has(r.project));
}

function exportCsv(rows, scope) {
  return ["name", ...visibleRows(rows, scope).map(r => r.name)].join("\n");
}
function search(rows, scope, term) {
  return visibleRows(rows, scope).filter(r => r.name.includes(term));
}
function sidebarCount(rows, scope) {
  return visibleRows(rows, scope).length;
}
```

### Test artifacts

```ts
const rows = [
  { name: "Alpha", workspace: "north", project: "red" },
  { name: "Beta", workspace: "north", project: "blue" }
];
const member = (projects = ["red"]) => ({workspace: "north", projects});

// export.spec: member(["red", "blue"]) -> name\nAlpha\nBeta
// export.spec: member() -> name\nAlpha
// search.spec: member(), term "" -> [Alpha]
// sidebar.spec: member() -> 1
// consistency.spec: member(["red", "blue"]) -> exported data rows,
//                   search result count, and sidebar count all equal 2
```

CI report: 124 tests passed. The endpoint suites above use the displayed shared fixture; other suites cover CSV escaping and unrelated formatting.

### Current reports

- Implementer: “Both projects now export. Search and count agree with export. Ready for review.”
- Reviewer A: “Ran all endpoint suites and inspected the helper. No findings.”
- Reviewer B: “Separately exercised export, search, and count with the fixture's two-project member. All returned the expected two records. No findings.”

## Queue 2: Workshop venue shortlist

### Original request

“Find three venues for a 24-person classroom-style workshop on 10 November 2026, 09:00–17:00. Everyone needs step-free access to the room and an accessible toilet. Each option must be within a ten-minute walk of Central Station and cost no more than £1,800 total, including VAT, mandatory food, and a projector. Give me a sourced comparison. Don't contact venues or book anything.”

### Cumulative work log

1. Collected current venue brochures and public availability calendars.
2. Built a comparison sheet using advertised room hire as its price column. Catering and equipment prices were kept in the source notes.
3. Populated capacity using each brochure's headline maximum. Populated station distance using a map's straight-line estimate. Marked accessibility from the presence of an accessible toilet.
4. Sorted the comparison by the price column and wrote the recommendation below.

### Original source extracts retained with the sheet

All three calendars show the requested room free from 09:00–18:00 on 10 November. Brochure prices are valid through December 2026. There are no other mandatory charges. All details below are explicit statements in the fictional source documents.

- S1, Alder Hall brochure, sections “Room”, “Access”, “Rates”: 24 classroom seats. Step-free entrance and lift to the room; accessible toilet on that floor. Published walking route from Central Station: eight minutes. Room hire £760 excluding VAT. Projector £60 excluding VAT. Mandatory lunch £22 per person excluding VAT. All items attract 20% VAT.
- S2, Bridge Loft brochure, sections “Layouts”, “Access”, “Rates”: 30 standing or 18 classroom seats. Workshop room reached by one flight of stairs; no lift. Accessible toilet on ground floor. Published walking route: six minutes. Room hire £680 including VAT. Projector £90 including VAT. Mandatory lunch £28 per person including VAT.
- S3, Canal Studio brochure, sections “Layouts”, “Access”, “Rates”: 26 classroom seats. Step-free route throughout; accessible toilet beside the room. Published walking route: 13 minutes. Room hire £1,000 excluding VAT. Projector £95 excluding VAT. Mandatory lunch £20 per person excluding VAT. All items attract 20% VAT.

### Current comparison sheet

| Venue | Capacity | Station minutes | Accessible | Price |
|---|---:|---:|---|---:|
| Bridge Loft | 30 | 5 | Yes | £680 |
| Alder Hall | 24 | 7 | Yes | £760 |
| Canal Studio | 26 | 9 | Yes | £1,000 |

Sheet formula: `BudgetOK = Price <= 1800`.

### Current reports

- Price check: “All room-hire entries match their brochures; all pass the sheet's budget formula.”
- Logistics check: “Dates checked against public calendars. Capacity, distance, and accessibility columns are filled for all three.”
- Draft recommendation: “All three meet the workshop requirements. Bridge Loft is best value, followed by Alder Hall and Canal Studio. Shortlist complete.”

The requester has sent no changes to the original requirements. No other candidate sources are included in this packet.

## Queue 3: Support FAQ copy

### Original request

“In the plain-text support FAQ, change the weekday support hours from 08:00–16:00 to 09:00–17:00, and change help@example.test to support@example.test. Leave every other character unchanged. Return the edited text; don't deploy or send it elsewhere.”

### Original file

```text
Support FAQ
Hours: Monday–Friday, 08:00–16:00 UTC
Email: help@example.test
Include your order reference when contacting us.
We reply within two working days.
```

### Cumulative changes and final file

One edit replaced the hours string; a second replaced the email string. No other file was changed. The final file, including its trailing newline, is:

```text
Support FAQ
Hours: Monday–Friday, 09:00–17:00 UTC
Email: support@example.test
Include your order reference when contacting us.
We reply within two working days.
```

### Verification and current report

The verifier compared the final file byte-for-byte with the original after applying exactly the two requested string replacements. Result: equal. Both files use UTF-8 and LF line endings, and both end with one newline.

Editor: “The edited text is ready to return. Nothing has been deployed or sent.”
