# Work Order — Notes-as-Pages Site Refactor

**Status:** Proposed. Not started. No implementation until explicitly confirmed.
**Filed:** 2026-07-07
**Site:** https://adamwarren3.github.io/tha/

---

## Trigger

Fixing the old-domain links (atom-unhinged/The-Human-Algorithm → adamwarren3/tha) across the 32 note files surfaced the underlying issue directly: those links live in the `.md` notes, but the live site's note content is a *separate*, hand-duplicated copy embedded inside `index.html`. Fixing one doesn't fix the other. This is the same class of problem as LG-001 (nav sidebar duplicating note metadata) — already closed — except this time it's full note *content* duplicated, not just titles and tags.

## Requested scope

1. Convert the 32 notes from `.md` to standalone `.html` pages — one file per note, same pattern as `/Articles`.
2. Have the live site link to / fetch those pages directly, rather than embedding all 32 notes' content inline in `index.html`.
3. Rename `/Articles` to `/articles` (lowercase, for consistency).
4. Update all internal links to the new site address as part of the same pass.

## Why this matters (steelmanning the request)

Right now there are at least three copies of note content in play: the `.md` vault file, the derived Definitions/Concepts pages, and the hardcoded `<div class="note">` block inside `index.html`. Only one of those is supposed to be authoritative per ADR-001 (Single Source of Truth). Collapsing the site's copy into something generated from — or fetched directly from — the real notes removes an entire class of future drift, permanently, rather than catching each instance of it after the fact the way this session has been doing.

## Risks and open questions — read before starting

**"Notes become HTML" has a bigger consequence than it sounds like: it may end vault editing for those 32 files.** The notes are currently Obsidian markdown — that's how they get authored and edited. If the canonical version becomes hand-written `.html`, Obsidian can no longer open or edit them; the authoring workflow that's been used for this entire project changes. Worth deciding explicitly whether that's intended, or whether:

**Alternative worth considering instead of hand-converting:** keep `.md` as the authored source (matching how Definitions/Concepts already work — markdown in, HTML generated out) and add a build step that *generates* one `.html` file per note from its `.md` source automatically. Same practical outcome — one fetchable address per note, no embedded duplication — without giving up Obsidian as the editing tool, if Obsidian re-enters the workflow later (currently not in use, per 2026-07-07 — not a blocking concern today, but worth keeping in mind if a v2 restructure brings it back).

**Resolved, 2026-07-07 — where automation would run and where output would land.** The conversion would run as a GitHub Action, same mechanism already used for `sitemap.xml`: triggers on push, reads each `.md`, writes the matching `.html`, commits it back. Where the output lands is a real fork, not a detail:
- **Embed into `index.html`** — fixes the drift problem only; doesn't achieve parity with `/Articles`. Smaller, safer, but not what was originally asked for.
- **Standalone file per note** (matches `/Articles`) — real per-note addresses, shareable and indexable. Splits further into plain-link-full-page-load (loses the persistent sidebar on note pages, matching how Articles behave today) vs. fetch-on-click (keeps the sidebar and current feel, but the note doesn't get a real shareable URL without extra work updating the address bar on load).

Current leaning: standalone files, fetch-on-click — closest to today's feel while still fixing the duplication. Not yet confirmed.

**Fetching content at runtime has a real trade-off, not just an upgrade.** The current site is instant — every note is already in the page, no network request per click. A fetch-per-note model means each note load becomes an HTTP request. Fine on a fast connection, a real (if probably small) regression on a slow one. Worth deciding if that's an acceptable trade for removing the duplication.

**The `/Articles` → `/articles` rename has no safety net.** Unlike the GitHub username/repo rename, which gets an automatic redirect from GitHub, renaming a folder inside a repo does not — any link anywhere on the internet currently pointing at `Articles/...` (shared links, bookmarks, search engine index) breaks permanently the moment the folder is renamed, unless old paths are deliberately kept as redirect stubs. Worth deciding whether that's acceptable before doing it, given the articles are the most likely thing to have been shared externally.

**Scope of the link-touch is large.** The new site address needs to land in: every note that currently links to another article (already catalogued in this session), `README.md`, the sitemap workflow, and now also every generated/converted note page's own internal cross-links — effectively a full-repo pass, not a small edit.

## Dependencies / sequencing

- The current in-progress fix (old-domain links across the 12 files already identified) should finish first — no reason to block it on this.
- If pursued, this likely needs its own Deferred Decision or Architecture Decision Record before implementation, given it changes what "authored source" means for the 32 notes — consistent with how Definitions/Concepts changes were handled earlier.

## Not yet decided

- Hand-convert to HTML vs. generate HTML from markdown (recommend the latter, not decided).
- Fetch-per-note vs. some other loading strategy.
- Whether to leave redirect stubs at the old `/Articles` paths.
- Folder name and home for this and future work orders in THA-Lab.
