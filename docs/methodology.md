# Methodology — DISG Top 200 AI companies

Extracted verbatim from the *Methodology* sheet of `downloads/DISG_Top200_AI_Companies_v1.xlsx`.

---

**Row 1** — Methodology — how this list is built

**Row 2** — Read this sheet before quoting any rank. Every judgement call is stated here.

**Row 3** — Last refreshed: 2 Nov 2026, 22:35 SGT   |   Data cut-off: 2026-11-02   |   FX per US$: CNY 7.15, KRW 1400, JPY 150, HKD 7.8, AUD 0.7, EUR 0.86, INR 88

**Row 4** — 1. Universe

**Row 5** — In scope: companies whose core product is AI software, worldwide, private or listed — frontier/foundation-model labs; AI applications and agents; AI infrastructure software (tooling, evaluation, training data); AI for science; embodied-AI software (robot brains, not robot makers).

**Row 6** — Screened on four axes: (a) every in-scope company valued at US$1B or more; (b) every in-scope company with reported revenue or ARR at any valuation; (c) all 40 DISG Top 40 accounts; (d) a sample of private sub-US$1B companies with no revenue, marked indicative.

**Row 7** — Pool at this refresh: 420 scored companies. 288 screened out and logged. 29 hardware-led firms carried unscored.

**Row 8** — 2. Exclusions

**Row 9** — R1 chips and hardware (chip designers, photonics, robot makers, devices, drones, defence hardware, brain implants). R2 data centres, neoclouds, inference clouds and compute providers. R3 autonomous-vehicle firms. R4 established software firms that added AI to an existing product. R5 acquired companies and majority-owned subsidiaries (counted within the parent). R6 companies with reported revenue but no published valuation — cannot be scored, logged. R7 out of scope entirely.

**Row 10** — Kept despite the rules, as instructed: tech giants (Alphabet, Microsoft, Amazon, Meta, Tencent, ByteDance, Alibaba, Baidu, Naver); SpaceX (which now carries SpaceXAI and Cursor); and the DISG enterprise-platform accounts (Databricks, ServiceNow, Snowflake, Datadog, Workato, AvePoint).

**Row 11** — Hardware-led exceptions (Nvidia, Apple, AMD, Samsung, Huawei) are NOT scored. They are appended after each list, ordered by valuation.

**Row 12** — Google DeepMind has no standalone figures and is shown directly below Alphabet, unscored. Microsoft Research Asia is shown directly below Microsoft on the same convention.

**Row 13** — 3. Data rules

**Row 14** — Valuation (US$B): listed = market cap on a stated date; private = post-money of the latest confirmed round. Flagged 'Reported' when the number is talks only, 'stale' when the round is older than ~18 months.

**Row 15** — Revenue (US$M): listed companies, tech giants and enterprise platforms = trailing-12-month whole-company revenue; private = latest ARR / run-rate / annual revenue reported by the company or credible press, with a date. No third-party estimates (Sacra, Latka, multiples.vc and similar are never used). Quarterly-only revenue is annualised at quarter × 4 and flagged. Gross revenue that includes contractor pay is flagged.

**Row 16** — No published revenue = revenue score 0. Nothing is imputed.

**Row 17** — Revenue verification grade — A: company statement (release, filing, CEO/founder on record). B: credible press citing the company or named sources. C: tracker or insider post pointing to an A/B source. Grade D is never used. Figures older than about two years are not used.

**Row 18** — Automatic checks flag but never change a figure: valuation > 150× or < 2× revenue; figure older than 12 months (re-search if > 18); revenue changed more than 2× since the previous refresh (re-verify); private figures within 30% of the revenue-test bar need a grade-A source or two independent sources.

**Row 19** — FX per US$: CNY 7.15, KRW 1,400, JPY 150, HKD 7.8, AUD 0.7, EUR 0.86, INR 88. Any change is recorded in the Revenue audit.

**Row 20** — 4. Scoring

**Row 21** — Fixed log ladders, each 10× step = 25 points, capped 0–100.

**Row 22** — valuation score = (log10(V) − log10(0.1)) / (log10(1000) − log10(0.1)) × 100   [V in US$B]

**Row 23** — revenue score  = (log10(R) − log10(10)) / (log10(100000) − log10(10)) × 100   [R in US$M]

**Row 24** — Composite = 50% valuation + 50% revenue (standard); 40% / 60% (revenue-weighted view). Order by composite; ties broken by valuation, then revenue.

**Row 25** — Worked check: Anthropic V = 965, R = 65,000 gives valuation 99.6, revenue 95.3, composite 97.5.

**Row 26** — 5. Lists

**Row 27** — Objective 100 and Objective 200: top N by composite, no guaranteed places.

**Row 28** — Top 100 and Top 200 (incl. Top 40): all 40 DISG accounts and the tech giants are guaranteed places; the remaining places are filled by composite; the whole list is ordered by composite.

**Row 29** — The first 100 of each 200 list equals the matching 100 list — this is asserted in code and reported.

**Row 30** — Ranked by valuation and Ranked by revenue show the whole pool on one measure.

**Row 31** — Top 40 positions: a company valued at US$1B+ takes its exact rank in the US$1B+ screen. Below US$1B the position is estimated as max(screen rank, companies above + 1, N × (1/V)^a + 1), with central N = 1.3 × N1 and a = 0.9, low N = N1 and a = 0.8, high N = 400 and a = 1.0 (high bound capped at 400). N1 = 154 companies found at US$1B+. V is the valuation in US$B.

**Row 32** — Confidence is 'Lower (indicative)' only for companies valued below US$1B that are unlisted and report no revenue; every other row is 'Standard'.

**Row 33** — 6. 2027 scenario planning

**Row 34** — DISG = champions; Global Ventures (GV) = emerging champions. The AI team does not cover tech giants, so the tech giants (and the five hardware-led firms) are removed from both teams.

**Row 35** — Causal Labs (AI Mission), Google DeepMind and Microsoft Research Asia (big-tech affiliates) and Workato (DISG decision) are kept with DISG by exception and take places inside the 60.

**Row 36** — Five methods: 50/50 composite; 60/40 composite; valuation only; revenue only (no-revenue companies follow by valuation); and a revenue test (published revenue ≥ US$130M, or no published revenue and valuation ≥ US$25B, plus the exceptions). In the ranking methods DISG = exceptions plus the top-ranked companies up to 60.

**Row 37** — The overview shows each company's owner under all five methods, plus the accounts that are DISG under every method and GV under every method.

**Row 38** — The revenue-test bar is chosen from the data rather than assumed: every gap between consecutive reported revenue figures is a candidate and the bar is placed in the void that lands nearest 60, so it never rides the cluster of US$100M milestone reports. The count that falls out is reported, not forced. The US$25B valuation floor for accounts with no published revenue is as specified.

**Row 39** — 7. How this workbook is wired

**Row 40** — Full pool holds the live formulas: the ladder bounds and the two weights are blue input cells, and every valuation score, revenue score, composite and live rank is a formula that reads them.

**Row 41** — Every list sheet pulls valuation, revenue, both scores and the composite back out of Full pool with INDEX/MATCH, so figures stay live. List membership and order are fixed at refresh time; change an input and the scores re-compute, but the ordering is a snapshot of the refresh.

**Row 42** — The workbook is recalculated before delivery and scanned for formula errors; live composites are spot-checked against independently computed values.

**Row 43** — 8. Judgement calls and known limits

**Row 44** — SpaceX is kept as a scored company (it now owns SpaceXAI and Cursor) even though it would normally be excluded as space and defence hardware. It is not a guaranteed place in the Top 100/200 — it competes on composite like any other company.

**Row 45** — xAI and Cursor/Anysphere also appear as separate scored rows because they are named DISG Top 40 accounts with a guaranteed place, even though the brief's exclusion rule would otherwise fold them into SpaceX.

**Row 46** — Placing Google DeepMind directly below Alphabet, and Microsoft Research Asia below Microsoft, consumes a Top 100 slot for each. That is the display convention the brief asks for, not a score.

**Row 47** — The revenue-test bar of US$130M is the stated bar. The bar is deliberately off the 'US$100M milestone' cluster so that a wave of milestone announcements does not push an account over the line.

**Row 48** — Where two credible sources disagree on a figure by more than 25% (valuation) or 2× (revenue), the conflict is recorded in the company's notes rather than silently resolved.

**Row 49** — No figure is imputed. A blank revenue cell means no gradeable published revenue exists — it is never a zero and never an estimate.

