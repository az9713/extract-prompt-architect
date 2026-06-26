# Prompt Distillation Report — Grading & Distilling the 15 Prior Prompts (15 → 7)

> **What this is:** an evaluation of the **15 pre-existing prompts** in `gpt5.5_summary.txt`, distilled to a 7-prompt minimal set. This is the analysis step that *motivated building the skill*.
> **Sibling doc:** for a prompt set **designed fresh from the article by the `extraction-prompt-architect` skill**, see [`extraction-prompts_us-grid-btm.md`](extraction-prompts_us-grid-btm.md). (That one supersedes this for *use*; this one is the reasoning that led to it.)

**Source:** SemiAnalysis, *US Grid Constraints: Towards 40GW+ of Behind-The-Meter Datacenter by 2028?* (Jun 25 2026)
**Input pack assessed:** the 15 prompts (§2–§16) + dimensions map (§1) in `gpt5.5_summary.txt`
**Status:** Distillation only. **No prompt has been run.**

---

## 1. The 80/20 inclusion criterion

A prompt earns a slot in the minimal set **only if it satisfies all three tests**:

1. **High yield** — extracts a large, decision-relevant share of the source's strategic signal.
2. **Orthogonality** — that share is *not* substantially recoverable from another prompt already in the set.
3. **Load-bearing** — the signal underpins the thesis itself or one's *trust* in it; it is not role-specific (operator-only) or speculation-prone (sludge).

Token cost is a tiebreak, not a gate. By construction the set is the *smallest* collection that still clears tests 1–3 across the source's load-bearing layers: **claims, the model behind them, the constraint that drives them, the concrete near-term evidence, an adversarial check, the trust-gate on the numbers, and a decision-grade synthesis.**

---

## 2. The minimal set — 7 prompts, in run order

Sequence matters: orient → trust-gate the numbers → rebuild the model → rank the constraint → read the concrete deal layer → attack it → compress. This deliberately defers all equity/name-picking until the physical and epistemic groundwork is laid.

| # | Run | Prompt | Why it clears 80/20 |
|---|-----|--------|---------------------|
| 1 | §2 | **Master extraction** | The backbone. Recalls claims, numbers, entities, causal chain in one pass. Everything else deepens or stress-tests this. |
| 2 | **NEW-A** | **Provenance & Verifiability Split** | Trust-gate. Tags every number as hard-fact vs proprietary-model BEFORE any prompt builds on it. On a paid vendor note this is foundational and orthogonal to all 15. *(full text in §3)* |
| 3 | §4 | **Grid math / ELCC** | The load-bearing model. The entire thesis is `nameplate → ELCC/UCAP → headroom`. Without reconstructing this you have a slogan, not an argument. Highest source-fit + falsifiability-forcing. |
| 4 | §3 | **Bottleneck map** | The article's actual argument structure is a constraint *stack*. Adds the cuts master only gestures at: "solvable by money alone?", "does BTM solve or merely shift it?" |
| 5 | §6 | **ERCOT / co-location** | The most concrete, checkable, near-term layer (actual MW, named deals). Now fully available — the `.mhtml` un-paywalls the deal table the public text hid. |
| 6 | §11 | **Adversarial + fragility map** | Mandatory for a directional vendor thesis. Pre-loaded counterarguments + an Assumption/Fragility/Impact table. **Graft the cui-bono kernel from NEW-B here** (see §3). |
| 7 | §16 | **Final synthesis** | Decision-grade capstone: what changed, why now, why consensus may be wrong, what falsifies, what to do next. |

**This is ~6 of the original prompts' value at <½ the prompts**, because §2 already shallow-covers the investment/second-order/signal-table material that §7–§10 and §13–§15 deepen — and for a *first* extraction those deepenings are diminishing returns.

---

## 3. The two blind-spot prompts

Both were created as instructed. Each is then judged against the §1 criterion. **One is admitted to the minimal set; one is not.**

### NEW-A — Provenance & Verifiability Split  ✅ INCLUDED (slot #2)

> You are a skeptical research-desk fact-checker. Your job is to separate what this article **proves** from what it **asserts as its own proprietary model output**. The author (SemiAnalysis) sells the very models cited as evidence, so treat unsourced numbers as claims, not facts.
>
> Go through every **quantitative, dated, or capacity claim** in the article. Classify each into exactly one class:
> - **HARD FACT** — externally checkable from a named non-author source (ISO auction result, NERC assessment, FERC docket, regulatory filing, company disclosure).
> - **MODEL OUTPUT** — produced by a SemiAnalysis proprietary model (Energy, Datacenter, Tokenomics, Accelerator, Industrials); not independently verifiable.
> - **DEFINITIONAL / METHODOLOGICAL** — an accounting convention or framework (ELCC, UCAP, the headroom equation); true by construction, not an empirical claim.
> - **INFERENCE / OPINION** — author judgment with no attached number or source.
>
> For each claim, record: the value/date, the exact in-text basis, the class, the named source (if any), how to verify it independently (which dataset + which field), and what observation would falsify it.
>
> Then produce a **trust ledger**:
>
> `Claim | Value | Class | Cited source | Independently checkable? (Y/N) | Falsifier`
>
> Finally, isolate the **load-bearing model outputs**: list the conclusions of the article that rest on UNVERIFIABLE proprietary numbers (e.g. +84GW by 2030, ~15GW/yr ELCC, "BTM >50% by 2028", 50GW/yr TAM). Rank them by how completely the thesis collapses if that single number is wrong. End with two lists: **"facts you can bank"** vs **"claims you must trust SemiAnalysis on."**
>
> Article:
> [PASTE ARTICLE]

**Verdict — clears 80/20.** *High yield:* it changes the epistemic status of every figure the other six prompts quote. *Orthogonal:* no existing prompt enforces the model-vs-fact split — §12 lists external datasets but never tags the *in-article* numbers by trust class. *Load-bearing:* on a paid directional note, mistaking a model output for a fact is the single largest analytic error available; this is the gate that prevents it. Cheap (one pass), and correctly placed at slot #2 so it conditions everything downstream.

### NEW-B — Author-Incentive & Reflexivity  ❌ EXCLUDED from minimal set (provided for completeness)

> Analyze the article along two axes the author cannot be neutral about: **their own incentives** and **what happens if everyone believes them**.
>
> **Part 1 — Cui bono (incentive bias).** Identify every SemiAnalysis product the article cites as evidence or advertises (Energy Model, Datacenter Model, Tokenomics, Accelerator, Industrials, Core Research), and every prior call it claims credit for (Bloom Dec-2024, the Onsite Gas deep dive, the "peak gas turbine orders" warning). For each: how does the reader *believing this thesis* benefit the author commercially? In which direction would that incentive bias the claim — toward more scarcity, more BTM, more urgency, more "non-obvious winners only we can identify"? Mark any claim where incentive and conclusion point the same way as **incentive-aligned (discount accordingly).**
>
> **Part 2 — Reflexivity (consensus decay).** Assume the thesis becomes widely believed and acted on. For each core claim, model the self-correcting or self-defeating response:
> - *BTM >50% believed* → turbine/RICE/fuel-cell over-ordering → glut, lead-times normalize → equipment-winner edge decays.
> - *Headroom-negative believed* → emergency reform / demand response / plant life-extension accelerate → headroom partially recovers.
> - *ERCOT advantage believed* → load rushes Texas → political & reliability backlash → rules tighten.
> - *Power-as-moat believed* → capital floods power procurement → the moat is competed away.
>
> For each, give: trigger, lag-to-correction, which beneficiaries lose their edge, and the **leading indicator that consensus has already arrived** (the "crowded-trade tell").
>
> Output two artifacts:
> - **Incentive-bias map:** `Claim | SemiAnalysis product/prior-call served | Bias direction | Discount`
> - **Reflexivity table:** `Claim | Consensus response | Self-defeating? | Lag | Crowded-trade signal`
>
> Article:
> [PASTE ARTICLE]

**Verdict — does NOT clear 80/20; it is the *first add* beyond the set.** Reasons:
- **Test 2 (orthogonality) fails partially.** Its highest-value 20% — the *cui-bono* kernel — grafts onto §11 (Adversarial) at near-zero marginal cost, which is exactly what slot #6 instructs. And §11's counterargument #10 ("winners already priced") plus §14's "consensus/crowded" dashboard signal already capture the most actionable slice of the reflexivity content.
- **Test 3 (load-bearing) fails.** Reflexivity refines **timing and crowdedness** — it tells you *when an edge decays*, not *whether the base thesis is true*. That is genuinely second-order: valuable for trade entry/exit, not for establishing the strategic picture the user asked to extract first.

**What you lose by excluding it:** the *explicit* self-defeating dynamics (turbine glut, ERCOT backlash, moat-competed-away) and a standing "is this now consensus?" tell. You recover the trust-relevant half by grafting cui-bono into §11. Add NEW-B in full the moment the task shifts from *understanding the source* to *timing a position* in it.

---

## 4. Exclusion ledger — what the other prompts would have added

Every prompt left out, and the exact signal forgone. "Recoverable" = substantially reconstructable from a prompt already in the minimal set.

| Excluded | Signal lost | Recoverable? | Why it fails 80/20 here |
|----------|-------------|--------------|--------------------------|
| **§5 AI scaling implications** | Power-as-AI-primitive framing: API margins, model-release cadence, neocloud viability, "what would falsify the power-bottleneck thesis." | Partly — master claim #1 + §11 falsification cover the core. | **Strongest next add.** Distinct lens, but its falsification half duplicates §11 and its thesis half duplicates master. |
| **§7 Supply-chain / equipment** | Lead-time & double-/over-ordering granularity that drives *equipment-equity timing*. | No. | Role-specific (equipment investor). Not load-bearing for the thesis; defers cleanly to a second pass. |
| **§8 Public-equity investment** | Structured hypothesis book (exposure type, consensus-awareness, valuation risk). | No. | **Starved by the paywall** — the named winners (GEV/Bloom/INNIO/NRG) are in the cut section. Running it now yields generic names. Defer until that section is obtained. |
| **§9 Hyperscaler strategy playbook** | Operator decision set (grid vs BTM vs hybrid vs nuclear playbook). | No. | An *application* prompt, not extraction. Only load-bearing if you ARE the buyer/operator. |
| **§10 Second/third-order consequences** | Ripple effects (ratepayer politics, emissions, fab siting, US-China). | No. | **Highest sludge risk** — several listed effects (sovereign AI, US-China) are barely supported by the source. Cheapest to cut; lowest signal density. |
| **§12 Missing-data checklist** | A standing diligence plan: dataset → field → bullish/bearish signal. | Partly — NEW-A + §11 already name the load-bearing unknowns and their falsifiers. | Verification *workflow*, not strategic *signal*. Its trust-critical core is absorbed by NEW-A. |
| **§13 Casual-vs-expert** | Two-column alpha table on the load-bearing concepts (UCAP vs ICAP, hidden headroom, no-penalty delays). | Yes — master's "non-obvious signals" section reproduces most of it. | Largely redundant with master; clever format, little net-new signal. |
| **§14 Monitoring dashboard** | 24-month tracking with bullish/bearish thresholds + early-warning system. | No. | Ongoing-tracking tool. A *first* extraction does not need it; high value only once you hold a view to monitor. |
| **§15 Paragraph-by-paragraph sweep** | Maximal-recall safety net against silently dropped detail. | Partly — only if master was run carelessly. | Token-heavy, low synthesis. Insurance, not signal. Run only if you suspect master missed something. |
| **NEW-B Author-incentive / reflexivity** | Explicit self-defeating dynamics + consensus-arrival tell. | Partly — cui-bono kernel grafts into §11; "already priced" in §11 #10. | Second-order (timing/crowdedness), not thesis-establishing. See §3. |

---

## 5. Bottom line

- **Minimal set = 7 prompts:** §2 → **NEW-A** → §4 → §3 → §6 → §11(+cui-bono graft) → §16.
- It captures the source's **thesis, its underlying model, its driving constraint, its concrete near-term evidence, an adversarial check, a trust-gate on every number, and a decision-grade synthesis** — the load-bearing 80%.
- **NEW-A (Provenance Split) is admitted** because it is foundational and orthogonal; **NEW-B (Incentive/Reflexivity) is held back** because its trust-relevant half folds into §11 and its remainder is timing-second-order.
- The excluded prompts are not low-quality — they are **role-specific (§7/§9), paywall-starved (§8), redundant (§13/§15), ongoing-use (§14), or speculation-prone (§10).** Add them deliberately when the task changes from *understanding the source* to *trading, operating, or monitoring* it.

*No prompts run. Awaiting go-ahead to execute the set against the un-paywalled `.mhtml`.*
