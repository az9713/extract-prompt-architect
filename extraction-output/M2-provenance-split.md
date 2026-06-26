---
# M2 — Provenance / Verifiability Split
*Run of the 8-prompt set (see `extraction-prompts_us-grid-btm.md`) against the SemiAnalysis article "US Grid Constraints: Towards 40GW+ of Behind-The-Meter Datacenter by 2028?". This is generated OUTPUT, not the source.*

## Prompt
> This is a paid vendor note whose author sells the Energy, Datacenter, Tokenomics, Accelerator, and Industrials models cited as its own evidence. Separate what is independently checkable from what you must take on trust. Classify every consequential quantitative or dated claim as: (F) externally checkable fact — name the independent verifier (ISO auction result, NERC assessment, FERC docket, ERCOT/PUCT filing, company disclosure); (M) proprietary-model output (e.g. +21→+84GW demand, ~15GW/yr ELCC, '>50% BTM by 2028', 50GW/yr TAM, '<10GW gas/yr'); (D) definitional convention (the headroom identity, the ELCC method); (O) opinion/framing. Then: (1) rank the (M) claims by how much the BTM-dominance thesis collapses if that number is materially wrong; (2) flag any (M)/(O) claim asserted with the confidence of an (F). Output: a table [claim | F/M/D/O | verifier or key assumption | overstated-confidence?]; then two lists — 'facts you can bank' vs 'claims you must trust SemiAnalysis on.'

## Output

### How to read the classes
- **(F)** Externally checkable against a named independent source (ISO/RTO auction result, NERC assessment, FERC docket, ERCOT/PUCT/TCEQ filing, company disclosure). Note: "checkable" ≠ "checked" — this run names verifiers, it does not fetch them.
- **(M)** Proprietary-model output. The only verifier is SemiAnalysis itself (Energy / Datacenter / Tokenomics / Accelerator / Industrials / AI Cloud TCO Models). These are the COI-laden claims: the author sells the very models cited as evidence.
- **(D)** Definitional convention — a method or identity that is true by construction, not an empirical assertion.
- **(O)** Opinion / framing / forward judgement.

Several claims are **hybrids** and are split in the table where the seam matters (e.g. an externally-filed permit whose MW interpretation is a SemiAnalysis estimate).

### Classification table

| # | Claim (location) | F/M/D/O | Verifier or key assumption | Overstated confidence? |
|---|---|---|---|---|
| 1 | DC US gross power demand +21GW (2026) → +84GW (2030) (L21) | **M** | Datacenter Model (bottom-up building-by-building), cross-checked by Accelerator + Tokenomics Models — all in-house | **Yes** — "we continue to see" frames a model forecast as observed fact; externally *corroborated* in direction (hyperscaler capex, third-party forecasters) but not in magnitude |
| 2 | "BTM will power well over half of new US datacenters in 2028+" (L8, L22) | **M** | Energy + Datacenter Models. **This is the thesis conclusion**, not an input | **Yes** — stated in the headline/dek with flat declarative confidence |
| 3 | DC BTM equipment TAM crosses 50GW/year by 2029 (L22) | **M** | Energy + Datacenter Models. Terminal commercial-sizing output | **Yes** — asserted as a forecast result without a stated band |
| 4 | "barely 15GW of net-new ELCC capacity added annually, rising to 20GW+ by end of decade" (L30) | **M** | Energy Model + proprietary ELCC model over 40k generators. **Core supply-constraint input** | **Yes** — "our forecast points to" but the number does the heaviest lifting in the whole note (see ranking) |
| 5 | Available headroom "approaching zero… turns negative by 2027" (L34, L94, L96) | **M** (derived) | Energy Model; = accredited supply − peak demand − required reserves, sub-region by sub-region. Anchored partly to (F) auction/NERC data but the cross-country aggregation is model | **Yes** — "goes red by 2027" presented as a finding; rests on the contested ELCC input |
| 6 | US adds "less than 10GW of gas per year in 2026 and 2027" (L58) | **M** | Energy Model construction-timeline analysis + satellite imagery. **Near-term firm-capacity input** | **Yes** — "our forecast shows" but phrased as near-certain ("we simply don't see enough plants") |
| 7 | Solar and BESS "each adding over 20GW nameplate per year" (L71) | **M** (near-term **F**-checkable) | Energy Model; near-term years checkable vs EIA-860/interconnection data | Mild — directionally consistent with public queues |
| 8 | Renewables'/storage ELCC contribution "minimal," steep declining marginal ELCC (L71, L89, L93) | **M** + **D** | Concept of declining marginal ELCC is **D** (definitional); the *magnitude* of the discount is **M** (Energy Model) | Partial — the mechanism is sound; the size of the discount is model-specific |
| 9 | "requested BTM in-service dates cluster around 2027–28 vs grid timelines slipping toward 2030" (L112) | **M** | Datacenter/Energy Model deal tracking | Mild |
| 10 | Anthropic API margins → "tens of billions of dollars of annual revenue per GW" (L113) | **M** | Tokenomics Model + AI Cloud TCO Model | **Yes** — sweeping magnitude stated as known |
| 11 | Gas-turbine & GSU-transformer lead times now 3–4 yrs vs ~18-month historical norm (L65) | **F** (figure **M**-flavored) | *Existence/direction* checkable via GEV / Siemens Energy / Mitsubishi earnings & backlog disclosures; the precise 3–4yr range is a SemiAnalysis synthesis | Mild |
| 12 | CCGT planning-to-COD 4–6 years; total gas-plant dev ≥4 yrs from ~24-mo baseline (L64–65) | **F** (range **M**-flavored) | EIA / industry construction-duration data; specific range is SemiAnalysis synthesis | No |
| 13 | PJM: ~57GW cleared studies/offered IAs; since 2020 ~24GW with executed IAs terminated pre-COD (incl. 13.5GW gas) (L63) | **F** | PJM interconnection data / "Powering Reliability through Market Design" (cited) | No |
| 14 | Permitting = 29% of project-milestone changes Jan 2023–Jan 2026 vs 23% supply-chain (L63) | **F** | "Powering Reliability through Market Design" (named source) | No |
| 15 | FERC accepted PJM's shift to marginal ELCC accreditation in early 2024 (replacing EFORd/avg ELCC) (L81) | **F** | FERC docket / PJM tariff filing | No |
| 16 | Marginal-ELCC / EFORd / ICAP / UCAP / 4CP-window definitions (L79–84, L101–106, L75) | **D** | Definitional conventions (the ELCC method + ICAP/UCAP identities the prompt names) | No |
| 17 | Headroom identity = accredited supply − peak demand − required reserves (L34, L96, L100) | **D** | The headroom identity the prompt names | No |
| 18 | PJM 2027/28 BRA cleared ~134,478MW UCAP → 14.4% reserve margin vs 20% target → ~6,517MW UCAP deficit (L100) | **F** | PJM Base Residual Auction result (public) | No |
| 19 | PJM 1-in-10 LOLE standard → IRM target ~20% (L102) | **F** / **D** | PJM reliability standard (public); 1-in-10 LOLE is an industry definitional standard | No |
| 20 | NERC 2025 Long-Term Reliability Assessment flags 13 of 23 areas with adequacy shortfalls (L100) | **F** | NERC 2025 LTRA | No |
| 21 | Switch Datacenter closed a multi-billion-$ performance LC facility in 2026 (L38) | **F** | Company / financing disclosure | No |
| 22 | FERC Dec 2025 order directing PJM co-location rules; opened Docket RM26-4 on >20MW large-load interconnection (L127) | **F** | FERC order + Docket RM26-4 | No |
| 23 | June 12 2026 FERC accepted PJM EIT (~10-month accelerated study); 2027/28 BRA ~6.6GW short (L127) | **F** | FERC filing / PJM tariff (the 6.6GW = the 6,517MW of #18) | No |
| 24 | ERCOT NPRR1325 & PGRR145 approved by ERCOT board June 1 2026, effective July 11; Batch Zero, WLPUN/PCLR/PUN constructs (L135, L159–164) | **F** | ERCOT board filings / Batch Study Workshop 8 (May 4 2026) | No |
| 25 | SB6 Sept 1 2025 statutory vintage trigger; PUCT Project 39169; 120-day transmission security assessment (L138) | **F** | Texas SB6 / PUCT Project 39169 | No |
| 26 | ~2,885 MW of reported ERCOT co-location projects; specific deals: Crusoe Goodnight 525.5MW, AWS Comanche Peak 1,200MW (20-yr PPA, full by 2032), CyrusOne Thad Hill 400MW, CyrusOne/Constellation Freestone 760MW (L139–151) | **F** (per-deal) + **M** (aggregate) | Individual deals = company / ERCOT interconnection disclosures; the **~2,885MW total and "likely more"** roll-up is a SemiAnalysis tally | Mild — aggregate is curated, not audited |
| 27 | Crusoe TCEQ air permit ≤933MW gross gas; "~665MW = 19× GE Vernova LM2500 (~35MW each)" (L142) | **F** (permit) + **M** (interpretation) | 933MW = TCEQ air-permit filing; the **665MW / 19-turbine** breakdown is a SemiAnalysis estimate ("we expect") | Mild — estimate flagged as such |
| 28 | Meta Prometheus has no gensets; many Meta self-built AI DCs target ~2 nines and forgo backup gen (L115, L117) | **M** (observation) | Industrials Model (proprietary); partly corroborable via site imagery/disclosures | Mild |
| 29 | Meta Ohio campus designed never to connect to PJM; El Paso & Louisiana built around dedicated utility-scale gas; Cipher Black Pearl / Fluidstack follow similar logic (L122) | **M** / **O** | "We understand" — SemiAnalysis interpretation; partly checkable via permits | Hedged appropriately ("we understand") |
| 30 | ~$1mm/MW genset capex; redundancy gain "on the order of a single nine" (L120) | **F** (cost) + **O** (the nine) | Genset capex is an industry-checkable figure; the "single nine" net-uptime judgement is opinion | Mild |
| 31 | BTM is "now the most attractive option" / "BTM Good" (L8, L109, L118) | **O** | Framing — the central editorial thesis | n/a (explicitly opinion) |
| 32 | Winners/losers ranking — GEV, Bloom, INNIO, NRG; "Bloom the biggest beneficiary" (L166–168) | **O** / **M** | [starved — paywalled section not in source] — only the teaser sentence is pre-paywall | n/a — content withheld |

---

### (1) Ranking the (M) claims by thesis-collapse impact

The BTM-dominance thesis is a three-link chain (L47): **demand is large and rising → grid cannot add firm capacity fast enough → the marginal buyer goes behind-the-meter**. Rank the *inputs* to that chain, not its conclusions.

**Discriminating inputs (the crux — collapse risk is real):**

1. **~15GW/yr net-new ELCC additions (#4).** *Most load-bearing.* This single number, fed through the headroom identity, is what makes spare capacity vanish. If true firm-capacity accreditation were ~30GW+/yr, headroom would **not** go negative and the grid could host the load — the thesis flips. It is also the least externally checkable claim (no public ELCC league table exists), so its weight and its opacity coincide. **Rank 1.**
2. **Headroom negative by 2027 (#5).** Mechanically downstream of #4 plus reserve margins. It is the proximate "grid is full" claim, but it inherits its fragility from #4 — so it ranks just below the input that drives it. **Rank 2.**
3. **<10GW gas/yr in 2026–27 (#6).** Sets up the *near-term* firm-capacity scarcity that forces buyers off-grid now rather than later. Wrong-on-the-high-side would not kill the long-run thesis but would blunt the urgency that makes BTM "the only way." **Rank 3.**
4. **+21→+84GW demand (#1).** Important but the **least** likely to flip the thesis. Demand can be materially wrong and the conclusion survives: even +40GW (half the headline) still swamps ~15GW/yr of firm additions, so the marginal buyer still goes BTM. It is also the most externally corroborated of the four (hyperscaler capex, multiple independent forecasters). High salience, low discriminating power. **Rank 4.**

**Why supply outranks demand:** the supply numbers' plausible error band *crosses the flip threshold* (≈15 vs ≈30GW/yr changes the sign of headroom); demand's plausible error band does not (the deficit persists across a wide demand range). And the supply scarcity is the proprietary, hard-to-check crux, whereas demand has outside corroboration. That asymmetry is the spine of the ranking.

**Terminal outputs (fall automatically if any input above fails — "collapse if wrong" is tautological here):**

5. **">50% BTM by 2028" (#2)** — the thesis *conclusion*. If the inputs hold it holds; it carries no independent evidentiary weight.
6. **50GW/yr BTM TAM by 2029 (#3)** — the *commercial sizing* of the conclusion. Matters most for the (paywalled) winners-and-losers investment case; least central to the dominance claim itself.

### (2) (M)/(O) claims asserted with the confidence of an (F)

- **+21→+84GW demand (#1)** — "we continue to see a record datacenter buildout… going from +21GW to +84GW." Model output narrated as direct observation.
- **">50% BTM by 2028" (#2)** — placed in the title and dek as a flat statement of fact; it is a model conclusion.
- **"<10GW gas per year" + "we simply don't see enough power plants" (#6)** — forecast phrased with near-empirical certainty.
- **"barely 15GW of net-new ELCC… rising to 20GW+" (#4)** — the most consequential and least checkable number, stated without a confidence band.
- **"headroom… turns negative by 2027 / goes red by 2027" (#5)** — derived model result given a hard date and a traffic-light label.
- **"tens of billions of dollars of annual revenue per GW" (#10)** — Tokenomics Model inference stated as established magnitude.
- **"BTM is now the most attractive option" (#31)** — opinion stated as settled conclusion ("This statement might shock some stakeholders, but…").

---

### Facts you can bank (independent verifier exists; named, not re-confirmed in this run)

- PJM 2027/28 Base Residual Auction: ~134,478MW UCAP cleared, 14.4% vs 20% target, ~6,517MW (~6.6GW) deficit — **PJM auction result** (#18, #23).
- NERC 2025 LTRA flags 13 of 23 assessment areas with adequacy shortfalls — **NERC** (#20).
- PJM marginal-ELCC accreditation accepted by FERC early 2024 — **FERC docket** (#15).
- FERC Dec 2025 co-location order + Docket RM26-4 (>20MW loads); June 12 2026 EIT acceptance — **FERC** (#22, #23).
- ERCOT NPRR1325 / PGRR145 (approved June 1 2026, eff. July 11); Batch Zero / WLPUN / PCLR / PUN constructs — **ERCOT filings / Workshop 8** (#24).
- SB6 Sept 1 2025 vintage trigger; PUCT Project 39169; 120-day assessment — **Texas SB6 / PUCT** (#25).
- PJM queue conversion: ~57GW cleared, ~24GW (incl. 13.5GW gas) terminated post-IA since 2020; permitting 29% vs supply-chain 23% of milestone changes — **PJM data / "Powering Reliability through Market Design"** (#13, #14).
- Switch multi-billion-$ LC facility (2026) — **company/financing disclosure** (#21).
- Named co-location deals (AWS–Comanche Peak 1,200MW/20-yr PPA; Crusoe Goodnight 525.5MW; CyrusOne Thad Hill 400MW; CyrusOne/Constellation Freestone 760MW); Crusoe 933MW TCEQ air permit — **company / ERCOT / TCEQ filings** (#26, #27).
- Extended gas-turbine & transformer lead times and multi-year CCGT build durations (*direction*, not the exact range) — **OEM earnings/backlog (GEV, Siemens Energy) + EIA build-time data** (#11, #12).

*Note: most bankable items are supporting/contextual — they establish that the grid is tight and that co-location is happening. None of them, on its own, establishes BTM dominance.*

### Claims you must trust SemiAnalysis on (only verifier = the seller of the model)

- +21→+84GW datacenter demand to 2030 — **Datacenter/Accelerator/Tokenomics Models** (#1).
- ~15GW/yr net-new ELCC, rising to 20GW+ — **Energy Model + proprietary ELCC model** (#4). *The crux.*
- Cross-country headroom going negative by 2027 — **Energy Model** (#5).
- <10GW/yr gas additions in 2026–27 — **Energy Model + satellite analysis** (#6).
- ">50% of new DCs BTM by 2028" — **Energy/Datacenter Models** (#2).
- 50GW/yr BTM-equipment TAM by 2029 — **Energy/Datacenter Models** (#3).
- Magnitude of the renewables/storage ELCC discount — **Energy Model** (#8; the *mechanism* is definitional, the *size* is model).
- BTM in-service dates clustering 2027–28 vs grid 2030 — **deal-tracking models** (#9).
- "Tens of billions of revenue per GW" / Anthropic margins — **Tokenomics + AI Cloud TCO Models** (#10).
- Meta no-genset / 2-nines posture and never-connect campus reads — **Industrials Model + "we understand"** (#28, #29).
- Winners/losers and "Bloom = biggest beneficiary" — **[starved — paywalled section not in source]** (#32).

**The asymmetry that is the answer:** the *bankable* column is overwhelmingly supporting and contextual (auction results, FERC/ERCOT/PUCT dockets, individual deal disclosures), while the **load-bearing thesis — the supply crunch, the demand curve, and the >50%-BTM / 50GW-TAM conclusions — rests almost entirely on proprietary models whose sole verifier is the firm selling them.** The public record corroborates that the grid is *tight*; it is SemiAnalysis's own models, not any independent source, that turn "tight" into "negative headroom by 2027" and into "BTM dominates by 2028."

## Caveats

- **Paywall starvation.** The article is cut at the "Winners and Losers of the rise of Behind-The-Meter" heading (L166). The entire company-level winner/loser analysis (GEV, Bloom, INNIO, NRG, IPPs) is absent — only the one-line teaser and the "Bloom the biggest beneficiary (Dec 2024 call)" claim are pre-paywall. All such company rankings are marked **[starved — paywalled section not in source]**. Note that the two headline model outputs — ">50% BTM by 2028" and "50GW/yr TAM by 2029" — *are* in the pre-paywall text (L8, L22) and so are classified, not starved.
- **Verifiers named, not confirmed.** This run performs the provenance *split* the prompt asks for; it does **not** fetch or audit the external sources. Naming "PJM 2027/28 BRA result" or "FERC Docket RM26-4" identifies where a claim *could* be checked — it does not assert it was checked here. Anyone relying on the "facts you can bank" column should still pull the primary source.
- **Could-not-confirm specifics.** The exact figures behind the (F)-classified industry claims — gas-turbine/transformer lead times (3–4yr), CCGT durations (4–6yr), ~$1mm/MW genset capex — are SemiAnalysis syntheses of industry data; the *direction* is independently checkable (OEM disclosures, EIA), the *precise number* is not, hence the F-with-caveat split.
- **Internal cross-reference.** The "~6,517MW UCAP deficit" (L100) and the "~6.6GW short" of the 2027/28 BRA (L127) are the same quantity stated twice — consistent, and both trace to the public PJM auction.
- **Hybrid claims** were split at the seam (e.g. #26 deal-by-deal F vs aggregate-tally M; #27 TCEQ permit F vs turbine-count estimate M; #8 mechanism D vs magnitude M) rather than forced into a single letter.
---
