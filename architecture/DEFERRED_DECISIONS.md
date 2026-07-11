# THA — Deferred Decisions

*This document is part of THA's development architecture. It is intended for maintainers rather than readers and is not part of the framework itself.*

Choices consciously postponed until a stated trigger condition is met. Not gaps (nothing predates a broken standard) and not tasks (nothing is being built now). Once a trigger fires, the entry resolves into a new ADR or Implementation Task — it is not edited in place.

---

## DD-001 — Contributor architecture

**Trigger:** THA's first external contributor.
**Status:** Deferred.
**Description:** Contribution workflow, evidence standards, style guide, proposal process, and review process are intentionally undesigned. These are best shaped by real friction — what contributors actually get wrong, how disagreements actually arise — rather than guessed at in advance. Maintainer documentation (ARCHITECTURE.md, LEGACY_GAPS.md, IMPLEMENTATION_TASKS.md) is sufficient until this triggers.
**Resolves to:** One or more new ADRs covering contributor workflow, once triggered.

## DD-002 — Canonical term removal and aliasing

**Trigger:** The first time a canonical term in DEFINITIONS.md is actually removed or renamed.
**Status:** Deferred.
**Description:** DEFINITIONS.md is strictly current-state — it describes today's vocabulary, not its history. Working assumption for when this triggers: the canonical entry is removed outright; an alias is retained only where old notes or external links would otherwise break; no historical definitions are kept inside the main artifact. History belongs in Git and ADRs, not in the specification itself. Undesigned until a real removal forces the question.
**Resolves to:** An ADR covering term-removal and aliasing mechanics, once triggered.

## DD-003 — Relationship ownership between semantic and conceptual artifacts

**Trigger:** CONCEPTS.md (Map's authored source) exists and its relationship to DEFINITIONS.md's term-level dependencies can be evaluated against real content.
**Status:** Deferred.
**Description:** Closed-vocabulary parsing of DEFINITIONS.md yields a semantic graph — canonical terms referencing other canonical terms where genuinely necessary to the definition. This is a different, sparser graph than the curated conceptual relationships CONCEPTS.md will hold, and the two are not guaranteed to sit at the same level of abstraction (a Map concept may cover multiple Definitions terms, or vice versa — ADR-001 does not assume a 1:1 mapping). Whether the semantic graph should inform Map's curation, remain fully independent, or share tooling is undesigned until CONCEPTS.md's actual ontology exists to test it against.
**Resolves to:** An ADR (if the two should formally interact) or a note confirming they remain intentionally separate, once triggered.

## DD-004 — Verification timing for derived-view prose

**Trigger:** The next time a derived textual view (a rendering of an authored source — Definitions, Map, or a future artifact) requires new prose not reused directly from its source.
**Status:** Deferred.
**Description:** During the Concepts-page implementation, new connective prose was written, presented as complete across several turns, and only checked line-by-line against CONCEPTS.md when it was explicitly asked whether that check had occurred. The check surfaced a real misattributed claim in the Practices paragraph. What's cleanly observed from this single cycle: the verification that eventually happened was reactive, prompted by a question, not a default step performed before the work was presented as finished. What's not yet established: whether the actual fix is minimizing new prose, mandating verification regardless of prose volume, or both — this cycle changed both at once and can't isolate which one mattered. One occurrence isn't enough to call this a recurring failure mode rather than a single lapse.
**Resolves to:** An ADR specifying when derived-view verification is required and by what method (a candidate: extending ARCHITECTURE.md's existing Editorial Test — modality preservation in particular — from Definitions edits to derived-view prose generally), if the same reactive-not-default pattern recurs. Or a note confirming this was situational, if a subsequent case shows verification happening by default without being prompted.

## DD-005 — Notes-to-linked-file conversion

**Trigger:** A specific note (or category of notes) shows drift between its vault `.md` copy and its embedded index.html copy in a way that causes a real, live error on the site — not a theoretical risk.
**Status:** Deferred.
**Description:** Every framework note currently exists twice: as a `.md` file in the vault, and as HTML embedded directly inside index.html. These are two separate copies with no automatic sync, and drift between them has already happened at least once in practice — a corrected claim in the Trustless Architecture note (an inaccurate Genesis Block/Romans reference) was fixed in the `.md` file but remained live on the site for an extended period, because the site only ever reads the embedded copy. Articles do not have this problem, structurally: index.html only links to article files rather than embedding their content, so there is only one copy to begin with. The same fix — standalone linked files instead of embedded HTML — would solve this for notes too, but converting every note at once would lose the current instant single-page toggle (notes display instantly today via a JavaScript class-toggle, since all content is already loaded in the page; converting to separate files means either real page navigation, simpler but a beat slower, or client-side live-fetching, which preserves the instant feel at the cost of real added complexity). Most notes rarely change once published and don't need this. The clearer candidates are notes expected to change often — architecture and process documents, and any note still actively being iterated before it's settled (the pending J-space note, for one).
**Resolves to:** An ADR specifying which notes convert to standalone linked files, which mechanism (plain navigation vs. live-fetch), and which notes remain embedded, once a specific note's drift causes a real error rather than a hypothetical one.

## DD-006 — Formal stress-testing process

**Trigger:** A section of the framework is stable enough that adversarial testing would surface genuine unresolved flaws, rather than just documenting an intentionally unfinished draft.
**Status:** First cycle complete. Methodology v0.1 executed once (ST-001), independently reviewed by two additional models, in the private THA-Lab repository. Not yet formalized as an ADR in this repository.
**Description:** ST-001 produced 14 scoped findings plus one reviewer-caught addition. All 15 are now resolved — 14 fixed, 1 refuted on independent review. Full detail: THA-Lab, `stress-tests/ST-001/ST-001-reconciliation.md`.
**Resolves to:** An ADR defining the stress-testing process — cadence, who or what performs it, and the decision tree for revise vs. flag vs. retract — once the methodology and its first results have been reviewed and judged ready to formalize.

## DD-007 — Interactive site map / dependency graph

**Trigger:** The framework has enough stable, cross-linked notes that a visual map would clarify its actual shape, and there is bandwidth to build and maintain it as its own artifact.
**Status:** Deferred.
**Description:** Framework notes already cross-reference each other extensively via internal links. A visual, interactive graph — notes as nodes, their links as edges — could make that structure visible at a glance, in the spirit of the Dependency Graph already planned as part of the five-artifact Guidebook. Undesigned: what renders it, whether it lives as its own page or inside index.html, whether it auto-generates from existing note links or needs separate curation, and how it avoids becoming a second sync-risk sitting on top of the one described in DD-005 rather than being solved alongside it.
**Resolves to:** An ADR covering the graph's implementation and how it stays in sync with the notes it maps, once triggered.

