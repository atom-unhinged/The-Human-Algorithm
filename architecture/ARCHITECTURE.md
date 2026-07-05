# THA — Architecture Decision Records

*This document is part of THA's development architecture. It is intended for maintainers rather than readers and is not part of the framework itself.*

---

## ADR-001: Single Source of Truth

**Principle:** Every artifact has one authored source of truth. Every other representation is a derived view that is regenerated, never edited directly.

**Corollaries:**
- One owner per piece of information — no two artifacts store the same fact.
- Six things, six owners — notes (explanations), terms (meaning), concepts (grouped ideas), relationships (graph structure), reading order (sequence), and status (maturity) are structurally distinct axes. Conflating any two is a category mistake, not a style choice — Phase 2 caught this happening twice with status alone (definition wording absorbing a hedge that belonged in the status field instead).
- Views never own data; they render it.
- Derived artifacts are regenerated from their source, never hand-edited.
- Navigation is independent of taxonomy — how readers move through THA is not dictated by how notes are tagged.
- Concepts are not notes — a Map node names an idea; it expands to the note IDs that elaborate it, but the idea and the note are different objects.
- Tags are metadata, not navigation — Core/Identity/Practice/Principles/Context/Tools classify notes; they don't have to be how readers browse them.
- Status is orthogonal to tags and concepts — a term's maturity (Established Principle / Working Model / Hypothesis / Working Term / Open Question) is a separate axis from which category or concept it belongs to.

**Artifact map:**

| Artifact | Authored Source | Derived View(s) |
|---|---|---|
| Index | `notes` data (id, num, title, tag) | Homepage grid, navigation sidebar, note metadata lookups |
| Definitions | Definition entries (term, meaning, status, linked note) | Definitions page |
| Map | Concept assignments (CONCEPTS.md) | Interactive concept map |
| Reading Paths | Path definitions (ordered note-ID sequences per reader question) | Reading Paths page |
| Dependency Graph | Existing note links (`showNote()` calls already inside note bodies) | Graph JSON / visualization |

Note: Dependency Graph owns no authored data of its own. Its source is the links already written inside notes — it is a pure derived view of content that lives elsewhere.

---

## Process

**Authorship timeline** — how THA's vocabulary actually originates: notes evolve, a concept stabilizes across them, and only then does a Definitions entry compress it. Definitions derives from settled understanding; it does not generate it.

**Maintenance timeline** — how a Definitions entry, once canonical, is kept correct: the definition changes, affected notes are checked for contradiction, derived artifacts regenerate. The reverse direction of Authorship, and it only applies to terms that already exist.

These are different processes answering different questions. Treating Maintenance's direction as if it were Authorship's — notes drifting until Definitions "catches up" — was an early framing error worth naming so it isn't repeated.

**Editorial test** — a definition entry is edited or accepted only when it satisfies (or corrects a failure against) a named test: concept, closed-vocabulary, modality preservation, stability, or reconstruction. Not stylistic preference. This principle is not expected to change based on CONCEPTS.md or later artifacts, since it documents Phase 2's editorial process rather than the term/concept ontology — though later artifacts may surface their own analogous tests rather than reuse these directly.

---

## Terminology

**Legacy Gap** — an architectural mismatch that predates the ADR it conflicts with. No blame; expected during maturation. Never disappears once logged — remains as historical record, marked Open or Closed (with a reference to the task that closed it). See LEGACY_GAPS.md.

**ADR Violation** — new work, written *after* an ADR existed, that fails to comply with it. Action: fix it, or consciously supersede the ADR. Reserved for future issues — everything currently logged predates ADR-001 and is therefore a Legacy Gap, not a Violation.

**Implementation Task** — actionable, concrete work that satisfies an ADR or closes a Legacy Gap. Disappears once completed, or moves to a completed archive. See IMPLEMENTATION_TASKS.md.

**Deferred Decision** — a choice consciously postponed until a stated trigger condition is met. Not a Legacy Gap (nothing predates a broken standard) and not an Implementation Task (nothing is being built now). Instances are logged, with their trigger condition, in DEFERRED_DECISIONS.md. Once triggered, a Deferred Decision resolves into either a new ADR or an Implementation Task — it does not simply get edited in place.

---

## Change log

- 2026-07-04 — ADR-001 established. Retroactively covers the Constructive Displacement rebuild (note renumbering, duplication cleanup in Peace is the Protocol / Sovereign Signal) and the five-artifact Guidebook architecture: Index, Definitions, Map, Reading Paths, Dependency Graph.
- 2026-07-04 — THA Architecture v1.0 frozen. Further changes expected from implementation experience, not further design review.
- 2026-07-04 — Deferred Decision term added; DD-001 (contributor architecture) logged in DEFERRED_DECISIONS.md.
- 2026-07-05 — Definitions v1.0 implemented: DEFINITIONS.md created (28 entries). Six-category ownership corollary, Authorship/Maintenance timelines, and the Editorial Test principle added, capturing patterns Phase 2 validated during drafting. DD-002 (term removal) and DD-003 (semantic/conceptual relationship ownership) logged in DEFERRED_DECISIONS.md.
