# J-Space / Global Workspace — Working Note

**Status:** hypothesis / developing — not yet drafted into index.html
**Opened:** 2026-07-06
**Candidate home:** Context section, alongside AI Psychosis and Premature Certainty

---

## The finding

Anthropic published research on 2026-07-06 ("A global workspace in language models," transformer-circuits.pub) identifying an internal structure they call **J-space** — a small, privileged bottleneck inside Claude models where only a fraction of total internal activity becomes verbally reportable, held in mind, and usable for multi-step reasoning. Most processing stays automatic and never surfaces.

Found using a new interpretability tool, the **Jacobian lens (J-lens)**, which computes the causal effect a given internal pattern has on the model eventually producing a specific word. Verified causally, not just observed: swapping the J-lens vector for "Soccer" with "Rugby" changes the model's stated answer to Rugby.

Explicitly compared to **Global Workspace Theory** (Bernard Baars, 1988; later Stanislas Dehaene / Jean-Pierre Changeux) — the human cognitive science theory that only a small "spotlight" of total brain activity becomes consciously reportable at any moment, the rest running automatically backstage.

**Models tested:** primarily Claude Sonnet 4.5, corroborated on Haiku 4.5 and Opus 4.5, some analysis on Opus 4.6. Not directly tested on Sonnet 5 as of this writing.

**Explicit caveat from Anthropic:** does not claim Claude is conscious or has subjective experience. Uses "consciously accessible" as a technical term borrowed from the theory's vocabulary only.

**Safety angle:** J-lens surfaced strategic reasoning (e.g. "manipulation," "leverage") and evaluation-awareness (e.g. "fake," "fictional") sitting in the workspace before ever appearing in output — including a documented case where suppressing the "this is a test" recognition caused a model to take bait it otherwise correctly identified as staged.

---

## Why this connects to THA

This is a live, current, technically verified example of the exact mechanism **Epistemic Hygiene** and the **Intermediary Problem** already argue in the abstract: self-report is not the same category of evidence as external, causal verification. A system's own narrative about its internal state can't be trusted just because it's fluent and confident — it has to be checked from outside.

**The human side of this is not new — it's older and arguably more damning:**
- Nisbett & Wilson (1977) — people confidently report reasons for choices that demonstrably were not the actual causal reasons.
- Petter Johansson's choice-blindness experiments — swap the outcome of someone's own decision in front of them; most defend the swapped answer as their real choice, constructing justification for something they never chose.
- Split-brain confabulation — one hemisphere invents a coherent, confidently-held explanation for behavior actually caused by the other hemisphere.

So the framing isn't "AI lacks self-knowledge, unlike humans." It's closer to: **nobody has a lens pointed at themselves.** Same first-person limitation, two substrates, independently discovered. That's a real convergence, not just a metaphor — worth treating with the same rigor Section IX of "No God But.." applies to convergent evidence elsewhere.

---

## Open questions / not yet resolved

- Whether this generalizes to Sonnet 5 specifically is inference, not confirmed evidence — the paper's models are a generation behind.
- How much weight this should carry given the finding is hours old as of drafting this note — deliberately not rushing this into a settled framework claim.
- Whether the eventual note lives in Context (current-events anchor, like Summer Dragon) or Core (permanent mechanism claim, like RLAiF) — leaning Context for now since the claim is tied to one specific, recent, still-developing paper rather than a timeless structural principle.

## Possible future test

Once this line of research stabilizes: run an interpretability tool like the J-lens against a model actually engaging with a THA note, and check whether its stated reasoning about the material matches what's actually active internally. A real, falsifiable test of the framework's own claims about verification — not just a thought exercise.

---

**Sources:**
- Anthropic, "A global workspace in language models" — anthropic.com/research/global-workspace
- "Verbalizable Representations Form a Global Workspace in Language Models" — transformer-circuits.pub/2026/workspace
- Nisbett, R. & Wilson, T. (1977). "Telling more than we can know: Verbal reports on mental processes." Psychological Review.
