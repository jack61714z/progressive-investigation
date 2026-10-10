# Persistent State Protocol
> Deep specification for the **ANCHOR** and **UPDATE** phases of Progressive Investigation.
## Role
This protocol defines how long-running reasoning preserves enough state to resume correctly without treating recent conversation or model memory as current truth.
[AGENT.md](AGENT.md) governs.
## 1. Core rule
**Memory is a constitution, not a database.**
Stable operating rules may live in memory.
Current task/system truth must come from durable evidence appropriate to the domain.
Conversation history, summaries, remembered states, and prior conclusions are navigation aids until reconciled.
## 2. When durable state is needed
Use durable state when work crosses:
- sessions or conversations;
- multiple agents, specialists, or executors;
- material baseline changes;
- authority/reference changes;
- consequential multi-step investigation;
- long-running decisions where drift or staleness matters.
A short self-contained task may remain conceptual.
## 3. Durable anchor
Persist enough state to reconstruct the reasoning state:
- canonical purpose / question;
- system or problem boundary;
- current baseline / reference state;
- material assumptions and their status;
- evidence and provenance;
- unresolved constraints / unknowns;
- current model;
- relevant authority or decision rights when applicable;
- progress state;
- last material reconciliation.
The representation is domain-specific.
## 4. Source hierarchy
Every domain should define a hierarchy of trustworthy current-state sources.
A general ordering principle is:
1. direct/current evidence closest to the underlying reality;
2. durable authoritative records;
3. durable explanatory/derived records;
4. planning/tracking representations;
5. conversation context and memory.
The exact sources differ by domain.
A lower-confidence or stale representation must not silently overwrite stronger contradictory evidence.
## 5. Cross-session bootstrap
When resuming consequential work:
1. identify the durable work unit or question;
2. recover canonical purpose and boundary;
3. recover current baseline/reference state;
4. recover material assumptions;
5. recover unresolved constraints/unknowns;
6. recover current model and progress state;
7. compare remembered/recent context against durable evidence;
8. mark unreconciled state as stale or UNKNOWN.
Do not infer missing state merely because the latest conversation sounds coherent.
## 6. Assumption lifecycle
Track material assumptions with:
- statement;
- status: unverified \| supported \| verified \| invalidated \| retired;
- impact if false;
- evidence;
- transition reason.
Assumption changes belong to UPDATE and can trigger RECONCILE.
## 7. Progress journal
For multi-cycle work, persist enough information to evaluate whether the decision state is improving.
Useful fields can include:
- baseline;
- objective;
- uncertainty change;
- contradiction change;
- constraint/coverage change;
- scope change;
- model change;
- resulting decision state.
Do not manufacture numerical precision. The purpose is to detect drift and false progress.
## 8. Staleness
Any fast-changing fact should be treated as stale when its freshness materially affects the next decision.
Examples vary by domain:
- software head/runtime state;
- market prices;
- medical measurements;
- supplier capacity;
- legal/regulatory status;
- external service state.
Do not promote volatile facts into long-term memory as durable truth.
## 9. Update discipline
After a material probe, state transition, intervention, reconciliation, or model reset:
- update durable state;
- preserve enough superseded history to explain important transitions;
- record why assumptions or boundaries changed;
- distinguish current truth from historical truth.
The goal is resumability and integrity, not exhaustive logging.
