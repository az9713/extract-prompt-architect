# M6 — ERCOT Structures & Deal Mechanics
*Run of the 8-prompt set (see `extraction-prompts_us-grid-btm.md`) against the SemiAnalysis article "US Grid Constraints: Towards 40GW+ of Behind-The-Meter Datacenter by 2028?". This is generated OUTPUT, not the source.*

## Prompt
> This section is fully available (not paywalled) — mine it hard; it is where concrete, near-term, checkable deal activity sits. 1. Define and disambiguate the structures along two axes: sourcing (NMA = existing generation operating before the Sept-1-2025 SB6 trigger; BYOG = newly built co-located generation) and metering/connection (PUN, WLPUN, PCLR), plus maximum withdrawal limit, export limit, Batch Zero, NPRR1325/PGRR145, PUCT Project 39169, FERC RM26-4, EIT. 2. For each structure: what problem it solves, who uses it, how it changes time-to-energization, what regulatory risk remains (curtailment, PUCT denial/conditioning). 3. Build the announced-deal table from the text: Crusoe/Goodnight (~525.5MW load → ~1GW campus, +TCEQ air permit ~933MW gross gas); AWS/Comanche Peak (1,200MW, 20-yr PPA, Vistra nuclear-adjacent); CyrusOne/Thad Hill (400MW, Calpine); CyrusOne–Constellation/Freestone (760MW potential, 380MW contracted); ~2,885MW total — with structure, counterparty generation, and status. Output: a two-axis taxonomy table and the deal table; end with what ERCOT regulatory fluency is worth as a strategic capability and which structure pulls the most equipment forward.

## Output

### 1. The two-axis frame

ERCOT's co-location landscape resolves into **two orthogonal questions**, and the article is explicit that conflating them is the main source of confusion:

- **Axis A — How does the site *source* its power?** This is a question of generation *vintage*, and it is what triggers (or escapes) Texas SB6 review.
  - **NMA (Net-Metering Arrangement)** = the co-located generator was **already operating before September 1, 2025** (the statutory SB6 trigger). Re-pointing *existing* grid generation to a private load.
  - **BYOG (Bring Your Own Generation)** = the load **builds, co-develops, or contracts *new*** co-located generation. Because the generation is new, it sits *outside* SB6's net-metering review.
- **Axis B — How does the site *interconnect and meter* with the grid?** This is the physical/commercial connection construct.
  - **PUN (Private Use Network)** — the long-established base case.
  - **WLPUN (Withdrawal-Limited Private Use Network)** — new under Batch Zero.
  - **PCLR (Provisional Controllable Load Resource)** — new under Batch Zero.

The two axes are **independent**: sourcing (NMA vs BYOG) describes *category and vintage*; metering (PUN/WLPUN/PCLR) describes *connection and dispatchability*. A site picks one answer on each axis.

#### Governing framework and key terms

| Term | What it is (per the text) |
|---|---|
| **Batch Zero** | ERCOT's batch-style large-load interconnection process that is *codifying* these hybrid structures; introduced the two new constructs (WLPUN, PCLR) alongside the established PUN. |
| **NPRR1325 / PGRR145** | The paired protocol/guide revisions that govern the framework. Approved by the ERCOT board **June 1, 2026**; **effective July 11**. They added the two new co-location constructs alongside PUN. |
| **Maximum withdrawal limit** | The single defining number for every large load: the amount the site may **draw from the grid independent of any on-site generation**. Set via the Batch Study for BYOG sites. |
| **Export limit** | What the on-site units may **push back to the grid**; set via the Generation Interconnection track. |
| **PUCT Project 39169** | The PUCT docket / ERCOT net-metering-arrangement review process that **NMA** sites pass through (paired with a 120-day transmission security assessment). |
| **FERC RM26-4** | DOE-directed FERC **rulemaking on faster interconnection of large loads above 20MW** (federal-level, demand-side reform). |
| **EIT (Expedited Interconnection Track)** | A PJM construct (not ERCOT): ~10-month accelerated *generator* interconnection study, accepted by FERC June 12, 2026, after the 2027/2028 BRA cleared ~6.6GW short. Included here for ontology/disambiguation — it is the PJM analogue of ERCOT's batch reform, **not** an ERCOT structure. |
| **SB6 / Sept-1-2025 trigger** | Texas statute; generators operating *before* this date fall under NMA net-metering review, generation built *after* escapes it (BYOG). |
| **SCED** | Security-Constrained Economic Dispatch — the market mechanism through which WLPUN sites export surplus. |

### 2. Two-axis taxonomy table

**Axis A — Sourcing (vintage → SB6 treatment)**

| Structure | What it is | Problem it solves | Who uses it | Time-to-energization effect | Regulatory risk remaining |
|---|---|---|---|---|---|
| **NMA (Net-Metering Arrangement)** | Existing generator (operating before Sept 1, 2025) co-locates with a new large load; nets load against on-site output behind a single meter; only the residual settles to grid, surplus exported. | Lets a buyer tap *already-built, already-firm* capacity instead of waiting on the interconnection queue or new plant construction. | **The bulk of announced ERCOT co-location activity to date** — Crusoe, AWS, CyrusOne (all four deals below). | Fastest in principle — generation already exists — but gated by ERCOT's net-metering review under **PUCT Project 39169** + a **120-day transmission security assessment**. | PUCT can **approve, deny, or condition**; conditions can require the **load to curtail during grid emergencies** or the **generator to make capacity available when the system is tight**. Central question: does re-pointing existing capacity to a private load "leave the rest of the system whole"? |
| **BYOG (Bring Your Own Generation)** | Load builds / co-develops / contracts **new** co-located generation to secure a near-term energization path. | Avoids waiting on grid upgrades to serve the *full* load request; secures incremental power the grid can't deliver in time. | Buyers planning new on-site generation (the path for GW-scale newbuilds; Crusoe's TCEQ-permitted gas build is the BYOG complement to its NMA load deal). | Staged: site draws up to its **withdrawal limit** (e.g. 100MW) from day one, then **ramps toward full capacity as each generation unit comes online**. | Evaluated on **three parallel tracks**: Batch Study (sets withdrawal limit), Generation Interconnection (sets export limit), Transmission Planning (identifies network upgrades). **Outside SB6 net-metering review** because the generation is new — but subject to system-stability limits on achievable load. |

**Axis B — Metering / connection construct**

| Structure | What it is | Problem it solves | Time-to-energization effect | Regulatory risk remaining |
|---|---|---|---|---|
| **PUN (Private Use Network)** | Entire campus (load + co-located generation) behind a **single point of interconnection**; ERCOT meters only the site's *net* exposure, not each resource. | The base case — keeps internal load/gen netted so only net grid exposure is visible/charged. | Established mechanism; baseline. | Standard interconnection exposure; no special dispatch cap. |
| **WLPUN (Withdrawal-Limited PUN)** | A load bringing its **own new generation** connects more MW than transmission alone could support, in exchange for an **enforced cap on grid withdrawal** (e.g. 1,000MW load that never pulls >100MW from grid; rest from on-site gen, surplus exported via **SCED**). | Lets a site **energize more of its desired load *sooner* within existing transmission limits.** | ERCOT is **explicit this is NOT faster interconnection** — it energizes *more load* sooner, not a quicker study. | Enforced withdrawal cap is binding; relies on on-site generation availability for the load above the cap. |
| **PCLR (Provisional Controllable Load Resource)** | A **dispatchable, flexible load needing no on-site generation**; connects at **full requested size**, but ERCOT can **dispatch it down in real time** during transmission constraints (e.g. 150MW backing to 100MW); cap **relaxes toward a defined exit date** as transmission is built. | Lets a flexible load connect at full size *now* while transmission catches up. | Connects at full size immediately — the **explicit bridge-to-firm path.** | Real-time **curtailment risk**: ERCOT can back the load down during transmission constraints until the exit date. |

### 3. Announced-deal table

Roughly **2,885 MW** of reported ERCOT co-location projects, "with likely more beyond these." All four announced deals sit in the **NMA / existing-generation** bucket.

| Buyer | Site / counterparty plant | Generation owner & type | Reported load | Structure | Detail / status |
|---|---|---|---|---|---|
| **Crusoe** | **Goodnight Campus** | (load co-located at single POI) + Crusoe-filed **TCEQ air permit** for new gas | **525.5 MW** (two agreements from same POI: 265.5 + 260 MW) → expected to serve a **~1 GW IT campus** | **NMA** (load); paired with **BYOG**-style new gas build | TCEQ filing for up to **933 MW gross nameplate gas**, of which SemiAnalysis expects **~665 MW = 19× GE Vernova LM2500 turbines (~35 MW each)**. |
| **AWS** | **Comanche Peak** (Somervell County) | **Vistra** — nuclear (co-located *adjacent* to the nuclear plant) | **1,200 MW** | **NMA** | **20-year PPA**, **ramping to full capacity by 2032**. |
| **CyrusOne** | **Thad Hill Energy Center** (Bosque County) | **Calpine** — gas | **400 MW** (Phase 1: 190 MW + Phase 2: 210 MW) | **NMA** | Two-phase, adjacent to Calpine's Thad Hill plant. |
| **CyrusOne / Constellation** | **Freestone Energy Center** | **Calpine / Constellation** — gas | **760 MW potential** (**380 MW contracted** + exclusive option on a second 380 MW phase) | **NMA** | Contracted on first 380 MW phase; option held on the second. |
| **Total** | | | **~2,885 MW** | | "likely more beyond these." |

*Note: the article labels all four as "net-metering arrangement." Crusoe is the one deal that also shows a clear new-build (BYOG) component via its TCEQ gas permit — i.e. an NMA load deal stacked with newly built on-site generation.*

### 4. Strategic-capability note: what ERCOT regulatory fluency is worth, and which structure pulls equipment forward

**ERCOT regulatory fluency as a strategic capability.** The article frames ERCOT as the place where "concrete, near-term, checkable deal activity sits" precisely *because* Texas permitting of onsite gas is easier and ERCOT/PUCT are "racing to write the rules." That speed-of-rule-making cuts both ways: the framework only became board-approved June 1, 2026 and effective July 11, 2026, so the operators who can read NPRR1325/PGRR145, navigate PUCT Project 39169 review, and structure a deal across the right pair of axes (sourcing × metering) are converting *regulatory navigation* directly into *time-to-power* — which the article values at "tens of billions of dollars of annual revenue per GW" and where "power as a percent of total TCO is mostly insignificant." Fluency lets a developer find the "hidden headroom," choose NMA to tap already-firm capacity, and avoid the curtailment/denial conditions the PUCT can impose. In a market where utilities themselves "struggle to understand their headroom," this is a genuine, defensible edge — not a commodity skill.

**Which structure pulls the most equipment forward.** **BYOG (sourced) connected via WLPUN** is the structure that pulls the most generation equipment forward. The logic:
- **NMA pulls *no new* equipment** — it re-points generators that already exist; it accelerates *deals*, not equipment orders.
- **PCLR needs *no on-site generation* at all** — it pulls forward zero turbines/fuel cells; it is a load-flexibility bridge.
- **BYOG is the only sourcing path that orders new generation**, and **WLPUN is the construct that maximizes how much of it gets built**: it explicitly lets a site connect *far more MW of load than transmission supports* (the 1,000MW-load / 100MW-withdrawal example) by leaning on on-site generation for the remaining ~900MW. That gap between connected load and withdrawal cap is exactly the volume of behind-the-meter generation equipment (turbines, RICE, fuel cells) that must be procured and installed. Crusoe/Goodnight is the live example — ~933MW of new gas (incl. 19× GE Vernova LM2500) stacked behind the load.

So: **NMA wins the near-term *announced-deal* count; BYOG-via-WLPUN is the structure that converts grid scarcity into the largest pull-forward of BTM generation equipment.**

## Caveats

- **Axis labeling vs. real deals.** The text presents NMA/BYOG (sourcing) and PUN/WLPUN/PCLR (metering) as two clean axes, but the four announced deals are all tagged only by sourcing ("net-metering arrangement"). The article does **not** explicitly state which *metering construct* (PUN/WLPUN/PCLR) each deal uses, so the deal-table "Structure" column reflects only what the source states (NMA). Mapping each deal to a Batch Zero metering construct would be inference beyond the text.
- **Crusoe NMA + BYOG overlap.** Crusoe is listed under "net-metering arrangement" yet also files a TCEQ permit for *new* gas — which by definition is BYOG (new generation, outside SB6 review). The source does not reconcile how a single campus is simultaneously NMA (load) and new-build gas; the table notes this as a stacked structure, but the exact regulatory treatment of the combined site is ambiguous.
- **~665 MW / 19× LM2500 figure is a SemiAnalysis estimate** ("we expect"), not a confirmed equipment order; the TCEQ filing is for *up to* 933 MW gross nameplate.
- **EIT and FERC RM26-4 are partly out-of-section.** EIT is a **PJM** construct and RM26-4 is a **federal FERC** rulemaking; both appear in the article's reform discussion, not strictly within the ERCOT co-location mechanics. They are included for ontology/disambiguation but are not ERCOT Batch Zero structures.
- **Status granularity is thin.** The source gives status detail only for some deals (AWS: 20-yr PPA, full ramp by 2032; CyrusOne/Constellation: 380MW contracted + option). For Crusoe and CyrusOne/Thad Hill, contract status beyond MW and phasing is not specified.
- **"~2,885 MW total"** is the article's own rounded sum and it explicitly flags "likely more beyond these" — treat as a floor, not a complete census.
- **Effective dates** (board approval June 1, 2026; effective July 11) imply the framework is brand-new as of the article's June 25, 2026 dateline, so deal-to-construct mappings were still settling at publication.
