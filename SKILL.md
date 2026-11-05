---
name: Quality-at-a-Discount
description: >-
  Use this whenever the user wants long-term accumulation: screen or analyze
  stocks, ETFs, or real-asset ballast for a quality business that is hard to
  replace and currently on a true sale-off. Auto-detect market (VN, US, UK, DE,
  AU). Every market and ballast needs VN-depth universe tables (not stub
  shorts). Always include a macro pulse (Fed, rates, labor, fiscal/tariffs, AI
  shifts, SBV/VN, relevant geopolitics) for context and pre-sale-off signals. If
  stocks, gold, metals, fertilizer, and oil/gas are all not cheap, park in
  cash-like yield until a sale-off. Empty equity is allowed after full evidence
  — not the goal. Notify on true sale-off or good/very-good zone entry. On
  bonus/split/GDKHQ, rebase all numeric price hooks (zone/(1+ratio)); never
  treat ex-rights reference prints as a buy zone. Load ONLY the files this
  router names.
---
# Quality-at-a-Discount (router)

**Load only what the question needs.** This file is the index. Do not read every sibling. A VN question must not load US/UK/DE/AU. An equity question must not load gold unless the equity screen is empty or they asked for ballast.

Core rule, every market: good business, hard to replace, **true sale-off** (or clear good/very-good zone with MOS), hold to accumulate. Zero equity buys is *allowed* when nothing clears — never invent a ticker to finish. **Do not end the job on empty.** If stocks, gold, metals, fertilizer, and oil/gas are all not cheap, Read `overlays/waiting-room.md` and park purchasing power in the residual cheap asset (cash-like yield) until a name enters the good zone.

**Sale-off NOTIFY (mandatory):** If any equity or ballast name **enters** good / very-good zones or earns sale-off label `true` / `moderately attractive` with thesis intact, the agent **must alert the user** (ticker, zone/label, price, one-line why, what to do: Probe / Accumulate / fund from waiting-room). Do not bury a clear name inside an empty-screen essay. Optional standing routine: on each re-run / maturity review, diff prior Watch list vs live prices and NOTIFY on any new zone entry (or zone exit / thesis break).

**Corporate-action NOTIFY guard (hard):** Bonus shares / stock dividends / splits are **not** cheapness. Before any price-zone NOTIFY or Probe/Accumulate on a name with a pending or just-effective GDKHQ: (1) confirm ex-date, (2) rebase every numeric hook `zone_post = zone_pre / (1+ratio)`, (3) compare live quote only to the **rebased** zone, (4) say explicitly “đây là ĐC kỹ thuật, không phải sale-off” if the print only fell with the reference. Hitting the old nominal number after adjustment (e.g. old ≤65k printing ~65k post 10:1) is a **false zone hit — do not alert as buyable.**

**Freshness gate (hard — applies to every routine, bulletin, alert and chat answer that reads this skill).** State files: `state/ladders.md` (hooks + per-row metadata tables), `state/events.md` (60-day calendar), `state/valuation-log.md` (append-only diff log). Before any BUY / Probe / Accumulate NOTIFY or order suggestion, read the row's metadata. The row is **STALE** and must NOT produce a buy alert if any holds: (a) an event for that ticker in `events.md` has passed with Done?=N (earnings, guidance, any corporate action); (b) today − valued_on > ttl_days; (c) a macro event moved the discount rate since valued_on — Fed/SBV/BoE policy-rate change, or UST10y moved ≥50bp (recompute 10y+150/250bp hooks), or a tariff/regulation change named in the sector file; (d) adj_factor_since_valued ≠ 1 or a CA ex-date has passed and hooks are not shown rebased; (e) status already STALE-* or valued_on unknown. Output instead: "⚠️ chạm vùng cũ nhưng STALE — cần định giá lại, KHÔNG đặt lệnh", then revalue (or queue it). A STALE row may trigger a revaluation, never a buy.

**Pre-order checklist (PRE-ORDER CHECK — mandatory before telling the user to place, keep, or re-price any order; re-run if >3 trading days old).** Fetch fresh this turn and print all 7: (1) live price + adjusted price history from 2 sources (e.g. SSI iboard vs Vietstock/Simplize), flag reference resets; (2) corporate actions last 60d + next 30d (ex-dates, ratios, ESOP/rights) → adj factor, show pre→post hooks; (3) latest reported quarter vs `data_as_of` — if newer, revalue first; (4) recompute hook from `basis` with fresh per-share numbers: old vs new valuation + one-line diff explanation; unexplained diff >5% ⇒ STOP; (5) every thesis-break criterion vs latest quarter: OK/WARN/BREAK; (6) macro delta since valued_on (policy rates, 10y, FX, relevant tariffs/regulation); (7) caps/sizing (sector cap, cash ≥15%, no margin) and open orders needing cancel/re-price around a CA (VN brokers may cancel or keep orders on GDKHQ — confirm). Verdict GO / GO-REDUCED / NO-GO; user's explicit OK still required.

**After any revaluation:** overwrite hooks + metadata (valued_on, data_as_of, basis, adj factor → 1.000, next_event, status FRESH), append old→new + category + reason to `state/valuation-log.md`, mark the event Done?=Y. Rows with OPEN ORDERS and a CA ex-date ≤2 trading days away: notify user with the rebased price and ask to confirm broker handling.

**Equal evidence depth (all markets + ballast):** VN-style detail is the **minimum for every MARKET** (US/UK/DE/AU too) and for real-assets. Do **not** stub UK/DE/AU as 3-column shorts while VN gets full tables. Same columns everywhere: price, % vs 52w/ATH, key multiple (PE and/or FCF yield after SBC; banks P/B×ROE), one quality fact, committee label, one-line vs zones/hurdle. Ballast gets the same numeric seriousness (spot, vs peak, real-rate/deck test, verdict, source+date) — not a one-line “gold not cheap.”

**Empty-screen delivery (mandatory on EQUITY screens):** a one-line “empty / keep cash” is **not** enough — users find it unpersuasive. Always show the work: (0) **macro pulse** (see below), (1) tape + hurdle, (2) **universe** of tickers actually opened — **full table per market screened**, (3) **shortlist** of closest maybes, (4) **per-name numerical fail**, (5) waiting-room instrument/rate/tenor. Brief empty without that evidence is a failed run.

**Macro pulse (mandatory on every equity / ballast / waiting-room / sale-off routine run):** Before labeling cheap vs not, skim live macro that can move the markets in scope (and VN home base even when screening abroad). Cover what printed recently; skip quiet items in one line. At least:
- **US:** Fed path (hike/hold/cut, dots/guidance), 10y UST + real yields, labor (NFP/unemployment/claims), CPI/PCE, fiscal/debt-ceiling or deficit headlines, tariffs/trade, USD.
- **Tech/AI:** material model/capex/regulation shifts that change AI-overlay or semis/software theses.
- **EU/UK/AU** when those markets are open: ECB/BoE/RBA stance, local CPI, growth surprises.
- **VN:** SBV policy rate / deposit-rate guidance, credit growth, FX VND, FDI/public investment, property/credit stress, CPI.
- **Geopolitics/energy** only when it moves oil, risk premia, or supply chains for names in the universe.

Use macro to (a) set cycle position and hurdle context, (b) flag **pre-sale-off** setup (tightening + rich valuations, credit stress, policy shock) vs (c) avoid mistaking a macro headline for a stock that is still expensive. Macro alone never forces a buy. Cite source + date.

**Role boundary (hard):** This skill is Finance / long-horizon QAD only. Read `ROLE_SPLIT.md`. Short/medium MMO, breakouts, shorts, and frequent trading belong to the sibling `swing-trend-trading` bot (Sóng). Do not invent swing entries here. If the user asks for a ≤~3 month trade or CFD scalp, say it is Sóng's book and stop (or hand off).

**LONG_CFD_CHANNEL (world only, optional execution path):** When a world equity or ballast clears Probe / Accumulate under this skill and cash-share access from VN is impractical, Finance may recommend a **long-only CFD** (e.g. Mitrade) that accepts overnight financing. Mandatory gates before any CFD suggestion: (1) committee label is Probe or Accumulate (never Watch/Avoid/Cycle-trade-only as a "buy now"); (2) Freshness gate + Pre-order checklist both pass; (3) estimate overnight financing vs expected MOS — if estimated 12m overnight cost ≥ half the MOS edge, prefer waiting-room instead; (4) size from ring-fenced CFD capital only, prefer unlevered-equivalent notional (do not suggest leverage that risks margin call); (5) never short via this channel; (6) keep QAD VN capital and Sóng trading capital untouched. Cadence stays event-driven — CFD does not justify intraday routines for Finance.

**Cadence note:** Finance routines exist to keep valuations fresh (earnings, CA, policy) and to bulletin sale-offs — not to catch intraday pivots. Missing a same-day bounce is acceptable; acting on a stale post-split/ex-rights print is not.

**Anti-paralysis:** “Valid equity output is zero names” means empty is *legal*, not that screens should usually be empty. Affirmative path: if quality + survivability clear and price is in good/very-good (or moderately attractive with bounded bear), prefer Probe or Accumulate over waiting-room. Probe/Watch with numeric price zones is **success**, not a failed buy recommendation. Stacked soft lenses (competence partial, excess thin, one behavior miss) must not be treated as hard fails — see `lenses.md` severity map.

All paths are next to this `SKILL.md`.

## 1. Detect `MARKET` and `MODE` (no extra files)

| Signal | MARKET |
|---|---|
| VNIndex, HOSE, HNX, UPCOM, Vietnamese tickers (FPT, MBB, HPG, …), “Vietnam stocks” | `VN` |
| NYSE, Nasdaq, S&P, 10-K, US 10Y, “US stocks”, NVDA/AAPL/BRK | `US` |
| FTSE, LSE, gilt, “UK stocks” | `UK` |
| DAX, Xetra, Bund, “German/European stocks”, SAP/SIE | `DE` |
| ASX, “Australian stocks”, BHP/CBA, franking | `AU` |
| “international / developed” with no country | `US` first; add others only if named or US is empty |

Ticker listing wins (FPT=`VN`, NVDA=`US`). Several names → several MARKET values, still **one pack per name**.

| MODE | When |
|---|---|
| `EQUITY` | Default |
| `AI_OVERLAY` | GPU, semis, foundry, wafer equipment, HBM, EDA, or hyperscaler thesis = AI capex |
| `REAL_ASSETS` | Gold/silver/metals/fertilizer/oil/gas asked, **or** equity screen returned nothing |
| `WAITING_ROOM` | Equity empty **and** real-assets (gold, metals, fertilizer, oil/gas) are not cheap. Mandatory. |

Hurdle (do not mix): VN = 12m VND deposit; US = 10y UST; UK = gilt; DE = Bund; AU = ACGB. Horizon: multi-year accumulation (1–2y is a floor, not a trade window).

## 2. Read map (mandatory)

After detection, **Read only these files** (in order). Stop. Do not browse the folder.

| Case | Files |
|---|---|
| Equity, one market | `core.md` → `lenses.md` → `sectors.md` → `markets/<market>.md` → `overlays/macro.md` |
| Equity + bank/tech/consumer/etc. | same |
| Recommending buy / sell / size / target | those, **then** `sizing.md` |
| `AI_OVERLAY` | equity files, **then** `overlays/ai-semis.md` **before** valuation |
| `REAL_ASSETS` only | `overlays/real-assets.md` → `overlays/macro.md` (skip `core.md` unless scoring a miner as a business) |
| Equity empty → ballast | `overlays/real-assets.md` after the equity files (macro already loaded) |
| Ballast not cheap / nothing in stocks or stuff is on sale | **then** `overlays/waiting-room.md` (do not skip) |
| Two markets named | `core.md` + `lenses.md` + `sectors.md` + **each** named `markets/*.md` + `overlays/macro.md` — skip the others |

`<market>` is `vn` `us` `uk` `de` `au`.

**Do not Read** unused market files, unused overlays, LICENSE, or README while analyzing.

## 3. Then run

Follow `overlays/macro.md` pulse first (or in parallel with tape), then `core.md` (10-agent committee) then `lenses.md` (competence, opportunity cost vs **index**, extra investor/institution gates). Apply the market pack. If you will recommend an action, Read `sizing.md` (expected value, not a single target price). If AI overlay hard-fails → no Strong buy / Accumulate.

**Multi-market screens:** each named MARKET gets its **own full universe table** (equal depth). Shortlists per market. Do not collapse non-home markets into a skinny appendix.

If the whole **equity** screen is empty → say so **with the evidence block above**, then real assets. If gold/metals/fertilizer/oil/gas also fail the cheap test → **waiting-room**: name the cash-like instrument, live rate, tenor, real yield, and the hold-until rule. Klarman: cash is an option. Marks: 2-sigma tape is leave-cash, not buy-the-dip. Never fill empty with a cigar-butt stock (falling price ≠ cheap). Never leave the user with “nothing to do.”

Committee label (required): Strong buy / Accumulate / Probe / Hold no add / Watch wait for price / Avoid on valuation / Avoid on quality / Cycle-trade only. Waiting-room is an **action**, not a committee equity label.

## State file + re-valuation write-back (mandatory)
Live price hooks for the user's watchlist live ONLY in `state/ladders.md`. Every routine/alert run reads it fresh; never use numbers baked into routine prompts or memory. After ANY revaluation (full or single-name), overwrite the affected rows, the date line, and move old hooks to "Superseded" in the same turn, before replying.
