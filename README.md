# DISG Top 200 AI Companies

An objective screen of **frontier AI firms**, ranked on two published numbers only:
**valuation** and **revenue**. No internal judgement about who "counts" as an AI
company enters the score — only the exclusion rules do.

**Live site:** https://bubbagump86.github.io/disg-top200-ai/
**Repository:** https://github.com/bubbagump86/disg-top200-ai
**Data cut-off:** 2 November 2026

This is the successor to [Top 100 Digital AI Companies 2026](https://bubbagump86.github.io/top100-digital-ai-2026/),
which used the same log-ladder scoring but scored AI-attributed ARR against a
Top 100. This edition screens a Top 200 universe, scores on published revenue as
well as valuation, and carries the DISG Top-40 account list through as a
guaranteed-placement cohort.

---

## What is in here

| Path | What it is |
|---|---|
| `index.html` | The interactive dashboard — 7 tabs, hand-rolled SVG charts, no JS framework |
| `data/*.json` | The seven datasets the dashboard reads (`meta`, `companies`, `lists`, `top40`, `scenario`, `audit`, `exclusions`) |
| `downloads/DISG_Top200_AI_Companies_v1.xlsx` | The workbook — 13 sheets, **live formulas**, no pasted values |
| `downloads/DISG_Top200_AI_Dashboard.html` | The dashboard as one self-contained file (all data inlined — open it offline) |
| `downloads/DISG_Top200_AI_Refresh_Report.md` | The refresh report — movers, exclusions, uncertainty, sources |
| `docs/methodology.md` | The Methodology sheet, extracted verbatim from the workbook |
| `docs/refresh-report-2026-11-02.md` | Same report, browsable in the repo |

## The dashboard tabs

1. **Overview** — the headline table, the valuation×revenue scatter, and the shape of the universe
2. **Objective lists** — pure ranking by composite, with no guaranteed places
3. **Top 100 / Top 200** — the delivered lists (all 40 DISG accounts hold a place)
4. **Ranked by valuation / by revenue** — the single-axis views
5. **Top 40 positions** — the estimated slot each DISG account would take, with the range
6. **2027 scenario** — how the DISG / Global Ventures split changes under five selection methods
7. **Methodology & audit** — the full method, the exclusion log, and the per-company revenue audit

## Methodology in 60 seconds

Both axes span five orders of magnitude, so each is log-transformed and rescaled
against **fixed** bounds — fixed so that a data update re-scores the list without
re-basing everyone else's score.

```
val_score = (log10(V) - log10(0.1)) / (log10(1000) - log10(0.1)) * 100     # V in US$ billions
rev_score = (log10(R) - log10(10)) / (log10(100000) - log10(10)) * 100      # R in US$ millions
composite = 100 * (w * val_score + (1 - w) * rev_score)                     # w = 0.5 or 0.4
```

Worked check — Anthropic: V = US$965B → val_score 99.6; R = US$65,000M →
rev_score 95.3; composite (50/50) = **97.5**.

**Nothing is imputed.** No published revenue → revenue score 0. No published
valuation → not scoreable, and the company is excluded under R6 rather than
guessed at.

### Source grades

| Grade | Meaning |
|---|---|
| **A** | Company statement — a filing, press release, or investor announcement |
| **B** | Credible press — Reuters, Bloomberg, FT, TechCrunch, WSJ, The Information |
| **C** | A tracker that itself points to an A or B source |
| **D** | **Never used** — Sacra, Latka, multiples.vc, Tracxn, ai-company-rankings, arr.club and similar revenue-estimate sites |

Every figure in the workbook and dashboard carries its grade, its date, its
measure (ARR / run-rate / gross run-rate / TTM revenue) and a link to its source.
The **Revenue audit** sheet flags every figure that is more than 12 months old,
sits within 30% of the revenue-test bar without grade-A backing, is a gross
run-rate, or has a valuation-to-revenue ratio outside 2×–150×.

### Valuation

- **Listed** — market capitalisation on a stated date, converted at the fixed
  FX table (CNY 7.15, KRW 1400, JPY 150, HKD 7.8, AUD 0.70, EUR 0.86, INR 88).
- **Private** — post-money of the latest round that was actually struck.
- A round still *in talks* is flagged **Reported**; a mark more than 18 months
  old is flagged **Stale**. A talks-stage number is never used when a struck
  round exists — and if no round exists at all, the reported figure is used and
  flagged, so the company does not silently vanish from the screen.

### Exclusion rules

| Rule | What it removes | Count |
|---|---|---|
| R1 | Chips, hardware, robotics, instruments, devices | (carried unscored — see below) |
| R2 | Data centres, neoclouds, inference clouds, compute providers | 1 |
| R4 | Established software firms that added AI to an existing product | 214 |
| R5 | Acquired or majority-owned subsidiaries — counted inside the acquirer | 54 |
| R6 | Revenue but no published valuation | 13 |
| R7 | Out of scope — not an AI software product | 6 |

**288 companies excluded; 29 hardware-led firms carried unscored.** Hardware
firms (Nvidia, Apple, AMD, Samsung, Huawei and 24 more) are appended after each
list by valuation and never compete for a place — they are a supply side, not a
frontier-AI screen.

## Judgement calls worth knowing about

These are the decisions that a reviewer is most likely to want to overturn. Each
is recorded in the workbook's Full pool sheet and the report.

- **AI must be the product, not a bolt-on.** CrowdStrike, MongoDB, Dynatrace,
  Rubrik, Akamai, Vercel and 25 other established firms were excluded under R4
  even where their AI products are real. Six names are kept against that rule
  because the brief keeps them: Databricks, ServiceNow, Snowflake, Datadog,
  Workato and AvePoint.
- **Palantir is excluded** under R4 — AIP is an add-on to a long-established
  platform and Palantir is not on the brief's kept list. It would rank top-10 if
  retained. This is the single most consequential exclusion in the screen.
- **xAI and Cursor/Anysphere are excluded from scoring** under R5 — xAI merged
  into SpaceX on 2 Feb 2026 and SpaceX completed the Cursor purchase on 14 Aug
  2026. Both are DISG Top-40 accounts, so both keep a guaranteed place in the
  Top 100/200, shown unscored directly below SpaceX, because scoring them
  separately would double-count them inside SpaceX's listed market cap.
- **Scale AI is kept.** Meta holds a 49% non-voting stake, not a majority.
- **Manus AI is kept.** Meta's acquisition was blocked by China's NDRC on
  27 Apr 2026 and unwound; the company is independent again with a US$500M+
  round closed on 8 Oct 2026.
- **Isomorphic Labs is excluded** under R5 — Alphabet has held a majority stake
  since the 2021 spin-out.
- **SpaceX is kept** despite being a space and defence hardware company, because
  it now owns SpaceXAI and Cursor. This is a judgement call, flagged as such.
- **The revenue-test bar is data-driven**, not the brief's illustrative US$130M.
  It is placed in a real void in the revenue distribution — currently
  **US$157.4M**, in the empty stretch between US$150.0M and US$165.2M. The
  US$130M bar sits on the cluster of "US$100M milestone" press releases.
- **No prior workbook existed** in this workspace, so the entrants/exits section
  compares against a prior ranking rebuilt from the team's cached tracker
  figures for the 40 DISG accounts. It is a baseline, not a like-for-like diff.

## Numbers at the cut-off

- **420** companies scored · **288** excluded · **29** hardware-led unscored
- **154** companies with a published valuation of US$1B or more
- Top 10 on the 50/50 composite: Microsoft, Microsoft Research Asia, Alphabet,
  Google DeepMind, Amazon, Meta, Anthropic, Tencent, OpenAI, ByteDance
- 40 DISG Top-40 accounts · 9 tech giants · all 40 hold a place in the Top 200

## Rebuilding

The build is a plain Python pipeline — no service dependencies, no secrets:

```
engine.py         # merge → dedupe → classify → score → 8 lists → payload
build_xlsx.py     # 13-sheet workbook with live formulas
recalc.py         # LibreOffice recalculation + XML error scan + composite spot-check
build_dashboard.py # dashboard + data/*.json + self-contained HTML
test_dashboard.py # Playwright test of every tab and switch
build_report.py   # the refresh report
```

`recalc.py` is the gate: it recalculates the workbook through LibreOffice with
forced recalculation, scans the result for error values, and spot-checks the
composite against the engine's own arithmetic. The shipped workbook has
**12,720 formula cells, 0 errors and 0 mismatches**.

## Known limits

- A private valuation is only as good as the last round that company chose to
  disclose. **11 of the Top 200 entries carry no score** — Microsoft Research Asia,
  Google DeepMind, xAI and Cursor/Anysphere (affiliates or acquired, held in place
  unscored), plus seven DISG Top-40 accounts with no published valuation.
- Run-rate revenue is not recognised revenue. Where a company disclosed
  bookings or gross marketplace volume instead, the measure is labelled as
  such in the audit sheet rather than presented as revenue.
- Top-40 slot positions for accounts below US$1B are *estimates* built from a
  decaying function of the companies above them, not measured ranks.
- The cut-off is 2 November 2026. Figures dated after it are excluded.
