# THA — Deferred Decisions

*This document is part of THA's development architecture. It is intended for maintainers rather than readers and is not part of the framework itself.*

Choices consciously postponed until a stated trigger condition is met. Not gaps (nothing predates a broken standard) and not tasks (nothing is being built now). Once a trigger fires, the entry resolves into a new ADR or Implementation Task — it is not edited in place.

---

## DD-001 — Contributor architecture

**Trigger:** THA's first external contributor.
**Status:** Deferred.
**Description:** Contribution workflow, evidence standards, style guide, proposal process, and review process are intentionally undesigned. These are best shaped by real friction — what contributors actually get wrong, how disagreements actually arise — rather than guessed at in advance. Maintainer documentation (ARCHITECTURE.md, LEGACY_GAPS.md, IMPLEMENTATION_TASKS.md) is sufficient until this triggers.
**Resolves to:** One or more new ADRs covering contributor workflow, once triggered.
