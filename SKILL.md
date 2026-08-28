---
name: Quality-at-a-Discount
description: >-
  Use this whenever the user wants long-term accumulation: screen or
  analyze stocks, ETFs, or real-asset ballast for a quality business that is
  hard to replace and currently on a true sale-off. Auto-detect market (VN, US,
  UK, DE, AU). Load ONLY the files this router names — never the whole pack.
  Valid output is zero names.
---

# Quality-at-a-Discount (router)

**Load only what the question needs.** This file is the index. Do not read every sibling. A VN question must not load US/UK/DE/AU. An equity question must not load gold unless the equity screen is empty or they asked for ballast.

Core rule, every market: good business, hard to replace, **true sale-off**, hold to accumulate. Valid answer is nothing to buy. Never pick a ticker to finish.

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
| `REAL_ASSETS` | Gold/silver/metals/fertilizer/oil asked, **or** equity screen returned nothing |

Hurdle (do not mix): VN = 12m VND deposit; US = 10y UST; UK = gilt; DE = Bund; AU = ACGB. Horizon: multi-year accumulation (1–2y is a floor, not a trade window).

## 2. Read map (mandatory)

After detection, **Read only these files** (in order). Stop. Do not browse the folder.

| Case | Files |
|---|---|
| Equity, one market | `core.md` → `sectors.md` → `markets/<market>.md` |
| Equity + bank/tech/consumer/etc. | same; sector extra is already in `sectors.md` + the market file |
| `AI_OVERLAY` | those three, **then** `overlays/ai-semis.md` **before** scoring valuation |
| `REAL_ASSETS` only | `overlays/real-assets.md` (skip `core.md` unless you are scoring a miner as a business) |
| Equity empty → ballast | `overlays/real-assets.md` after the equity files |
| Two markets named | `core.md` + `sectors.md` + **each** named `markets/*.md` — still skip the others |

`<market>` is `vn` `us` `uk` `de` `au`.

**Do not Read** unused market files, unused overlays, LICENSE, or README while analyzing.

## 3. Then run

Follow `core.md` (10-agent committee, score, hard fails, sale-off test, 11-point output). Apply the market pack. If AI overlay hard-fails → no Strong buy / Accumulate. If the whole screen is empty → say so, then cash or real assets.

Committee label (required): Strong buy / Accumulate / Probe / Hold no add / Watch wait for price / Avoid on valuation / Avoid on quality / Cycle-trade only.
