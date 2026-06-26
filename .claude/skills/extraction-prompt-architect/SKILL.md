---
name: extraction-prompt-architect
description: >-
  Turn any dense source (article, research note, academic paper, SEC filing,
  earnings-call transcript, long report, spec) into a distilled MINIMAL set of
  MAXIMAL-impact extraction prompts — derived from orthogonal analysis
  dimensions, gap-checked for blind spots, and accompanied by a full rationale
  for every include/exclude decision. Use this whenever the user wants prompts
  to "extract", "analyze", "pull signal from", "mine", or "get the most out of"
  a document; whenever they ask which angles/dimensions to analyze a source
  along; whenever they want a "prompt set", "prompt pack", or to distill many
  prompts into a small high-leverage subset; or when they hand over a meaty
  document and ask how to thoroughly interrogate it. Trigger even if the word
  "prompt" is never said — e.g. "how should I break down this whitepaper",
  "what's the smallest set of questions that gets 80% of the value from this
  report", or "give me angles to analyze this filing from".
---

# Extraction Prompt Architect

## What this skill is for

Given a dense source, produce the **smallest set of prompts that extracts the
largest share of its strategically significant signal** — plus the orthogonal
dimensions the prompts are built from, and a transparent justification for what
made the cut and what didn't.

The output is a **distillation report** (a Markdown file), not the answers. You
are designing the instrument, not running it. Do not execute the prompts unless
the user explicitly asks — designing and running are separate jobs, and mixing
them buries the design rationale under a wall of extracted content.

## Why a fixed template fails

The naive approach ("here are 15 questions to ask any document") produces
generic sludge because it ignores two things that change *everything*: **what
kind of source it is** (a vendor research note has author incentives a peer
-reviewed paper doesn't) and **what the reader will do with the extraction**
(someone deciding whether to trade needs a different set than someone briefing
their boss). Dimensions and the minimal set are both *functions of those two
inputs*. Pin them first, derive everything else.

## The workflow

Six steps. Each produces a labeled section of the final report so the user can
see the reasoning, not just the result.

### Step 0 — Profile the source and bind the decision

Before any prompt-writing, establish:

- **Source type** — vendor/sell-side research, peer-reviewed paper, news,
  regulatory filing, earnings call, technical doc, internal memo, etc. This
  determines which blind spots (Step 3) are mandatory. *Vendor and opinion
  sources always need a provenance prompt; the author profits from you
  believing them.*
- **Author incentive & accessibility** — who wrote it, what do they gain from
  the reader's belief, and is any of it paywalled/truncated (a prompt aimed at
  a missing section just produces guesswork — flag it).
- **The reader's decision** — what will the output be *used for*? Understand /
  trade / operate / build / monitor / brief. The minimal set in Step 4 is tuned
  to this. State it explicitly; if the user didn't say, ask or assume the most
  general ("understand the source deeply") and note the assumption.

Skipping Step 0 is the single most common way this workflow degrades into a
generic question list.

### Step 1 — Derive orthogonal dimensions

Generate the analysis dimensions **from `source-type × decision`**, not a
template. A dimension is a distinct *axis of strategic signal* (e.g. for a power
-market note: capacity accounting, timing mismatch, regulatory design,
supply-chain, competitive advantage…).

Then run an **explicit orthogonality pass** — this is not optional, it is what
keeps the downstream prompt set from being half-redundant:

- Lay the candidate dimensions in a list and check each pair for conceptual
  overlap. Merge any pair that overlaps more than ~30% (e.g. "competitive
  advantage", "winners/losers", and "investment signals" usually collapse to
  one or two axes).
- Drop any dimension that doesn't actually *bind* on this specific source.
- Target ~8–15 genuinely independent axes. More than that and you're slicing
  the same signal twice; fewer and you're probably missing a layer.

### Step 2 — Generate the maximal high-impact prompt set

Write one or more prompts per dimension. Each prompt should be reusable,
high-leverage, and force structure (tables, classifications, ranked lists) so it
extracts rather than summarizes. Tag every prompt with the dimension(s) it
serves and build a small **coverage matrix** (dimension × prompt) so over- and
under-covered axes are visible at a glance.

House style for a prompt: a directive framing paragraph that states the lens and
*why it matters for this source*, then a structured extraction body (numbered
asks / bullets), then a required output artifact (a table or ranked list), then
`Article:` / `[PASTE SOURCE]`.

### Step 3 — Blind-spot / gap pass  (the step a dimension-only workflow lacks)

A dimension-derived set can only surface what the dimensions named. "Maximal" is
not maximal until you check what **no dimension covered**. Test the source
against this standing checklist and add a prompt for every real gap:

- **Provenance / verifiability** — does any prompt force a split between
  externally checkable *facts* and the author's unverifiable *model outputs or
  opinion*? Mandatory for vendor/opinion sources. (This is usually the single
  highest-value addition for sell-side research.)
- **Author incentive & reflexivity** — is there a *cui bono* lens (what does the
  author gain from belief?) and a reflexivity lens (if the thesis becomes
  consensus, does it self-defeat — gluts, backlash, edge competed away)?
- **Definitional / ontology** — is the source's load-bearing vocabulary
  (the 5–10 terms everything else rests on) extracted and defined? Misread the
  vocabulary and every number is misread.
- **Recall safety net** — is there a maximal-recall sweep (e.g. paragraph-by
  -paragraph) to catch concrete detail the thematic prompts silently drop?
- **Base-rate / comparative** — vs history, vs the author's own prior track
  record, vs an independent benchmark. If the source makes *datable* predictions
  and part of their horizon has already elapsed, exploit the current date: grade
  the now-resolved checkpoints against what actually happened. A forecast's own
  scored near-term predictions beat any generic base-rate.

Not every source needs all five. Add only the gaps that genuinely bind, and say
why the others were skipped.

### Step 4 — Distill to the minimal set

Apply an **explicit, auditable criterion**. A prompt earns a minimal-set slot
only if it meets all three tests:

1. **Yield** — extracts a large, decision-relevant share of the signal.
2. **Orthogonality** — that share is *not* substantially recoverable from
   another prompt already in the set.
3. **Load-bearing** — the signal underpins the thesis or one's *trust* in it,
   rather than being role-specific or speculation-prone.

Distillation has **three moves, not one**: *drop* the redundant, *merge*
overlapping prompts into one, and *keep* what's load-bearing. The minimal set is
**decision-relative** — a trader's set ≠ an operator's set ≠ a briefer's set;
tune it to the decision from Step 0.

Emit a **run-order**, because sequence matters. The default spine:

> orient (master extraction) → trust-gate (provenance, if present) → rebuild the
> core model → rank the constraints → read the concrete near-term evidence →
> adversarial check → synthesize.

A good minimal set is usually **5–8 prompts** for a single dense source. If it's
larger, suspect you've failed test 2 somewhere.

### Step 5 — Explain everything (exclusion ledger)

The rationale is a first-class deliverable, not a footnote. Include:

- Per-step decisions (why these dimensions, why these blind-spot adds).
- The coverage matrix.
- An **exclusion ledger**: every prompt left out of the minimal set, the *exact*
  signal forgone, whether it's recoverable from a set member, and which 80/20
  test it failed.
- **First adds beyond minimal**, in priority order — what to add first if the
  reader's decision shifts (e.g. "add the investment-hypothesis prompt once the
  paywalled winners section is obtained").

## Output format

Write a single Markdown report. Use this skeleton:

```markdown
# Prompt Distillation Report — <source short name>
**Source / type / author-incentive / accessibility:**
**Reader decision this set serves:**
**Status:** Distillation only. No prompt has been run.

## 1. The inclusion criterion        (the 3 tests, stated so decisions are auditable)
## 2. Dimensions                     (the orthogonal axes + the merge/drop log)
## 3. The minimal set — N prompts     (table: # | run-order | prompt | why it clears 80/20)
## 4. New / blind-spot prompts        (full text of any prompt added in Step 3, each with an include/exclude verdict)
## 5. Exclusion ledger                (every omitted prompt → signal lost → recoverable? → which test it failed)
## 6. Bottom line                     (the set in run-order; first-adds beyond minimal)
```

Full prompt text belongs in the report (so it's copy-pasteable). Keep the
framing prose dense — the reader asked for an instrument plus its design notes,
not an essay.

## Scope discipline

- **Design, don't run.** Producing the report is the job. Offer to run the set
  as a separate follow-up.
- **Be honest about gaps.** If part of the source is missing/paywalled, say
  which prompts are starved by it rather than pretending coverage.
- **Right-size.** A short or simple source may only warrant 3–4 prompts and two
  dimensions; don't manufacture fifteen. The minimal set scales with the
  source's actual signal density.

## Upgrade path (mention, don't build unless asked)

If the user later wants the minimal set *executed* rather than just designed,
that's a fan-out job: one subagent per prompt in run-order, results merged into
a synthesis — a Workflow/plugin, not this skill. This skill stops at the
instrument.
