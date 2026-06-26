---
# M4 — Supply Additions & COD-Timing + Bottleneck Rank
*Run of the 8-prompt set (see `extraction-prompts_us-grid-btm.md`) against the SemiAnalysis article "US Grid Constraints: Towards 40GW+ of Behind-The-Meter Datacenter by 2028?". This is generated OUTPUT, not the source.*

## Prompt
> Extract why firm dispatchable supply cannot arrive in time, then rank the constraints.
> 1. Lay out the additions picture: gas <10GW/yr in 2026–27 (rising 2028+), CCGT builds 4–6 yrs, gas-turbine and GSU-transformer lead times 3–4 yrs vs ~18 months historically, and the 40k-generator / advanced-construction / satellite basis for the forecast.
> 2. Decompose the 2026–27 shortfall into its stacked causes: queue→COD conversion (~57GW cleared vs ~24GW of executed projects terminated since 2020, incl. 13.5GW gas), permitting (29% of milestone changes) vs supply-chain (23%), CCGT slowness, plus financing/labor/community.
> 3. Rank every bottleneck by [severity | timing | solvable by money alone? | can hyperscalers bypass via BTM? | does BTM solve it or merely shift it].
>
> Output: an additions/lead-time table; a ranked bottleneck table naming the top-2 constraints on 2027–28 buildout and the leading indicator for each.
>
> Article: [PASTE SOURCE]

## Output

### Core finding (one line)
Firm dispatchable supply cannot arrive in 2026–27 because the **physical clock has already run out**: the plants that would deliver in those years are not in advanced construction today, and the equipment + build durations needed to get there (4–6 yr CCGTs, 3–4 yr turbine/transformer lead times) exceed the window. The shortfall is a **stack** of bottlenecks, not one — and only some are bypassable. Net-new accredited (ELCC) firm capacity runs at just **~15GW/yr, rising toward 20GW+ by end-decade** (article §"Forecasting Power Plants"; intro), against a +21→+84GW datacenter demand ramp.

---

### 1. Additions / lead-time table

| Item | Figure (per source) | Detail / basis |
|---|---|---|
| **Gas nameplate additions, 2026–27** | **< 10 GW/yr** | Nameplate forecast; additions "only pick up in 2028 and beyond." Cause: too few plants in advanced construction stage for a 2026–27 COD. |
| **Net-new ELCC (firm, accredited) additions** | **~15 GW/yr**, rising to **20GW+** by end of decade | "Effectively all the firm capacity a grid operator can recognize" to serve firm load (datacenters, fabs, industrials). This is the binding number, not nameplate. |
| **CCGT planning→COD** | **4–6 years** (in some ISOs) | CCGT = most efficient way to burn gas but the **slowest build of any generation technology**. Bulk of utility gas orders are CCGTs + combustion turbines. |
| **Gas turbine lead time** | **3–4 years** (vs ~18 months historically) | Supply-chain stretch; ~2.5x the historical norm. |
| **Generator step-up (GSU) transformer lead time** | **3–4 years** (vs ~18 months historically) | Same stretch as turbines; both must arrive before a plant can energize. |
| **Total gas-plant development time** | **From ~24-month baseline → ≥ 4 years** even under optimistic assumptions | CCGTs sit at the long end (4–6 yr). The lead-time stretch is what converts a 2-yr baseline into a 4yr+ reality. |
| **Faster alternatives (BTM path)** | Fuel Cells, RICE | "Aggressively secured directly by datacenter operators for onsite generation" — chosen precisely because they sidestep CCGT/turbine timelines. |
| **Grid-interconnection long-lead gear** | MPTs, high-voltage breakers, network upgrades | Drives the utility "2027 → 2029" slip pattern even when generation exists. (article §intro example) |

**Forecast methodology (the 40k-generator / advanced-construction / satellite basis):**
- Tracks **40,000 generation assets** in the US; forecasts **quarter-by-quarter COD for all fuel types**.
- Replicates the Datacenter Model methodology: **extensive construction-timeline analysis**, **hundreds of thousands of empirical datapoints**, backed by **real-time satellite imagery** to see which plants are physically in advanced construction.
- True capacity value of each plant set via a **proprietary ELCC model**, adapted per ISO / major non-ISO region.
- Conclusion drawn from observation, not assumption: *"We simply don't see enough power plants in advanced construction stage that would enable a 2026–27 delivery."*

---

### 2. The 2026–27 shortfall, decomposed into its stacked causes

The source is explicit: *"The 2026–27 shortfall isn't the product of one bottleneck but a stack of them."* Four layers:

| # | Layer | Mechanism & numbers (per source) |
|---|---|---|
| 1 | **Institutional / queue friction (conversion, not queue size)** | Slowness of key stakeholders (utilities) + overcrowded interconnection queues. **In PJM the queue is no longer the binding constraint — conversion is:** ~**57GW** has cleared studies and been offered/executed interconnection agreements, yet **since 2020 ~24GW of fully-executed-agreement projects (incl. 13.5GW gas) terminated before commercial operation** — due to permitting denials, supply-chain delays, and financing that couldn't close. |
| 2 | **Permitting vs supply-chain (the two largest single causes of slippage)** | **Permitting = 29%** of project milestone changes (Jan-2023→Jan-2026); **supply-chain delays = 23%**. (Source cited in text: *Powering Reliability through Market Design*.) Permitting is the single largest discrete cause. |
| 3 | **Technology mix works against speed** | Bulk of utility gas orders = **CCGTs + combustion turbines**; CCGT is the **slowest build of any generation tech (4–6 yr)**. The mix is structurally biased toward the slow end. |
| 4 | **Supply chain stretches every timeline** | Gas-turbine and GSU-transformer lead times each at **3–4 yr vs ~18-mo norm**, pushing total gas-plant development to **≥4 yr** even optimistically (CCGTs at the 4–6yr long end). |
| 5 | **Residual project-specific slippage** | Increased equipment costs, **community pushback**, **labor availability**, **financing concerns** — any of which can independently slip a project. |

**Read-through:** queue clearance overstates deliverable supply by a wide margin — only ~57GW cleared vs 24GW since-2020 attrition on *executed* agreements means even "approved" pipeline leaks heavily. The binding loss happens **after** the queue, at permitting/supply-chain/financing — i.e., late enough that 2027-28 COD cannot be recovered by reform alone.

---

### 3. Ranked bottleneck table

Severity = how much it constrains 2027–28 firm-capacity delivery. Timing = when it bites. "$ alone?" = can capital remove it on the 2027–28 timeline. "BTM bypass?" = can a hyperscaler route around it by going behind-the-meter. "Solve or shift?" = at the *system* (grid) level, does BTM add net firm capacity or merely relocate/compete for the same constraint.

| Rank | Bottleneck | Severity | Timing | Solvable by $ alone (by 2027–28)? | Hyperscaler BTM bypass? | BTM solves or shifts? |
|---|---|---|---|---|---|---|
| **1** | **Long-lead equipment supply chain** (gas turbines + GSU transformers, 3–4 yr; grid-side MPTs/HV breakers) | **Critical** | Now → 2029+ | **No** — slots are physical; money buys queue position, not time | **Partial** — BTM pivots to faster Fuel Cells / RICE + secondary-market turbines, but core CCGT-class gear is the same OEMs (GEV/Siemens) | **Shifts.** BTM competes for the same turbine/transformer pool; adds no net grid firm capacity. Relieves the buyer, not the system. |
| **2** | **CCGT build duration / technology mix** (4–6 yr; slowest tech, dominant in utility orders) | **Critical** | 2027–28 already foreclosed | **No** — construction physics; capital can't compress a 4–6 yr build into the window | **Yes (genuinely)** — BTM chooses RICE/fuel cells/peakers that energize far faster, sidestepping CCGT entirely | **Bypasses at buyer level; shifts at system level** — faster onsite tech is less efficient and serves one load, not the grid. |
| **3** | **Queue→COD conversion failure / interconnection** (24GW since-2020 attrition incl. 13.5GW gas; MPT-driven "2027→2029" utility slips) | **High** | 2026–29 | **Partial** — reform (FERC EIT, ~10-mo expedited track; RM26-4) helps over time, not by 2027 | **Yes** — islanded BTM needs no generator interconnection; removes the utility from the critical path | **Solves for the buyer / shifts for the grid** — load leaves the grid rather than capacity being added to it. |
| **4** | **Permitting** (29% of milestone changes; largest single cause) | **High** | Persistent | **No** — regulatory/political, not purely financial | **Partial** — Texas onsite-gas permitting is "easier" (driver of 5GW+ ERCOT BTM plans), but BTM still needs **air permits** (e.g., Crusoe TCEQ filing) | **Shifts** to a different (often lighter) permitting regime — emissions/air-permit risk, not eliminated. |
| **5** | **Institutional / utility slowness + queue congestion** | Medium-High | Persistent | No — structural | **Yes** — BTM removes the utility from the schedule entirely (the stated #1 BTM advantage: speed + schedule *certainty*) | **Bypasses for the buyer; unsolved for everyone behind the utility.** |
| **6** | **Financing / cost / labor / community** | Medium (project-specific) | Variable | **Mostly yes** — hyperscaler balance sheets can fund and self-underwrite (LCs, deposits, take-or-pay) | **Yes** — buyer-funded BTM internalizes the financing | **Solves the financing leg** (this is the one layer money *does* clear); labor/community partly shift onsite. |

**Top-2 constraints on the 2027–28 buildout (named):**

1. **Long-lead equipment supply chain (gas turbines + GSU transformers, 3–4 yr).** This is the master constraint: it converts a 24-month baseline into 4yr+ and is **not solvable by money** on the 2027–28 timeline. It also caps BTM itself, since onsite gas draws on the same OEM pool — the reason the article highlights Fuel Cells/RICE and a surging **secondary turbine market** as the real release valves.
   - *Note the article's own counter-signal:* it reports turbine constraints "proved far easier than many had feared" and "surging turbine availability." This applies mainly to the **BTM / secondary-market release valve** (and to faster Fuel Cell/RICE classes), not to **grid-scale new-build CCGT OEM slots**, which remain 3–4 yr — so the #1 ranking is specifically a *grid-supply* constraint, partially relieved precisely by routing demand to BTM.
   - **Leading indicator:** OEM turbine + GSU-transformer **lead-time quotes and order backlog** (GEV/Siemens slot availability), and **secondary-market turbine availability** — the article flags "surging turbine availability" as the metric to watch. Compression of quoted new-build lead times back toward the ~18-mo norm = constraint easing; continued 3–4 yr quotes = locked.

2. **CCGT build duration / technology mix (4–6 yr).** The dominant utility gas product is also the slowest; 2027–28 CODs require advanced construction *today*, which the satellite/40k-generator scan does not see.
   - **Leading indicator:** **count of CCGTs reaching advanced-construction stage** with a 2027–28 COD (satellite-tracked), and the **PJM queue→COD conversion ratio** (cleared GW that actually reaches commercial operation vs the ~24GW since-2020 termination baseline). Rising advanced-construction starts and a falling termination rate = supply finally arriving.

**Cross-cutting verdict — does BTM solve or merely shift?** At the **buyer** level BTM genuinely bypasses bottlenecks #2, #3, #5 (CCGT speed, interconnection, utility slowness) and clears #6 (financing). At the **system/grid** level it *shifts* rather than solves #1 and #4 — it competes for the same turbines/transformers and merely relocates permitting to the air-permit/emissions regime, adding **no net accredited firm capacity** to the grid. That distinction is the engine of the whole "BTM > grid" thesis: BTM wins the buyer's clock, not the grid's capacity math.

---

## Caveats

- **Paywall starvation:** The article is paywalled at "Winners and Losers of the rise of Behind-The-Meter." Any equipment-equity translation of these bottlenecks (which OEM/IPP wins from turbine lead times, who is exposed to the secondary-turbine glut, NRG/GEV/Bloom/INNIO positioning) sits in the cut section. **[starved — paywalled section not in source]** — this M4 output ranks the *constraints*, not the *named beneficiaries*.
- **Vendor-model uncertainty:** The load-bearing additions figures — **<10GW gas/yr in 2026–27**, **~15GW/yr ELCC rising to 20GW+**, and the "not enough plants in advanced construction" judgment — are **proprietary SemiAnalysis Energy Model outputs (M-class per M2)**, not independently audited facts. They depend on the 40k-generator COD forecast and satellite reads being accurate; a more aggressive 2028 ramp or hidden advanced-construction pipeline would soften the rank. The lead-time numbers (3–4 yr turbines/transformers; 4–6 yr CCGT) and the permitting/supply-chain split (**29% / 23%**, *Powering Reliability through Market Design*) and the PJM conversion figures (**~57GW cleared, ~24GW terminated incl. 13.5GW gas**) are externally checkable in principle (ISO queue data, OEM disclosures) but are reported here only as the source states them.
- **Ranking is interpretive:** The article asserts the stack and its components but does **not** itself publish a numbered severity ranking or an explicit "solvable-by-money / BTM-bypass / solve-vs-shift" scoring — those columns and the top-2 selection are this extraction's synthesis from the stated mechanics, not a verbatim list. The leading indicators are inferred from metrics the article says its Energy Model tracks (lead times, secondary-market availability, advanced-construction satellite reads, queue conversion).
---
