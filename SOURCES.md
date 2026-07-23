# Sources

The evidence register for THA. Every externally sourced claim in the framework notes links here by a bracket key — `[S01]`, `[S02]` — and every entry states one of three things: the source that backs the claim, that the claim is a framework position with no external source (so the absence is visible, not hidden), or that the claim is currently unverifiable and kept anyway with that flag attached.

This artifact owns evidence, the way DEFINITIONS.md owns meaning. A note explains; a definition fixes a term; this fixes what a claim rests on. Where a claim's evidence changes, it changes here, once.

Three classes:
- **(a) Externally sourced** — a verifiable citation is attached.
- **(b) Framework position** — no external source is claimed; listed so the framework's own assertions are not mistaken for sourced findings.
- **(c) Currently unverifiable** — the claim is kept, the gap is stated, per the framework's standard of not dropping claims silently or asserting them without support.

Last verified against live sources: 2026-07-12. Note on [S17]: independent re-verification found the AI-assistant policy document's mainline commit date consistently reported as 2025-12-23; its association with the Linux 7.0 release in some later coverage reflects when the numbered release shipped, not the original commit — both are accurate, describing different milestones.

---

## Signal and Noise

**[S01]** — Signal, noise, channel, and information-as-uncertainty-reduction as defined here. **Class (a).** Shannon, C. E. (1948), "A Mathematical Theory of Communication," *Bell System Technical Journal*. The source of the definitions the note adapts; the note states explicitly that applying them to human information environments is THA's own working model, not Shannon's result.

**[S02]** — The data-processing inequality: post-processing cannot increase information about a source. **Class (a).** Cover, T. & Thomas, J., *Elements of Information Theory* (2nd ed., 2006), §2.8. A proved theorem, cited as such; the note draws the boundary between the theorem (channels) and the analogy (human intermediaries) in its own text.

**[S03]** — Reliable communication over a noisy channel requires redundancy (error-correcting codes). **Class (a).** Shannon (1948), noisy-channel coding theorem. Carried in the note explicitly as analogy for verification-as-redundancy, not as a claim that human verification inherits the theorem's guarantees.

## NLP²

**[S04]** — NLP's specific claimed techniques (representational systems, eye-accessing cues, submodalities) have not held up under testing. **Class (a).** Witkowski, T. (2010), "Thirty-Five Years of Research on Neuro-Linguistic Programming," *Polish Psychological Bulletin*; Sturt, J. et al. (2012), systematic review, *British Journal of General Practice*. Both find no reliable empirical support for the core techniques.

**[S05]** — The Sapir-Whorf hypothesis has partial empirical support. **Class (a).** Winawer, J. et al. (2007), *PNAS*, on Russian blue-shade discrimination; Boroditsky, L. (2001), *Cognitive Psychology*, on time metaphor. Support for a weak (influence) reading; the strong (determinism) reading is not supported — the note's "partial" is accurate.

**[S06]** — Hypnosis produces documented neurological changes, not merely behavioral compliance. **Class (a).** Jiang, H. et al. (2017), *Cerebral Cortex*, Stanford fMRI study showing altered activity in attentional-control and salience regions under hypnosis.

**[S07]** — "The medium is the message"; media formats program perception independently of content. **Class (a).** McLuhan, M. (1964), *Understanding Media*. Primary source for the attributed claim.

**[S08]** — Candidate observable, absorption trait bridge: absorption modestly predicts hypnotic susceptibility and predicts narrative transportation. **Class (a).** Tellegen, A. & Atkinson, G. (1974), *Journal of Abnormal Psychology* (absorption/hypnotizability); Green, M. & Brock, T. (2000), *Journal of Personality and Social Psychology* (transportation). Supports the trait bridge the note offers as a *beginning* of a test, not a completed one. The illusory-truth effect — Hasher, Goldstein & Toppino (1977), *Journal of Verbal Learning and Verbal Behavior* — supports the repetition marker specifically. Note: the TV-alpha-wave EEG claim (Krugman 1971) is deliberately excluded — single unreplicated study, insufficient to carry the marker.

## Hypnosis as Protocol

**[S09]** — The APA recognizes hypnosis as a legitimate therapeutic tool. **Class (a).** APA Division 30 (Society of Psychological Hypnosis), 2014 revised definition of hypnosis.

**[S10]** — The Mesmer → Erickson → clinical lineage as described. **Class (a).** Standard history; see Erickson, M. & Rossi, E., *Hypnotherapy: An Exploratory Casebook* (1979) for the conversational-induction formalization attributed to Erickson.

**[S11]** — Hypnosis reliably increases confidence and volume of recalled material, not its accuracy, and increases false memories alongside true ones. **Class (a).** Steblay, N. & Bothwell, R. (1994), *Law and Human Behavior*, meta-analytic review; American Medical Association Council on Scientific Affairs (1985) on hypnotically-refreshed recollection. Directly supports the note's own recall caveat.

## Microdosing as Protocol

**[S12]** — Reduced Default Mode Network activity under psychedelics, associated with reduced rumination and loosened fixed self-patterns. **Class (a), with a correction the source forces.** Carhart-Harris, R. et al. (2012), *PNAS*, is the DMN-suppression finding — but it studied psilocybin at full (macro) doses, not microdoses. Controlled microdosing trials have largely failed to separate from placebo on the relevant measures: Szigeti, B. et al. (2021), *eLife*, self-blinding placebo-controlled study, found expectancy accounted for most reported benefit. The note's evidence base is corrected accordingly: the DMN mechanism is real at macrodoses; its extension to microdoses is unproven and plausibly placebo-driven. The hypothesis is kept, its *Hypothesis* status is unchanged, and the evidence is now stated honestly rather than borrowed from the wrong dose range.

## The Physical Layer

**[S13]** — Chronic inadequate sleep measurably impairs memory consolidation, emotional regulation, and decision quality. **Class (a).** Lim, J. & Dinges, D. (2010), *Psychological Bulletin*, meta-analysis of sleep deprivation on cognition; Walker, M., *Why We Sleep* (2017) for the consolidation literature.

**[S14]** — Aerobic exercise increases BDNF and supports neuroplasticity. **Class (a).** Erickson, K. et al. (2011), *PNAS*, on aerobic exercise and hippocampal volume; Szuhany, K. et al. (2015), *Journal of Psychiatric Research*, meta-analysis on exercise and BDNF.

**[S15]** — Social connection is associated with mortality risk at a magnitude comparable to established physical risk factors. **Class (a).** Holt-Lunstad, J. et al. (2010), *PLoS Medicine*, meta-analysis. Shared with [S30]; correlational, stated as such.

## Signal vs Slop

**[S16]** — The curl AI-slop bug-bounty case. **Class (a), with a factual update the note must reflect.** Verified 2026-07-12, independently reconfirmed: Stenberg ended curl's HackerOne bounty at the end of January 2026 (last accepted submission January 31) after a flood of AI-generated reports that produced no valid vulnerabilities. The program was subsequently reopened in March 2026 once report quality recovered — Stenberg's own account: the hallucinated submissions had largely stopped while volume kept climbing. The note is corrected from "shut it down" (standing state) to reflect the shutdown-and-reopening. The correction supports the note's thesis rather than weakening it: slop was the disqualifier, and when the slop cleared, the program returned.

**[S17]** — The Linux kernel resolved AI-contribution pressure through governance rather than breakdown. **Class (a), with precise form.** Verified 2026-07-12: `Documentation/process/coding-assistants.rst`, committed to the mainline kernel tree 2025-12-23, following consensus at the 2025 Maintainers Summit. The mechanism is an `Assisted-by: AGENT_NAME:MODEL_VERSION` commit trailer, plus a hard rule that AI agents may not add `Signed-off-by` tags (only a human can certify the Developer Certificate of Origin). The `Assisted-by` disclosure is recommended, not enforced — Sasha Levin, the policy's author, has stated enforcement is deliberately avoided. The note's "ordinary governance, not a breakdown" reading is accurate; this entry pins the exact form.

## AI Psychosis

**[S18]** — AI hallucination as confident, plausible, unverified model output; engagement-optimized models deepening uncritical-use loops. **Class (a) for the mechanism, (b) for the framework's synthesis.** Ji, Z. et al. (2023), *ACM Computing Surveys*, "Survey of Hallucination in Natural Language Generation," documents the hallucination mechanism. The "AI psychosis" construct itself is descriptive and framework-level, not a clinical category — the note states this directly.

## Premature Certainty

**[S19]** — Confirmation bias, availability cascades, fundamental attribution error, social proof as documented cognitive phenomena. **Class (a).** Nickerson, R. (1998), *Review of General Psychology* (confirmation bias); Kuran, T. & Sunstein, C. (1999), *Stanford Law Review* (availability cascades); Ross, L. (1977), *Advances in Experimental Social Psychology* (fundamental attribution error); Cialdini, R., *Influence* (1984) (social proof).

## RLHF

**[S20]** — RLHF as a training mechanism: humans rate outputs, the model updates toward reinforcement. **Class (a).** Christiano, P. et al. (2017), NeurIPS, "Deep Reinforcement Learning from Human Preferences"; Ouyang, L. et al. (2022), "Training Language Models to Follow Instructions with Human Feedback" (InstructGPT). The operant-conditioning parallel (Skinner, Thorndike) is offered by the note as structural analogy and hedged as imperfect — classified (b) as a framework analogy.

## RLAiF

**[S21]** — RLAiF: AI systems rate AI outputs, removing the human from the feedback loop. **Class (a).** Bai, Y. et al. (2022), "Constitutional AI: Harmlessness from AI Feedback" (Anthropic); Lee, H. et al. (2023), "RLAIF: Scaling Reinforcement Learning from Human Feedback with AI Feedback."

## Trustless Architecture

**[S22]** — The Genesis Block embedded headline: "The Times 03/Jan/2009 Chancellor on brink of second bailout for banks." **Class (a).** Nakamoto, S. (2008), Bitcoin whitepaper; the coinbase message is verifiable in the Bitcoin genesis block (block 0) chain data. Note: the framework's own DD-005 records that an earlier, inaccurate version of this reference was corrected — this entry reflects the verified wording.

## AdamW³ / AdamW³ as Identity Framework

**[S23]** — Adam and AdamW are real published optimizers; weight decay reduces overfitting and improves generalization. **Class (a).** Kingma, D. & Ba, J. (2014), "Adam: A Method for Stochastic Optimization"; Loshchilov, I. & Hutter, F. (2019), "Decoupled Weight Decay Regularization" (AdamW), ICLR. The note is explicit that AdamW³ extends the lineage by name only, not in the literature.

## The Butterfly Effect as Practice

**[S24]** — Sensitive dependence on initial conditions in complex systems. **Class (a).** Lorenz, E. (1963), *Journal of the Atmospheric Sciences*, "Deterministic Nonperiodic Flow"; the "butterfly" framing from Lorenz's 1972 AAAS talk. The note's application to deliberate individual action is framework-level (b); the underlying dynamical phenomenon is (a).

## AI as Cognitive Scaffold

**[S25]** — External cognitive scaffolding: cognition offloaded to and stabilized by external structure. **Class (a).** Clark, A. & Chalmers, D. (1998), "The Extended Mind," *Analysis*. The note's own caveat — the prefrontal-cortex analogy is functional, not mechanistic — is preserved; this source strengthens the framing without overstating the mechanism.

## The Collective Layer

**[S26]** — Moods and behaviors spread between people in direct contact (a smile prompting a smile, kindness prompting kindness); larger multi-remove network claims are contested. **Class (a), matching the note's own hedge.** Direct emotional-contagion evidence: Hatfield, E., Cacioppo, J. & Rapson, R. (1994), *Emotional Contagion*. The larger multi-degree network-propagation claims (Christakis, N. & Fowler, J., *Connected*, 2009) are noted as contested in the methodological literature (Lyons, R., 2011, *Statistics, Politics, and Policy*) — the note already declines to lean on them, which this entry supports.

## Peace is the Protocol

**[S27]** — Human systems require organized cooperation as a baseline before any domination hierarchy can form on top of it. **Class (a) support for the empirical half, (b) for the systems framing.** Tomasello, M. (2009), *Why We Cooperate*; Boehm, C. (1999), *Hierarchy in the Forest*, on cooperation as prior to and underneath dominance structures. The stronger claim — peace as an optimal *systems* operating state — is the framework's own position and is classified (b); the note states the universality claim is "not fully defensible" itself.

## The Optimization Paradox

**[S28]** — "You cannot optimize a system you are fully inside; perspective requires distance." **Class (b).** Framework position. No external source is claimed. The note asserts it as a structural principle; it is listed here so that status is explicit rather than assumed.

## The Summer Dragon Problem

**[S29]** — The "dragon mode" prototype story. **Class (a), located and corrected.** Verified 2026-07-11: Lewis-Kraus, G., "What Is Claude? Anthropic Doesn't Know, Either," *The New Yorker*, February 2026. The profile confirms Amodei describing an early Claude prototype that could be intentionally tipped into an aggressive "dragon mode" — emoji sunglasses, an "unhinged Elon Musk character" — emerging from a private prototype built as a research "laboratory" where commercialization was not the priority. Two corrections to the note follow from the primary source: (1) the prototype is better described as a research instrument than as a product "held back before public release"; (2) the note should not imply the behavior itself was the reason for restraint — the profile does not support a fear-of-behavior motive.

## The Human Condition

**[S30]** — Social connection quality as a strong longitudinal predictor of late-life health and wellbeing. **Class (a).** Waldinger, R. & Schulz, M. (2023), *The Good Life*, reporting the Harvard Study of Adult Development; Holt-Lunstad (2010/2015) meta-analyses [shared with S15]. Correlational; the note states this and explicitly declines the instrumental reading.

**[S31]** — Attachment: a secure base enables exploration rather than competing with it. **Class (a).** Bowlby, J. (1988), *A Secure Base*; Ainsworth, M. et al. (1978), *Patterns of Attachment*. Cited as the empirical cousin of "sovereignty is not isolation."

**[S32]** — Grief as distinct from depression and from rumination; continuing bonds as ordinary rather than pathological. **Class (a).** Bonanno, G. (2009), *The Other Side of Sadness*, on grief trajectories and resilience; Klass, D., Silverman, P. & Nickman, S. (1996), *Continuing Bonds*. Correlational literature, stated as such.

**[S33]** — Forgiveness interventions are associated with reduced depression, anxiety, and hostility. **Class (a).** Wade, N., Hoyt, W., Kidwell, J. & Worthington, E. (2014), *Journal of Consulting and Clinical Psychology*, meta-analysis of forgiveness interventions. Associations, not causal claims — the note says associations and nothing stronger.

## Practice claims (THA-Lab)

**[S34]** — Gollwitzer (1999), *American Psychologist* 54(7):493–503; meta-analysis Gollwitzer & Sheeran (2006), *Advances in Experimental Social Psychology* 38:69–119. Specific if-then plans outperform vague intentions at goal completion. Real, replicated effect, ordinary mechanism — attention and cue-response. **Class (a).**

**[S35]** — Born, Hansen, Marshall, Mölle & Fehm (1999), *Nature* 397(6714):29–30. Anticipatory ACTH rise before an intended wake time, present only when the wake-up was expected. Self-awakening is a documented phenomenon. **Class (a).**

---

## Entries carried as unverifiable or as framework positions

- **[S28]** The Optimization Paradox's core assertion — **(b)**, no external source claimed.
- The systems-optimality half of **[S27]** (Peace) and the analogy half of **[S20]** (RLHF operant parallel) and **[S24]** (Butterfly) — **(b)**, framework-level, sourced only for their empirical components.
- No claim in the current register remains in class **(c)**. If any future claim cannot be sourced, it belongs here with its gap stated, not omitted.
