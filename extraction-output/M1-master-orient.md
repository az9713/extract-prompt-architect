---
# M1 — Master Orient
*Run of the 8-prompt set (see `extraction-prompts_us-grid-btm.md`) against the SemiAnalysis article "US Grid Constraints: Towards 40GW+ of Behind-The-Meter Datacenter by 2028?". This is generated OUTPUT, not the source.*

## Prompt
> You are an AI-infrastructure and US-power-markets analyst. Decompose this research note into its strategic skeleton before any judgment. Output: (1) the core thesis in one paragraph; (2) the 8–10 most important strategic claims, ranked, each as a row [claim | in-text evidence | author inference | unstated assumption | who benefits | who is harmed | what to monitor]; (3) the causal chain from AI model demand → datacenter pipeline → gross power demand → grid headroom → BTM/hybrid adoption → equipment/IPP winners; (4) a register of every number, date, named company, project, regulator, technology, and regulatory construct. Do not summarize narratively — decompose into discrete claims.

## Output

### (1) Core Thesis

The US electric grid cannot add firm, accredited capacity fast enough to serve the accelerating power demand of AI datacenters: SemiAnalysis models only ~15GW of net-new ELCC (effective, grid-credited) capacity added annually rising toward 20GW+ by decade-end, against a datacenter buildout climbing from +21GW (2026) to +84GW (2030). Because renewables and storage contribute little on an ELCC basis, and because gas additions are throttled by interconnection-queue friction, slow-build CCGTs, and 3–4 year equipment lead times, grid headroom (accredited supply minus peak demand minus required reserves) approaches zero and turns negative ("red") by 2027 across a growing set of subregions. That structural supply constraint pushes the marginal GW-scale buyer — driven fundamentally by AI labs like OpenAI and Anthropic, for whom power is a tiny share of TCO but worth billions in revenue — Behind-The-Meter (BTM), because onsite generation offers speed and schedule certainty (in-service 2027–28) that utility interconnections (slipping toward 2030) cannot, especially now that hyperscalers/AI labs accept lower uptime (e.g., Meta's two-nines, no-genset builds). SemiAnalysis forecasts BTM will power over half of new US datacenters in 2028+, with the BTM equipment TAM crossing 50GW/year by 2029, and argues the winners are not the obvious gas-turbine OEMs but a reshuffled set of equipment vendors and IPPs, with hybrid co-location structures (codified by ERCOT's Batch Zero process) forming the practical bridge between BTM and the grid.

### (2) Ranked Strategic Claims

| # | Claim | In-text evidence | Author inference | Unstated assumption | Who benefits | Who is harmed | What to monitor |
|---|-------|------------------|------------------|---------------------|--------------|---------------|-----------------|
| 1 | Grid headroom turns negative ("red") by 2027; power generation is the binding bottleneck on grid-connected DC growth | "available headroom is already approaching zero and turns negative by 2027"; PJM 2027/28 BRA cleared ~134,478MW UCAP = 14.4% reserve margin vs 20% target, ~6,517MW deficit; NERC flags 13 of 23 areas | Headroom-red threshold being crossed across "a growing set of subregions" by 2027 | Required reserve margins stay near current targets; ISO methodologies hold; demand forecast realizes | BTM providers, onsite-gas equipment vendors | Grid-only DC developers, utilities, ratepayers | Subregional reserve-margin filings; NERC LTRA updates; BRA clearing prices |
| 2 | BTM will power >50% of new US datacenters in 2028+; DC BTM equipment TAM crosses 50GW/year by 2029 | "BTM will power well over half of new US datacenters in 2028+"; "TAM for DC BTM equipment to cross 50GW/year by 2029" | Marginal buyer is forced behind the meter as headroom vanishes | Permitting/equipment for onsite gas remains available; demand sustained | BTM equipment OEMs, onsite-gas vendors, hybrid developers | Traditional utility/IPP grid-supply model | BTM in-service dates; onsite air-permit filings; Texas 5GW+ campus announcements |
| 3 | Only ~15GW/yr net-new ELCC capacity is being added (rising toward 20GW+ by end of decade) — far below DC demand | "barely 15GW of net-new ELCC capacity being added annually, with a rising trend towards 20GW+"; DC buildout +21GW (2026)→+84GW (2030) | Accredited (not nameplate) capacity is the true ceiling on hostable load | ELCC methodology fairly captures firm value; 40k-asset model is accurate | Firms selling firm/dispatchable BTM capacity | Loads needing firm grid power (DCs, fabs, industrials) | Quarterly COD tracking; ELCC accreditation changes by ISO |
| 4 | Renewables/storage add little firm capacity on an ELCC basis despite large nameplate | Solar & BESS each add >20GW nameplate/yr but ELCC contribution "minimal"; declining marginal ELCC; ERCOT "de facto no-solar scenario" credits incremental solar ~zero | Nameplate "badly overstates" firm contribution; the nameplate-accredited gap determines hostable load | Correlation/saturation dynamics persist; no breakthrough in long-duration storage | Gas/firm-capacity vendors; ELCC-savvy analysts | Solar/wind/short-duration BESS developers (capacity value) | Marginal ELCC curves; BESS duration mix (2hr/4hr/8hr); 4CP/curtailment timing in ERCOT |
| 5 | BTM beats grid on speed and schedule certainty; utility timelines are unreliable with no symmetric penalties | BTM in-service clusters 2027–28 vs grid slipping toward 2030; utility may revise a 2027 500MW ramp to 2029; "utilities don't even face any penalties" | Schedule control in buyer's hands is decisive for AI labs | Onsite generation can actually be energized on the 2027–28 timeline | AI labs, hyperscalers, BTM developers | Utilities, grid-interconnection-dependent tenants | Realized BTM energization dates vs promises; LC/take-or-pay terms (e.g., Switch facility) |
| 6 | AI labs (OpenAI, Anthropic) are the fundamental demand driver; power is tiny % of TCO but worth billions | "OpenAI, Anthropic now make up the bulk of demand" directly + indirectly via Amazon/Microsoft/Oracle; "power as a % of total TCO is mostly insignificant"; "tens of billions of revenue per GW" | Any power secured by an AI lab is worth billions → willingness to pay/forgo redundancy | Tokenomics margins (e.g., Anthropic API) sustain; AI demand is not a bubble | AI labs, compute-revenue chain, BTM vendors | Skeptics of AI demand durability | Tokenomics Model margins; Anthropic TPU / Oracle-OpenAI RPO signals |
| 7 | Lower uptime tolerance (e.g., Meta two-nines, no gensets) removes the historical cost barrier to BTM | Meta self-built DCs "target just two nines... forgo backup generators entirely"; Ohio campus designed never to connect to PJM; Cipher Black Pearl, Fluidstack similar | Relaxed redundancy rebalances grid-vs-BTM economics in BTM's favor | Tenants/SLAs continue to accept lower redundancy; genset capex (~$1mm/MW) not justified | BTM developers (lower capex), AI labs | Genset/backup-power vendors; redundancy-premium model | SLA/uptime spec trends; genset inclusion in BTM-to-FTM bridge deals |
| 8 | Hybrid co-location structures (ERCOT Batch Zero) are the practical bridge; early winners forming there | NPRR1325/PGRR145 approved June 1 2026, effective July 11; new constructs WLPUN, PCLR alongside PUN; NMA vs BYOG sourcing; ~2,885MW announced co-location | Hybrid (grid + onsite) is where deal activity concentrates and winners emerge | ERCOT/PUCT rules stabilize as written; SB6 vintage rules hold | Co-location developers (Crusoe, AWS, CyrusOne, Constellation), ERCOT | Pure-islanded or pure-grid models; slow movers | Batch Zero outcomes; withdrawal-limit awards; NMA approvals (PUCT 39169) |
| 9 | Gas additions are structurally throttled — "No Gas Until 2028"; <10GW/yr gas in 2026–27 | "<10GW of gas per year in 2026 and 2027"; PJM ~24GW executed-IA projects (incl. 13.5GW gas) terminated since 2020; permitting 29% of milestone changes vs 23% supply chain; turbine + GSU lead times 3–4yr vs ~18mo norm; CCGT 4–6yr | Stack of bottlenecks (queue conversion, tech mix, supply chain) not a single cause | Satellite/construction-stage analysis reliably predicts COD | Onsite/fast tech (fuel cells, RICE) vendors; BTM | CCGT/combustion-turbine grid bet; utilities | Gas COD slippage; turbine secondary-market availability; queue conversion rates |
| 10 | The BTM winners are NOT the usual suspects (peak gas-turbine orders risk being temporary) | "key beneficiaries aren't the usual suspects"; flagged "risk of temporary peak gas turbine orders"; "surging turbine availability"; report names GEV, Bloom, INNIO, NRG (detail paywalled) | Grid-equipment demand accelerates while turbine orders peak/IPPs challenged | Secondary-market turbine glut materializes; relative positioning model is right | Grid-equipment OEMs, fuel-cell/RICE (Bloom, INNIO) per teaser | Peak-turbine-order OEMs, challenged IPPs | Turbine order book vs secondary supply; named equity calls (paywalled) |

### (3) Causal Chain

1. **AI model demand** — Inference (revenue) + training (future revenue) from AI labs (OpenAI, Anthropic) make large-scale compute the "lifeblood"; power is insignificant % of TCO but each GW implies tens of billions in revenue → willingness to pay for and forgo redundancy on power.
2. **→ Datacenter pipeline** — Bottom-up, building-by-building + chip-by-chip Accelerator Model, validated by Tokenomics ("bubble" question), yields a record buildout: +21GW (2026) → +84GW (2030). AI labs drive this directly and indirectly (via Amazon, Microsoft, Oracle).
3. **→ Gross power demand** — Datacenter US Gross Power Demand is one of three forecast blocks; it grows far faster than firm supply and must compete with non-DC load growth (industrials, fabs).
4. **→ Grid headroom** — Energy Model tracks 40k generation assets, forecasts quarter-by-quarter COD, applies proprietary ELCC to get "true" capacity value. Only ~15GW/yr net-new ELCC added (→20GW+ later). Renewables/storage add big nameplate (>20GW each) but minimal ELCC (declining marginal ELCC, correlation/saturation). Headroom = accredited supply − peak demand − required reserves → approaches zero, turns red by 2027 (UCAP view tighter than ICAP, turns red first).
5. **→ BTM / hybrid adoption** — With supply structurally constrained and utilities offering unreliable, penalty-free timelines, the marginal buyer goes BTM for speed (in-service 2027–28 vs grid ~2030) and certainty. Lower uptime tolerance (Meta two-nines/no-gensets) removes the cost barrier. Result: >50% of new DCs BTM in 2028+; hybrid co-location (ERCOT Batch Zero: NMA/BYOG sourcing; PUN/WLPUN/PCLR metering) bridges BTM and grid.
6. **→ Equipment / IPP winners** — BTM equipment TAM crosses 50GW/yr by 2029. But winners are "not the usual suspects": peak gas-turbine orders flagged as possibly temporary, IPPs challenged, while grid-equipment demand accelerates and turbine secondary-market availability surges. Named (paywalled): turbine OEMs (GEV), fuel cell/RICE (Bloom, INNIO), IPPs (NRG); Bloom flagged as biggest beneficiary since Dec 2024.

### (4) Register

**Numbers / quantities**
- DC buildout: +21GW (2026), +84GW (2030); ">50% of new DCs BTM in 2028+"; BTM equipment TAM >50GW/yr by 2029; "40GW+ BTM by 2028" (title)
- Net-new ELCC capacity: ~15GW/yr rising to 20GW+ by end of decade
- Gas additions: <10GW/yr in 2026 & 2027
- Solar and BESS: each >20GW nameplate/yr
- PJM queue: ~57GW cleared studies/offered IAs; ~24GW executed-IA projects terminated since 2020 (incl. 13.5GW gas)
- Permitting = 29% of milestone changes (Jan 2023–Jan 2026); supply-chain = 23%
- Lead times: turbines + GSU transformers 3–4yr (vs ~18mo historical norm); gas-plant dev ~24mo baseline → 4yr+; CCGT 4–6yr
- BESS durations: 1hr, 2hr, 4hr, 8hr+
- PJM 2027/28 BRA: ~134,478MW UCAP cleared; 14.4% reserve margin vs 20% target; ~6,517MW UCAP deficit; "~6.6GW short"
- NERC: 13 of 23 assessment areas facing resource-adequacy shortfalls
- ICAP reserve norm: 15–20%; PJM IRM target ~20% (1-in-10 LOLE)
- 4CP: four 15-minute intervals, June–September
- FERC large-load interconnection threshold: >20MW; EIT ~10-month study
- Genset capex: ~$1mm/MW
- Uptime: two/three/four/five nines
- ERCOT co-location announced: ~2,885MW
  - Crusoe Goodnight: 265.5MW + 260MW = 525.5MW; ~1GW IT campus; TCEQ air permit up to 933MW gross gas, ~665MW = 19× GE Vernova LM2500 (~35MW each)
  - AWS Comanche Peak: 1,200MW; 20-year PPA; full capacity by 2032
  - CyrusOne Thad Hill: 190MW (Ph1) + 210MW (Ph2) = 400MW
  - CyrusOne/Constellation Freestone: 760MW potential (380MW contracted + 380MW option)
- WLPUN example: 1,000MW load, ≤100MW grid withdrawal
- PCLR example: 150MW backing down to 100MW
- BYOG example: withdrawal limit 100MW
- Switch: multi-billion-dollar performance LC facility (2026)

**Dates**
- Article: Jun 25, 2026 (paid); © 2026 Dylan Patel
- Onsite Gas deep dive: ~"nearly a year ago"
- FERC marginal ELCC acceptance: early 2024
- SB6 generator vintage trigger: September 1, 2025
- FERC co-location/large-load order: December 2025
- NPRR1325 / PGRR145: approved ERCOT board June 1, 2026; effective July 11
- PJM EIT tariff revisions accepted: June 12, 2026
- ERCOT Batch Study Workshop 8: May 4, 2026
- Bloom first called out: December 2024
- Milestone-change window: Jan 2023–Jan 2026
- NMA transmission security assessment: 120-day

**Named companies / developers**
- Authors/publisher: Jeremie Eliahou Ontiveros, Sebastian Orejas, Ellie Holbrook, Dylan Patel (SemiAnalysis)
- Equipment/OEM: Bloom Energy, Bergen Engines, Wärtsilä, GE Vernova (GEV), Siemens, INNIO
- AI labs / hyperscalers: OpenAI, Anthropic, Amazon (AWS), Microsoft, Oracle, Meta
- IPPs / generators: NRG, Vistra (Comanche Peak), Calpine (Thad Hill, Freestone), Constellation
- DC developers: Switch Datacenter, Crusoe, CyrusOne, Cipher (Black Pearl, AWS-leased), Fluidstack

**Projects / sites**
- Crusoe Goodnight Campus; AWS Comanche Peak; CyrusOne Thad Hill Energy Center; CyrusOne/Constellation Freestone Energy Center; Meta Prometheus, Ohio, El Paso, Louisiana campuses; Cipher Black Pearl

**Regulators / bodies**
- FERC, PUCT, ERCOT, PJM, MISO, NERC, DOE, ISOs/RTOs, TCEQ
- Dockets/projects: FERC Docket RM26-4; PUCT Project 39169

**Technologies**
- CCGT (combined-cycle gas), combustion turbines, RICE (reciprocating engines), fuel cells, gas turbines, GE Vernova LM2500, solar, wind, BESS (1/2/4/8hr), main power transformers (MPTs), generator step-up (GSU) transformers, high-voltage breakers, gensets/backup generators
- Geothermal/nuclear context: Comanche Peak nuclear plant

**Regulatory / market constructs**
- ELCC (Effective Load Carrying Capability), Marginal ELCC, EFORd, UCAP, ICAP, reserve margin, IRM, LOLE (1-in-10), Base Residual Auction (BRA), 4CP, Duck Curve, COD, energy-only market (ERCOT), seasonal resource adequacy (MISO)
- Co-location sourcing: NMA (Net-Metering Arrangement), BYOG (Bring Your Own Generation), PUN (Private Use Network)
- Co-location metering/interconnect: WLPUN (Withdrawal-Limited PUN), PCLR (Provisional Controllable Load Resource), maximum withdrawal limit, Batch Study, Batch Zero, SCED
- Reform: Expedited Interconnection Track (EIT), SB6, NPRR1325, PGRR145, load flexibility, take-or-pay, letters of credit
- SemiAnalysis models: Energy Model, Datacenter Model, Accelerator Model, Tokenomics Model, AI Cloud TCO Model, Industrials Model; report "Grid Power Bad, BTM Good"

## Caveats
- **Paywall starvation.** The source is cut off at the "Winners and Losers of the rise of Behind-The-Meter" section. The article teases turbine manufacturers (GEV), fuel cell/RICE vendors (Bloom, INNIO), and IPPs (NRG), and states Bloom was called the biggest beneficiary in Dec 2024 — but the actual named, ranked equity calls and the winner/loser reasoning are **[starved — paywalled section not in source]**. Claim #10 and the final node of the causal chain are therefore directional only.
- **Single-source, vendor-authored.** Every quantitative claim derives from SemiAnalysis's own proprietary models (Energy, Datacenter, Accelerator, Tokenomics, ELCC). No independent corroboration is present in-source; figures referenced charts ("Source: SemiAnalysis Energy Model") that are not reproducible as text here.
- **Forecast uncertainty.** Headroom-red-by-2027, >50%-BTM-by-2028, and 50GW/yr-TAM-by-2029 are model outputs dependent on assumptions (reserve-margin stability, demand realization, onsite-permit/equipment availability) that the author flags as hard even for utilities to estimate ("hidden headroom").
- **Scope exclusions stated by author.** Load flexibility and transmission buildout are explicitly deferred to future deep dives, so the headroom picture here is partial by design (generation-focused; transmission named as a second bottleneck but not modeled).
- **Author's directional bias.** The note is a continuation of a prior thesis ("Grid Power Bad, BTM Good") and explicitly markets subscriber models; claims of prior successful calls (Anthropic TPU, Oracle/OpenAI RPO, Bloom) are self-reported.
---
