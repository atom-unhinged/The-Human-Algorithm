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
