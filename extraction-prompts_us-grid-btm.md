# Prompt Distillation Report — Skill-Designed Set for the SemiAnalysis Article (fresh, 8 prompts)

> **What this is:** the **`extraction-prompt-architect` skill applied to the source article** — an 8-prompt set designed fresh from the document. This is the "use this" artifact.
> **Sibling doc:** for the earlier exercise of **grading the 15 pre-existing prompts and distilling them 15 → 7**, see [`prompt-distillation-report.md`](prompt-distillation-report.md).

**Source / type / author-incentive / accessibility:**
- **Source:** SemiAnalysis research note, *US Grid Constraints: Towards 40GW+ of Behind-The-Meter Datacenter by 2028?* (mid-2026).
- **Type:** Paid **vendor / sell-side** research. The note's core outputs (+21→+84GW demand, ~15GW/yr ELCC, ">50% BTM by 2028", 50GW/yr TAM) are **proprietary-model outputs**, and the note explicitly sells those models (Energy, Datacenter, Tokenomics, Accelerator, Industrials) and Core Research as evidence. The author **profits from the reader believing the thesis** → provenance and cui-bono are mandatory, not optional.
- **Accessibility:** **Split.** The note is **paywalled at "Winners and Losers of the rise of Behind-The-Meter"** — the named equity calls (GEV, Bloom, INNIO, NRG, etc.) are NOT in the saved copy → any investment-naming prompt **starves**. BUT the **full ERCOT co-location section is present and un-paywalled** (NMA/BYOG/PUN/WLPUN/PCLR + the ~2,885 MW deal table) → the deal-mechanics prompt is **well-fed**.

**Reader decision this set serves:** *Evaluate the BTM-dominance thesis well enough to take an investment / positioning view.* (Assumed — not specified. A **build/operate** decision, e.g. a developer choosing how to power a 5GW campus, would demote M2/M7 and promote a procurement/strategy prompt; a **brief** decision would collapse to M1+M8.)

**Status:** Distillation only. No prompt has been run.

---

## 1. The inclusion criterion

A prompt earns a minimal-set slot only if it passes all three:

1. **Yield** — extracts a large, *positioning-relevant* share of signal.
2. **Orthogonality** — not substantially recoverable from another prompt already in the set.
3. **Load-bearing** — underpins the thesis *or one's trust in it*, not role-specific to a non-positioner or pure speculation.

For a paid vendor note consumed for a positioning call, test 3 forces a **trust gate** (M2) and a **disconfirmation pass** (M7) into the set alongside the content prompts — without them you are pricing model outputs as facts.

---

## 2. Dimensions

Derived from **source-type (sell-side power/AI note) × decision (evaluate-to-position)**, then put through an orthogonality pass.

### 2a. Orthogonality / merge log

| Candidate axis | Verdict |
|---|---|
| Datacenter demand model (+21→+84GW) | **Fold → M1/M3** — it is an *input* to headroom and almost entirely a model output; its epistemic status is handled by M2, its "too high?" risk by M7. Not a standalone minimal prompt. |
| Capacity accounting / ELCC / headroom | **Keep → M3** (the load-bearing engine). |
| Supply additions & COD timing | **Keep → M4.** |
| Bottleneck stack | **Merge → M4** — a *ranking* cross-cut over supply/equipment/permitting, not an independent axis. |
| BTM buyer economics (speed/uptime/redundancy) | **Keep → M5** (the thesis pivot). |
| ERCOT hybrid structures & regulatory design | **Keep → M6** (un-paywalled, concrete, near-term). |
| Equipment & supply chain | **Drop from minimal → first-add** — lead-time/double-order granularity is equipment-equity-specific; partly in M4. |
| Winners/losers & investment naming | **Drop from minimal → first-add** — **paywall-starved**; partly recoverable via M6 (deals name developers) + M7. |
| Thesis fragility & alternatives (load-flex, transmission, reform) | **Keep → M7.** |
| Author incentive / model provenance | **Blind-spots** (Step 3), not content dimensions → M2 + folded into M7. |

**Result: 6 content dimensions** (demand folded) → M3 capacity, M4 supply+bottleneck, M5 buyer-economics, M6 ERCOT, M7 fragility, plus the M1 orient cross-cut. Capacity-accounting and ERCOT **ontology** are folded into M3 and M6 respectively rather than given a standalone prompt.

### 2b. Coverage matrix (dimension × minimal prompt)

| Axis | M1 | M2 | M3 | M4 | M5 | M6 | M7 | M8 |
|---|----|----|----|----|----|----|----|----|
| Demand model | ●● | ● | ● | | | | ● | ○ |
| Capacity / ELCC / headroom | ● | ○ | ●● | ● | | | ● | ○ |
| Supply & COD timing + bottlenecks | ● | | ○ | ●● | ○ | | ● | ○ |
| BTM buyer economics | ● | | | | ●● | ○ | ●● | ○ |
| ERCOT structures & deals | ● | ○ | | | ○ | ●● | | ○ |
| Thesis fragility / alternatives | ○ | | ○ | ● | ● | | ●● | ● |
| *Provenance (B1)* | | ●● | ○ | | | | ● | ○ |
| *Cui-bono/reflexivity (B2)* | | ○ | | | | | ●● | ○ |
| *Ontology (B3)* | ○ | | ●● | | | ●● | | |
| *Track-record (B5)* | | ○ | | | | | ●● | ○ |

●● primary · ● secondary · ○ touched. Equipment-supply-chain and investment-naming axes are intentionally absent (first-adds; the latter paywall-starved).

---

## 3. The minimal set — 8 prompts

Run-order spine (tuned to evaluate-to-position): **orient → trust-gate → rebuild the headroom engine → why supply can't arrive (rank it) → the BTM pivot → the concrete ERCOT deal layer → adversarial + discount the messenger → synthesize the call.** Eight is top-of-band, justified: a vendor note read for positioning needs both a trust cluster (M2) and a disconfirmation/track-record pass (M7) on top of the content spine.

| # | Run-order | Prompt | Serves | Why it clears 80/20 |
|---|-----------|--------|--------|---------------------|
| M1 | 1 orient | Master claim/number/causal-chain extraction | all | Highest-yield single pass; renders the thesis so every later prompt has a target. |
| M2 | 2 trust-gate | Provenance / verifiability split | B1 | Mandatory on a paid note; reclassifies every figure as fact vs model-output. Not recoverable elsewhere. |
| M3 | 3 rebuild | Grid-math / ELCC / headroom (+capacity ontology) | D-capacity, B3 | The load-bearing engine; without it the thesis is a slogan. |
| M4 | 4 supply | Supply & COD-timing + bottleneck rank | D-supply | Why firm capacity can't arrive in time; ranks the constraint stack. |
| M5 | 5 pivot | BTM-vs-grid buyer economics | D-buyer | The thesis pivot — if "BTM wins" is wrong, the whole call is wrong. |
| M6 | 6 evidence | ERCOT structures & deal mechanics (+ERCOT ontology) | D-ERCOT, B3 | The concrete, **un-paywalled**, near-term checkable layer; where deal activity is. |
| M7 | 7 adversarial | Fragility + cui-bono + prior-call track record | D-fragility, B2, B5 | Don't swallow a vendor thesis; grade its own resolved calls; discount for incentive. |
| M8 | 8 synthesize | Positioning verdict | all | The decision: likelihood × trust, cruxes, leading indicators, paywall-flagged positioning. |

### Full prompt text

---
**M1 — Master orient**
> You are an AI-infrastructure and US-power-markets analyst. Decompose this research note into its strategic skeleton before any judgment. Output: (1) the core thesis in one paragraph; (2) the 8–10 most important strategic claims, ranked, each as a row [claim | in-text evidence | author inference | unstated assumption | who benefits | who is harmed | what to monitor]; (3) the causal chain from AI model demand → datacenter pipeline → gross power demand → grid headroom → BTM/hybrid adoption → equipment/IPP winners; (4) a register of every number, date, named company, project, regulator, technology, and regulatory construct. Do not summarize narratively — decompose into discrete claims.
>
> Article: [PASTE SOURCE]

---
**M2 — Provenance / verifiability split** *(trust-gate)*
> This is a paid vendor note whose author sells the Energy, Datacenter, Tokenomics, Accelerator, and Industrials models cited as its own evidence. Separate what is independently checkable from what you must take on trust. Classify every consequential quantitative or dated claim as:
> - **(F) externally checkable fact** — name the independent verifier (ISO auction result, NERC assessment, FERC docket, ERCOT/PUCT filing, company disclosure). E.g. PJM 134,478 MW UCAP, 14.4% vs 20%, NERC 13/23, FERC RM26-4, NPRR1325/PGRR145 dates.
> - **(M) proprietary-model output** — e.g. +21→+84GW demand, ~15GW/yr ELCC, ">50% BTM by 2028", 50GW/yr TAM, "<10GW gas/yr".
> - **(D) definitional convention** — the headroom identity, the ELCC method.
> - **(O) opinion / framing.**
>
> Then: (1) rank the (M) claims by how much the BTM-dominance thesis collapses if that number is materially wrong; (2) flag any (M)/(O) claim asserted with the confidence of an (F).
>
> Output: a table [claim | F/M/D/O | verifier or key assumption | overstated-confidence?]; then two lists — **"facts you can bank"** vs **"claims you must trust SemiAnalysis on."**
>
> Article: [PASTE SOURCE]

---
**M3 — Grid-math / ELCC / headroom** *(+ capacity ontology)*
> Reconstruct the capacity-accounting engine the thesis rests on, defining its vocabulary as you go (misreading UCAP vs ICAP vs ELCC flips the whole conclusion).
> 1. Define, in this source's usage: ELCC, marginal ELCC, ICAP, UCAP, reserve margin, IRM, LOLE, accredited capacity, headroom.
> 2. Rebuild the headroom identity (accredited supply − peak demand − required reserve) and show, using the article's PJM example (134,478 MW UCAP cleared, 14.4% reserve margin vs 20% IRM target, ~6.6GW deficit), exactly how headroom goes "red."
> 3. Explain the nameplate→accredited gap: why incremental solar, wind, and duration-limited BESS earn a steep, widening ELCC discount as the risk window they serve saturates (the duck-curve / 4hr-BESS saturation argument).
> 4. For each input variable, mark how uncertain it is and how a wrong assumption moves the "negative by 2027" call.
>
> Output: a glossary table [term | definition-in-source | why it matters]; the headroom equation with the PJM numbers plugged in; and a sensitivity note naming the variable that, if wrong, flips the conclusion.
>
> Article: [PASTE SOURCE]

---
**M4 — Supply additions & COD-timing + bottleneck rank**
> Extract why firm dispatchable supply cannot arrive in time, then rank the constraints.
> 1. Lay out the additions picture: gas <10GW/yr in 2026–27 (rising 2028+), CCGT builds 4–6 yrs, gas-turbine and GSU-transformer lead times 3–4 yrs vs ~18 months historically, and the 40k-generator / advanced-construction / satellite basis for the forecast.
> 2. Decompose the 2026–27 shortfall into its stacked causes: queue→COD conversion (~57GW cleared vs ~24GW of executed projects terminated since 2020, incl. 13.5GW gas), permitting (29% of milestone changes) vs supply-chain (23%), CCGT slowness, plus financing/labor/community.
> 3. Rank every bottleneck by [severity | timing | solvable by money alone? | can hyperscalers bypass via BTM? | does BTM solve it or merely shift it].
>
> Output: an additions/lead-time table; a ranked bottleneck table naming the top-2 constraints on 2027–28 buildout and the leading indicator for each.
>
> Article: [PASTE SOURCE]

---
**M5 — BTM-vs-grid buyer economics** *(the pivot)*
> Stress the load-bearing pivot: that the marginal GW-scale AI buyer now prefers behind-the-meter. If this is wrong, the thesis is wrong.
> 1. Extract the buyer's decision drivers — speed and certainty of energization (BTM in-service ~2027–28 vs grid slipping toward 2030), schedule control, and buyer risk transfer (letters of credit, deposits, take-or-pay, utilities facing no penalty for delay).
> 2. Reconstruct the redundancy/uptime economics: the old five-nines playbook (N+1 substation ≈ 3–4 nines + >100% backup to reach 5) vs relaxed two-nines / no-genset designs (Meta examples), and why lower uptime tolerance is what makes onsite generation economically viable.
> 3. State the conditions under which BTM does NOT win (short bridge-to-grid, strict inference SLAs, fuel supply / air-permit / emissions limits, genset economics).
>
> Output: a driver table [driver | grid | BTM | who it favors]; and an explicit list of the assumptions the "BTM wins" claim requires to hold.
>
> Article: [PASTE SOURCE]

---
**M6 — ERCOT structures & deal mechanics** *(+ ERCOT ontology; the concrete layer)*
> This section is fully available (not paywalled) — mine it hard; it is where concrete, near-term, checkable deal activity sits.
> 1. Define and disambiguate the structures along two axes: **sourcing** (NMA = existing generation operating before the Sept-1-2025 SB6 trigger; BYOG = newly built co-located generation) and **metering/connection** (PUN, WLPUN, PCLR), plus maximum withdrawal limit, export limit, Batch Zero, NPRR1325/PGRR145, PUCT Project 39169, FERC RM26-4, EIT.
> 2. For each structure: what problem it solves, who uses it, how it changes time-to-energization, what regulatory risk remains (curtailment, PUCT denial/conditioning).
> 3. Build the announced-deal table from the text: Crusoe/Goodnight (~525.5MW load → ~1GW campus, +TCEQ air permit ~933MW gross gas); AWS/Comanche Peak (1,200MW, 20-yr PPA, Vistra nuclear-adjacent); CyrusOne/Thad Hill (400MW, Calpine); CyrusOne–Constellation/Freestone (760MW potential, 380MW contracted); ~2,885MW total — with structure, counterparty generation, and status.
>
> Output: a two-axis taxonomy table and the deal table; end with what ERCOT regulatory fluency is worth as a strategic capability and which structure pulls the most equipment forward.
>
> Article: [PASTE SOURCE]

---
**M7 — Adversarial fragility + cui-bono + prior-call track record**
> Attack the thesis as a hostile but competent analyst, and discount for the messenger.
> 1. **Counterarguments** — build the strongest version of each: AI demand forecast too high; efficiency/inference optimization cuts power intensity; load flexibility unlocks more grid headroom than claimed; interconnection/transmission reform accelerates; BTM's own fuel / air-permit / emissions / equipment bottlenecks are underestimated; uptime SLAs re-tighten as inference matures; equipment winners already priced. For each: supporting vs refuting evidence, and how much it damages the BTM-dominance conclusion.
> 2. **Cui bono** — which claims most serve SemiAnalysis's commercial interest (selling the cited models; validating prior calls; "the winners aren't the usual suspects — only our Energy Model can tell you")? Mark incentive-aligned claims to discount.
> 3. **Track record** — grade the note's own now-testable prior calls against ~mid-2026 reality: Bloom (flagged Dec-2024 as biggest beneficiary), the onsite-gas "first to predict" claim, the "peak gas turbine orders" warning. Hit / partial / miss / too-early.
>
> Output: a thesis-fragility map [assumption | importance | fragility | evidence needed | impact if wrong]; an incentive-discount note; and a prior-call scorecard.
>
> Article: [PASTE SOURCE]

---
**M8 — Synthesis: positioning verdict**
> Using the prior outputs, render a positioning-grade synthesis. Provide: a one-sentence thesis; the single most decision-relevant number and the single most load-bearing mechanism; an explicit separation of **"how likely is BTM-dominance to be right"** from **"how much do I trust this author"**; the 2–3 cruxes that most move the call and the leading indicator that would update each over the next 2–4 quarters; and a positioning read across direct beneficiaries / second-order / crowded / losers — **flagging which calls are blocked by the paywalled Winners-and-Losers section.** Terse, high-density; separate fact from inference.

---

## 4. New / blind-spot prompts (Step 3)

| Blind spot | Fires? | Disposition |
|---|---|---|
| **B1 Provenance / verifiability** | **YES — mandatory** (paid vendor note selling its own models as evidence) | **Included → M2** (trust-gate). The single highest-value add here. |
| **B2 Author-incentive & reflexivity** | YES | **Cui-bono kernel folded → M7.** Standalone **reflexivity** (does BTM-consensus self-defeat: turbine glut, ERCOT backlash, edge competed away) **excluded → first-add** — it refines *timing/crowdedness*, second-order to "is the thesis true." |
| **B3 Definitional / ontology** | YES — two dense vocabularies (capacity accounting; ERCOT constructs) | **Folded → M3 (capacity terms) and M6 (ERCOT terms)** at near-zero marginal cost; no standalone prompt. |
| **B4 Recall safety net** | YES | **Excluded → #1 first-add.** Long note with many specific MW figures; a section-by-section sweep becomes essential the moment the paywalled section is obtained. Full text below. |
| **B5 Base-rate / track record** | YES — note advertises its own prior calls; some are now resolved | **Folded → M7** (prior-call scorecard). A deeper standalone vs external forecasts is a first-add. |

**B4 full text (held as first-add):**
> Sweep the note section by section. For each, list every concrete claim a thematic summary would drop: specific MW/GW figures, dates, named entities, lead times, conditional ("if X then Y") statements, and any number attached to a deal or a model output. Output a running table [location | concrete claim | type: number/date/entity/conditional | F/M epistemic class | thesis-relevant? Y/N]. Do not summarize — capture. Run this especially over the Winners-and-Losers section once it is available.

---

## 5. Exclusion ledger

| Excluded / folded | Signal forgone | Recoverable from set? | Test failed / disposition |
|---|---|---|---|
| **Standalone demand-model audit (D1)** | A dedicated "how is +84GW built / is it credible" pass | Partly — M1 registers it, M2 classes it as model-output, M7 attacks "too high" | Orthogonality — its epistemic + adversarial value is split across M1/M2/M7 |
| **Equipment & supply-chain prompt (D6)** | Lead-time / double-order / manufacturing-capacity granularity for OEM equity timing | Partly — M4 covers lead times | Load-bearing/role-specific — equipment-equity-specific, not thesis-critical; **first-add** |
| **Investment / winners-losers prompt (D7)** | The structured equity hypothesis book (IPPs, OEMs, developers) | Partly — M6 names developers; M7 frames crowding | **Paywall-starved** (named winners are in the cut section) — running it now yields guesswork; **first-add once the section is obtained** |
| **Standalone reflexivity (B2)** | Explicit self-defeating dynamics (turbine glut, ERCOT backlash) + crowding tell | Cui-bono kernel in M7 | Load-bearing — second-order (timing) vs the is-it-true core; **first-add** |
| **Standalone ontology (B3)** | One dedicated glossary pass | Yes — folded into M3 + M6 | Orthogonality |
| **Recall sweep (B4)** | Concrete figures/deals the thematic prompts drop | Partly — M3/M6 catch the load-bearing ones | Orthogonality at the margin; **#1 first-add** |
| **Second/third-order consequences** | Ratepayer politics, emissions, fab siting, gas demand ripples | No | Yield — high sludge risk, low positioning signal for *this* decision |

---

## 6. Bottom line

**Minimal set, in run-order (evaluate-to-position):**
1. **M1** Master orient → 2. **M2** Provenance trust-gate → 3. **M3** Grid-math/ELCC/headroom → 4. **M4** Supply & COD-timing + bottleneck rank → 5. **M5** BTM-vs-grid buyer economics → 6. **M6** ERCOT structures & deal mechanics → 7. **M7** Adversarial + cui-bono + track-record → 8. **M8** Positioning verdict.

The set is weighted so that **M2 + M7** (trust + disconfirmation) flank the content spine — correct for a paid directional note read for a positioning call.

**First-adds beyond minimal, in priority order:**
1. **B4 Recall sweep** — the moment you obtain the paywalled section, or want every MW figure pinned.
2. **D7 Investment / winners-losers** — once the Winners-and-Losers section is in hand (it is the whole point for a positioner, but starved now).
3. **B2 Reflexivity / crowding** — if entry *timing* and crowdedness matter to the position.
4. **D6 Equipment supply-chain** — if taking equipment-OEM equity exposure specifically.

**Designer's caveat:** the paywall starves the investment-naming layer (D7), so M8's positioning read is partial by construction; the un-paywalled ERCOT section makes M6 the richest, most checkable prompt in the set. If your decision is actually **operate** (power a campus) not **position**, swap M2/M7 down and add a procurement/strategy-playbook prompt — say the word and I'll re-tune.
