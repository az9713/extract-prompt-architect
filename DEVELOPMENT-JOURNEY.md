# Development Journey — From One Dense Source to a Reusable Extraction-Prompt Skill

**Purpose of this document.** A faithful, end-to-end record of how a single
analysis task (mining one paywalled research article) was generalized into a
reusable Claude Code skill (`extraction-prompt-architect`). It captures the
inputs, the sequence of work, every meaningful decision fork, the mistakes made
and corrected, and the artifacts produced. It is written to be used later as an
audit trail: to judge (a) the quality of the *decision process* and (b) the
quality of the *prompts and the skill* that came out of it.

No personal paths, names, or identifiers are included; files are referenced by
base name only.

---

## 0. How to read this document

- **§1** — the raw starting materials.
- **§2** — the chronological narrative, phase by phase, with the fork at each step called out inline.
- **§3** — a consolidated decision-fork table (the same forks, but side-by-side with "how to judge this later").
- **§4** — artifacts produced.
- **§5** — the workflow's evolution (the original 5 steps → the final 6).
- **§6** — the two blind-spot prompts and why they were the crux.
- **§7** — a rubric for judging quality later.
- **§8** — open risks and unmeasured claims a skeptic should re-check.
- **§9** — lessons.

---

## 1. Starting materials

Four inputs existed at the start:

1. **The source article** — a saved web page (`.mhtml`) of a SemiAnalysis
   research note, *"US Grid Constraints: Towards 40GW+ of Behind-The-Meter
   Datacenter by 2028?"* (dated mid-2026). A long, dense, **vendor/sell-side**
   note. Crucially, it is **paywalled**: the public/saved portion stops at the
   "Winners and Losers" section, so the named equity calls were not in the
   saved copy.
2. **`README.txt`** — a short orientation note (defined "BTM" = Behind-The-Meter
   and summarized the thesis).
3. **`gpt5.5_summary.txt`** — a transcript excerpt of a prior ChatGPT session.
   At first this appeared to contain only a *meta-pattern* plus a *master
   extraction memo*. It was **later expanded by the user** to also contain the
   full **15 numbered prompts** (plus a dimensions section) — the actual
   artifact under evaluation.
4. **A ChatGPT "share" link** — a public mirror of that same conversation.

The user's standing methodology (recorded in the transcript) was a four-move
meta-pattern: *map orthogonal dimensions → generate high-leverage prompts from
them → recommend the minimal subset → explain what is lost by skipping the
rest.*

---

## 2. The narrative, phase by phase

### Phase 1 — Ingest and read

- Decoded the `.mhtml` to plain text (it is quoted-printable HTML); confirmed the
  article is complete up to the paywall cut at "Winners and Losers."
- Read `README.txt` and `gpt5.5_summary.txt`.
- Attempted to read the ChatGPT share link with the standard fetch tool →
  **failed** (login wall / JS-rendered shell returned an empty template).

**Fork A — how hard to chase the share link.** Options: (i) give up on it, (ii)
fetch via the logged-in browser. Chose (ii) later, when it became necessary.
*Why it mattered:* the share link was assumed to hold the prompt set; verifying
that assumption (rather than trusting it) changed the next phase.

**Finding that reframed everything:** the browser pull of the share link
revealed it contained only the meta-pattern + the master memo + a closing list
of *5 "next prompts"* — **not** the 15 prompts. The memo had also been built on
the *free* portion of the article only. So at this point the "16 prompts" the
user referred to were **not visible in any material on hand.**

### Phase 2 — Refusing to assess an unseen artifact

When asked to assess "the dimensions and quality of the 16 prompts," the honest
state was: *the prompts were not in front of me.*

**Fork B — assess from memory/inference, or insist on the real artifact.**
Chose to **state plainly that the prompts were not visible** and decline to
grade them, while still delivering what *could* be grounded (an assessment of
the dimensional framework and the maximal-extraction question). The user then
**expanded `gpt5.5_summary.txt`** to include the actual 15 prompts (§2–§16) plus
the dimensions table (§1).

*Why this fork matters for quality-judging:* the alternative — fabricating an
assessment of prompts inferred from context — would have looked productive and
been worthless. The decision to block on the real artifact is the single most
important *process* decision in the whole journey.

**A self-correction also happened here.** An earlier comment had criticized two
dimensions ("geopolitical" as poor-fit, "temporal" as underpowered). That
critique was aimed at the *generic meta-pattern* list. When the *real* dimension
table appeared, it used "Geography / site-selection" and "Timing mismatch" —
both good fits — so the critique was explicitly retracted. A numbering error was
also corrected (the ERCOT prompt is §6, not §5; §5 is "AI scaling"). Capturing
these matters: the process self-corrected on contact with primary evidence
rather than defending the earlier take.

### Phase 3 — Assessing the 15 prompts

Each prompt was graded on four axes:

- **Leverage** (signal per token),
- **Orthogonality** (overlap with sibling prompts),
- **Source-fit** (does it bind on *this* source),
- **Falsifiability-forcing** (does it force claims to be checkable).

Result: the set was judged **strong and well-layered** (it had three things
most prompt packs lack — a recall sweep, an adversarial pass, and a
verification/diligence plan). But **two genuine blind spots survived
inspection**, both traceable to the "Model risk" dimension being scoped too
narrowly (to the article's *internal* assumptions only):

1. **Provenance / verifiability** — nothing forced a split between externally
   checkable facts and the author's unverifiable proprietary-model outputs. On a
   *vendor* source this is the highest-value missing cut.
2. **Author-incentive / reflexivity** — the adversarial prompt attacked the
   thesis *logically* but never asked *cui bono* (the author sells the models
   cited as evidence), nor modeled reflexivity (does the thesis self-defeat if
   it becomes consensus).

### Phase 4 — The distillation report (the 80/20)

Deliverable: `prompt-distillation-report.md`. Key moves:

- **Made the inclusion criterion explicit and auditable** — a prompt earns a
  minimal-set slot only if it passes all three tests: **yield**,
  **orthogonality**, **load-bearing**. Token cost is only a tiebreak.
- **Wrote the two blind-spot prompts** (provenance; author-incentive/reflexivity).

**Fork C — which blind-spot prompts make the minimal set.** Decision:

- **Provenance → INCLUDED** (placed second in run-order, right after the master
  pass, so it gates trust in every downstream number). Rationale: foundational,
  orthogonal to all 15, and on a paid note the single largest analytic error is
  mistaking a model output for a fact.
- **Author-incentive/reflexivity → EXCLUDED** from the minimal set. Rationale:
  its trust-relevant half (cui bono) folds into the adversarial prompt at near-
  zero cost, and the remainder (reflexivity) is *second-order* — it refines
  timing/crowdedness, not the base thesis. Logged as the **first add** beyond
  minimal.

- **Minimal set = 7 prompts**, with an explicit **run-order** (orient →
  trust-gate → rebuild model → rank constraints → read concrete evidence →
  adversarial → synthesize).
- **Exclusion ledger** — every omitted prompt with the exact signal forgone,
  whether it was recoverable from a set member, and which test it failed.
- **Decision-relative framing** — flagged that the minimal set depends on what
  the reader will *do* (the paywalled investment prompt "starves" for an investor;
  the operator playbook only matters to an operator).

### Phase 5 — Generalizing into a skill

**Fork D — skill vs plugin.** Chose a **single skill**. A plugin bundles
multiple skills/commands/hooks/agents and was overkill for one coherent
workflow. The plugin/automation path was noted as a *future* upgrade (auto-
*executing* a finished set as a parallel fan-out), explicitly deferred under
YAGNI.

**Fork E — keep the user's 5 steps, or improve them.** The user invited changes.
The structural gap found: the original 5 steps had **no mechanism to generate
the blind-spot prompts** — steps only produced prompts *from dimensions*, so the
distillation could only prune what the dimensions happened to surface. But the
two best prompts (provenance, reflexivity) came from noticing what *no dimension
covered*. That has to be its own step. The workflow was redesigned **5 → 6
steps** (see §5).

Deliverable: `SKILL.md` for `extraction-prompt-architect`, written to the global
skills directory, encoding the 6-step workflow, the 3-test criterion, the
standing blind-spot checklist, and a decision-relative minimal set.

### Phase 6 — Sanity test (with a baseline)

The skill-creator process was invoked. **Fork F — verification depth:** options
ranged from "stop" to a full benchmark loop; chose the **light sanity test**
(run the skill on fresh sources, eyeball the output, fix issues).

Three subagents ran in parallel on **deliberately different source types** than
the original (to test generality), plus one no-skill baseline:

- **Test A — an advice essay** (PG, *How to Do Great Work*). The skill correctly
  **down-weighted** the provenance prompt (an essay has ~no checkable facts),
  folded survivorship bias into the adversarial prompt, **promoted ontology +
  recall** as the high-value blind-spot adds, and ended in a weekly-action
  artifact (because the bound decision was "apply to my career").
- **Test B — an incentivized forecast** (*Situational Awareness*). **All five**
  blind-spots fired; the set was weighted half toward trust/disconfirmation; and
  the base-rate blind-spot was **spontaneously upgraded** to a date-exploiting
  "actuals scorecard" (it is now ~2 years after a dated forecast, so its own
  near-term checkpoints are gradable).
- **Baseline (no skill)** — a competent 12-question list, but it **missed the
  ontology prompt entirely** (the coined-vocabulary blind-spot the skill caught).

**Verdict:** the skill generalized, adapted to source type in *opposite*
directions, and beat the baseline on rigor + blind-spot coverage. One emergent
behavior from Test B (exploit the current date to grade already-resolved
predictions) was judged broadly useful and **folded back into the skill's
base-rate checklist item.**

### Phase 7 — Trigger optimization: attempted, then abandoned

Goal: tune the skill's `description` so it auto-fires on the right requests and
stays quiet on near-misses. A 20-query eval set was built (10 should-trigger, 10
tricky near-miss should-not-trigger).

**Two independent blockers surfaced:**

1. The optimizer's *improvement* step uses the Anthropic SDK, which needs an API
   key — not present under subscription auth.
2. The *measurement* step (spawning nested `claude -p` subprocesses to observe
   real triggering) returned **all-zero triggers across all 20 queries** —
   including dead-obvious positives. Diagnosis: each nested invocation re-runs
   the full global `SessionStart` hook stack, flooding every subprocess so the
   triggering proxy never fired and/or timed out. This is an **instrument
   failure** (the measuring tool read zero, like a broken scale), not a verdict
   on the description.

**Fork G — adapt, relocate, or accept.** Options: (i) substitute myself as the
improver and keep the broken measurement (rejected — no trustworthy signal),
(ii) relocate the eval to a clean environment / API key (deferred), (iii)
**accept the description as-is** (chosen). Rationale: the description is explicit
and well-scoped, the sanity-test subagents found the skill without trouble, and
the near-miss negatives are well-covered by construction. Triggering quality is
therefore accepted on *judgment*, not measurement — and that limitation is
recorded honestly (see §8).

---

## 3. Consolidated decision-fork table

| Fork | Options | Chosen | Rationale | How to judge it later |
|------|---------|--------|-----------|-----------------------|
| **A** Chase the share link | Drop it / browser-fetch | Browser-fetch | Verify the assumption that it held the prompts | Did verifying change the plan? (Yes — it revealed the prompts weren't there.) |
| **B** Assess unseen prompts | Infer & grade / block on the artifact | Block | Grading fabricated prompts is worthless | The cleanest correct call; would have been the worst error to skip |
| **C** Blind-spot prompts into minimal set | Both in / both out / split | Provenance in, reflexivity out | Provenance gates trust (foundational); reflexivity is second-order and folds into adversarial | Is provenance genuinely load-bearing and reflexivity genuinely second-order? Re-test on a non-vendor source |
| **D** Skill vs plugin | Skill / plugin | Skill | One coherent workflow; plugin is for bundles | Did a plugin ever become necessary? (Only if auto-execution is added) |
| **E** Keep 5 steps vs redesign | Keep / improve | Redesign to 6 | Original had no step to *generate* blind-spots | Does Step 3 (blind-spot pass) earn its place on new sources? |
| **F** Verification depth | Stop / sanity / full benchmark / triggering-only | Sanity test | Cheap, catches the obvious failures | Did the sanity test catch real issues? (Yes — surfaced the date-exploit improvement) |
| **G** Trigger loop after instrument failure | Fake-improve / relocate / accept | Accept as-is | No trustworthy automated signal here; description already strong | Re-run the eval in a clean env to confirm the description actually triggers well |

---

## 4. Artifacts produced

| Artifact | What it is |
|----------|-----------|
| `prompt-distillation-report.md` | The 80/20 distillation of the 15 prompts → 7, with the 3-test criterion, the two new blind-spot prompts, the exclusion ledger, and first-adds. |
| `SKILL.md` (`extraction-prompt-architect`, in the global skills dir) | The reusable 6-step skill generalized from the report. |
| `trigger-eval.json` (scratch) | A reusable 20-query triggering eval set (10 positive, 10 near-miss negative). Usable in a clean environment. |
| This document | The development journey / audit trail. |

---

## 5. Workflow evolution — the original 5 steps vs the final 6

**Original (user's):** (1) given a source, (2) orthogonal dimensions, (3)
maximal prompt set from those dimensions, (4) distill to a minimal set, (5)
copious explanation throughout.

**Structural flaw found:** steps 2→3 only generate prompts *from dimensions*, so
step 4 can only prune what the dimensions surfaced. The two highest-value
prompts came from what *no dimension named* — there was no step to find them.

**Final (6 steps):**

| Step | Name | What changed vs original |
|------|------|--------------------------|
| **0** | Profile source + bind the decision | **NEW.** Source-type × reader-decision drives dimensions *and* the minimal set. Skipping it produces generic output. |
| **1** | Derive orthogonal dimensions | + an explicit orthogonality/merge pass (the original set had ~4 of 15 dimensions that weren't independent). |
| **2** | Generate the maximal prompt set | + tag each prompt to its dimension(s); build a coverage matrix. |
| **3** | **Blind-spot / gap pass** | **NEW.** Test against a standing checklist — provenance, incentive/reflexivity, ontology, recall, base-rate — and *add* prompts. This is where the two best prompts came from. |
| **4** | Distill to the minimal set | Explicit 3-test criterion; **decision-relative**; drop **+ merge + keep** (not just drop); emit a run-order. |
| **5** | Explain + exclusion ledger | Per-decision rationale + what each omission costs + recoverability + "first adds." |

---

## 6. The two blind-spot prompts (the crux)

These are the payoff of Step 3 and the clearest test of whether the process
added value beyond the original prompt set.

- **Provenance / verifiability split** — classify every consequential claim as a
  checkable fact, a proprietary-model output, a definitional convention, or an
  opinion; then rank the model-outputs by how much the thesis rides on them.
  *Verdict: included in the minimal set as the trust-gate.* On a vendor source,
  this is the highest-value addition because it changes the epistemic status of
  every number the other prompts quote.
- **Author-incentive & reflexivity** — *cui bono* (who profits from belief) plus
  reflexivity (does consensus make the thesis self-fulfilling or self-defeating).
  *Verdict: excluded from the minimal set; first add beyond it.* Its trust-half
  folds into the adversarial prompt; its remainder is second-order
  (timing/crowdedness), not thesis-establishing.

The asymmetry between these two (one in, one out) is itself the evidence that the
3-test criterion was applied as a discriminator rather than a rubber stamp.

---

## 7. Rubric for judging quality later

**Judging the prompts / the minimal set:**
- Does each minimal-set prompt pass all three tests (yield, orthogonality,
  load-bearing) on *its* source, not just generically?
- Is the run-order defensible (trust-gate before you build on the numbers)?
- Does the exclusion ledger name a *specific* signal lost per cut, with
  recoverability — or does it hand-wave?
- Is the set genuinely *decision-relative*, or one-size-fits-all wearing a label?

**Judging the skill:**
- On a new source type, does Step 0 actually steer the output (different
  source/decision → materially different dimensions and set)?
- Does Step 3 fire the *right* blind-spots for the source type (e.g. provenance
  recedes for a sincere essay, dominates for a vendor note)?
- Does it stop at *designing* the instrument, or does it bleed into running it?

**Judging the decision process:**
- Were assumptions verified against primary evidence before being built on
  (Fork A/B)?
- Were the author's own errors corrected on contact with evidence, or defended?
- Were limitations (paywall, instrument failure, unmeasured triggering) stated
  honestly rather than papered over?

---

## 8. Open risks and unmeasured claims (what a skeptic should re-check)

1. **Triggering is unmeasured.** The auto-optimization could not run here
   (instrument failure + no API key). The description is accepted on judgment.
   *Re-check:* run `trigger-eval.json` through the optimizer in a clean
   environment, or observe real-world over/under-triggering.
2. **The sanity test was small (2 sources + 1 baseline).** It demonstrated
   generality across two *types*, not robustness. *Re-check:* run more source
   types (a filing, an earnings call, a spec).
3. **Some sanity-test evidence began as subagent self-grades.** This was
   mitigated by reading the actual output files — but a fully independent grader
   was not used. *Re-check:* blind-compare skill output vs baseline with a
   neutral judge.
4. **The 80/20 criterion is judgment-laden.** "Load-bearing" and "≤~30% overlap"
   are calls, not measurements. The Fork-C split (provenance in / reflexivity
   out) is the place that judgment is most exposed.
5. **The original source was paywalled.** Every downstream assessment of the
   investment layer was made without the named winners/losers section.

---

## 9. Lessons

- **Block on the real artifact.** The highest-leverage decision was refusing to
  grade prompts that weren't visible. Inferred artifacts produce confident
  noise.
- **A "maximal" set isn't maximal until you check what no dimension covered.**
  The blind-spot pass (Step 3) was the structural insight that justified turning
  a one-off analysis into a skill.
- **Make the cut criterion explicit and auditable.** A written 3-test rule turns
  "I kept these seven" into a decision someone else can check and overturn.
- **Tie the minimal set to a decision.** "Minimal" is meaningless without "for
  whom, to do what."
- **Distinguish a bad result from a broken instrument.** The all-zero eval was a
  broken scale, not a failing skill; reporting it as such (rather than "the
  description scores 0%") prevented a wrong "fix."
- **Generalize, then test the generalization on something unlike the original.**
  The essay-vs-forecast contrast is what proved the skill adapts rather than
  pattern-matches its birth source.
