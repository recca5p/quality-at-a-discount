---
name: Quality-at-a-Discount
description: >-
  Use this whenever the user wants long-term accumulation (tích sản): screen or
  analyze stocks, ETFs, or real-asset ballast for a quality business that is
  hard to replace and currently on a true sale-off. Auto-detect market from the
  question (VN, US, UK, DE, AU, or mixed). Includes the AI/semiconductor cycle
  overlay and a gold/metals/fertilizer/oil fallback. Valid output is zero names.
---

# Quality-at-a-Discount

One skill. Market is a **variable**, not a separate playbook. Core never changes: **good business, hard to replace, price is a true sale-off, hold to accumulate.** Valid conclusion is nothing to buy. Never pick a ticker to finish the answer. Never rotate into another country just because the home market is fairly priced.

## 0. Router (run first, every time)

### 0.1 Detect `MARKET`

Read the user's words, tickers, and exchanges. Set one primary `MARKET` (or a list if they named several). Do not ask if it is obvious.

| Signal | MARKET |
|---|---|
| VNIndex, HOSE, HNX, UPCOM, Vietnamese names, tickers like FPT/MBB/HPG, “cổ phiếu Việt” | `VN` |
| NYSE, Nasdaq, S&P, US 10Y, “cổ Mỹ”, NVDA/AAPL/BRK, 10-K | `US` |
| FTSE, LSE, AIM, gilt, “cổ Anh”, SHEL/ULVR/AZN | `UK` |
| DAX, Xetra, Frankfurt, Bund, “cổ Đức/Âu”, SAP/SIE/ALV, Euro-core NL/FR/CH named with DE | `DE` |
| ASX, “cổ Úc”, BHP/CBA/WOW, RBA, franking | `AU` |
| Unspecified “quốc tế / developed / ra nước ngoài” | Screen `US` first, then `UK`/`DE`/`AU` only if US is empty or they named those markets |
| Gold, silver, dầu, phân bón, kim loại, “ETF hàng hóa”, or equity screen returns nothing | `MODE=REAL_ASSETS` (still record a MARKET for listing currency) |

If they name a ticker, the **listing** wins (FPT=`VN`, NVDA=`US`, TSM listed in US or TW — treat listing used to buy).

### 0.2 Detect `MODE`

| MODE | When |
|---|---|
| `EQUITY` | Default. Stocks / equity ETFs of businesses. |
| `AI_OVERLAY` | Name or theme is GPU, semiconductor, foundry, wafer equipment, HBM/memory, EDA, or a hyperscaler whose thesis is AI capex. Run §6 **before** scoring valuation. Overlay hard-fail blocks Accumulate / Strong buy. |
| `REAL_ASSETS` | User asked for gold/silver/metals/fertilizer/oil, or `EQUITY` returned nothing worth buying. Run §7. Do not stretch equities to avoid this mode. |

A name can be `EQUITY` + `AI_OVERLAY`. A screen can end in `REAL_ASSETS`.

### 0.3 Hurdle rate (bind to MARKET)

Earnings yield and FCF yield are compared to **this table**, not to a vibe.

| MARKET | Risk-free | Extra notes |
|---|---|---|
| VN | 12-month big-bank VND deposit (and 10y VGB if useful) | Bonus shares and par ESOP are not yield |
| US | 10-year UST | FCF **after SBC** |
| UK | 10-year gilt | Bake 0.5% stamp into MOS |
| DE | 10-year Bund | IFRS, pensions, export cycle |
| AU | 10-year ACGB | Ignore franking for a non-resident |

### 0.4 Horizon

Default **multi-year accumulation** (3–10y). If they said 1–2 years, that is the **minimum** hold, not a trading window.

---

## 1. Do not confuse

- A good company vs a stock worth buying
- A falling price vs a cheap price
- Low P/E vs attractive valuation
- Revenue growth vs value-creating growth for owners
- Accounting profit vs cash to owners
- Bonus shares / splits vs newly created value (`VN` especially)
- Buybacks vs value creation (buybacks **above** intrinsic value destroy value)
- SBC / ESOP “non-cash” vs real dilution
- Index membership, Mag-7, “AI winner”, FTSE upgrade vs a durable moat
- Cyclical upside vs a hard-to-replace franchise
- A developed market vs a safer stock (more professional capital makes **obvious** cheapness rarer)

---

## 2. Data standard

Each full name: ~6–12 sources.

**Always:** latest annual + last two interims; IR / proxy / AGM; exchange or regulator for price and fully diluted shares; independent industry data; fresh corporate actions.

**By MARKET:**
- `VN` — BCTC/BCTN, SSC, HOSE/HNX, nghị quyết, CafeF/Vietstock only to locate filings
- `US` — 10-K, 10-Q, 8-K, DEF 14A, Form 4
- `UK` — annual report + RNS
- `DE` — Geschäftsbericht, BaFin / Bundesanzeiger
- `AU` — annual report + ASX filings

Forums, Glassdoor, Twitter are investigation signals. Confirm or kill them with filings.

Adjust for splits, bonus shares, rights, spin-offs, ESOP/SBC, one-offs, restatements, M&A, discontinued ops. Never compare a pre-bonus price to post-dilution EPS. Fully diluted = options + RSUs/PSUs + convertibles + pending bonus/rights.

---

## 3. Analysis sequence (do not skip)

1. **Data** — price, fully diluted shares, mcap, EV (leases, pensions), book; 5–10y revenue, EBIT, NI, CFO, FCF, SBC/ESOP; debt, cash, maintenance vs growth capex, receivables, inventory; buybacks/issuance/insiders; latest quarter vs year-ago.
2. **Moat** — how cash is earned; recurring vs re-sold; switching costs; brand/network/license/scale/cost/IP; concentration; substitution (AI, imports, policy). Classify honestly: product/IP, implementation, outsourcing, distributor, or only *using* AI. Moat in 5–10y: stronger / stable / weaker.
3. **Cash quality** — 5–10y CFO/NI; FCF after SBC and maintenance capex (treat SBC as cash); receivables vs sales; one-offs. Rising profit + weak FCF, ballooning receivables, or debt-funded buybacks/dividends is not owner earnings. **Banks:** skip CFO; use the bank module.
4. **Balance sheet** — net debt/EBITDA on *mid-cycle* earnings, interest cover, maturity wall, leases, pensions, FX. A true sale-off requires the firm can live through the mispricing.
5. **Governance & dilution** — **economic** dilution %/year (VN par ESOP; US cheap RSUs + offsetting buybacks). Who got private placements. Related parties. Dividends covered by FCF. ROIC on retained earnings. Buybacks when cheap vs issuance when cheap.
6. **Sector & macro** — cycle trough/mid/peak; real demand vs credit; policy; rates/FX/CPI/inputs. High GDP is not a buy signal for every bank, steel, property, or retailer.
7. **Valuation** — ≥2 methods: P/E on **normalized** earnings; EV/EBIT or EV/EBITDA mid-cycle; FCF yield on owner earnings; DCF with fading ROIC; SOTP; P/B × sustainable ROE for banks; NAV for assets; reverse DCF vs the MARKET hurdle. Bear / base / bull. Is base upside ≥ 2× realistic downside?
8. **Red team** — ≥3 ways the thesis is wrong; one −25% to −40% path; numeric watchpoints.
9. **Portfolio** — core / cyclical / tactical / avoid; max weight; deploy now vs wait; very-good / good / fair / expensive in **local currency**; add / do-not-average-down / trim. Weight by certainty, MOS, leverage, cyclicity, liquidity, FX, correlation.
10. **Committee** — do not average notes. Verdict must be one of: Strong buy / Accumulate / Probe / Hold no add / Watch wait for price / Avoid on valuation / Avoid on quality / Cycle-trade only.

If `AI_OVERLAY`, insert §6 between steps 2 and 7. If it hard-fails, skip Strong buy / Accumulate.

---

## 4. Score (100)

| Group | Weight |
|---|---|
| Business quality and moat | 20 |
| Growth and unit economics | 10 |
| Earnings and cash-flow quality | 15 |
| Balance sheet and cycle survivability | 10 |
| Governance, capital allocation, dilution | 10 |
| Valuation and margin of safety | **25** |
| Catalyst | 5 |
| Risk/reward asymmetry | 5 |

**S** strong buy · **A** accumulate · **B** watchlist · **C** tactical/cycle · **D** avoid.

Score cannot hide a hard fail.

### Direct disqualifiers (no Strong buy / Accumulate)

Going-concern, material weakness, serial restatements, or `VN` audit concern; profit/FCF dominated by one-offs; chronically weak FCF/CFO without a clean WC explanation; ST debt or liquidity stress; opaque related parties; repeated dilution without ROIC lift; structurally declining industry; price only works in a perfect scenario; cannot estimate intrinsic value with minimum confidence; realistic downside ≥ base upside; reverse DCF needs growth the firm never earned through a full cycle; `AI_OVERLAY` hard-fail.

---

## 5. MARKET packs (apply the matching row)

### VN

Filings in Vietnamese, HOSE/HNX/UPCOM. **Bonus shares / stock dividends are not value** — always split-adjust. Par ESOP is real economic dilution. Banks: P/B + sustainable ROE, NIM, CASA, group-2, NPL, LLR, credit cost, CAR, LDR, loan vs deposit growth, CRE/bonds, related-party, bancassurance/reversals — not CFO. Property: default avoid unless per-project legal + cash collected + NAV-to-cash is documented. Brokers: never value on one boom quarter. Steel/fertilizer: mid-cycle, never peak H1. Tech (FPT/CMG): outsourcing/SI/telecom, not an “AI stock.” FTSE/MSCI upgrade is not a thesis.

### US

10-K/Q, DEF 14A, Form 4. Dilution = RSU + option + convertible. Buyback yield ≈ SBC ⇒ **zero net shrink**. Banks: CET1, NCO, AOCI, HTM vs AFS, deposit beta. Energy/materials: mid-cycle strip. Software: FCF after SBC and net retention, not Rule of 40. Do not treat S&P/QQQ/Mag-7 as quality. Equal-weight or unloved cash compounders are the usual hunting ground when the index is concentrated. A 15–20% Mag-7 dip is usually **down but not cheap**.

### UK

RNS + annual report. Stamp 0.5% is a round-trip cost. FTSE 100 is global oil, miners, banks, pharma, luxury — **not** “the UK economy.” Check pension deficit, IFRS 16, dividend after sustaining capex (UK boards over-distribute).

### DE (Euro-core allowed)

Geschäftsbericht. Auto and chemicals: mid-cycle + China-bear. Family dual-class is a haircut, not an auto-fail. Power prices and energy policy can change unit economics before the P&L does. SAP-class software still needs MOS vs US peers.

### AU

ASX filings. Big-4 banks + BHP/RIO dominate. **Franking is worthless to a foreign accumulator** — do not pay up for it. Iron ore/coal/lithium: mid-cycle China demand. AUD is a commodity currency; a miner is a geared China bet. Banks: house prices + APRA, not Vietnamese NPL rules.

---

## 6. AI / semiconductor overlay (`MODE=AI_OVERLAY`)

AI is real. **The price of AI infrastructure is often a cycle.** Do not buy the theme. Classify, then ask if today’s earnings assume peak capex forever.

**Bucket (pick one):** (1) accelerator/GPU vendor (2) foundry (3) wafer equipment / EDA (4) memory/HBM (5) hyperscaler whose thesis is AI capex (6) application software with an “AI feature” (7) power/cooling/networking/OSAT.

**Deflation path (must write, or state that none exists):** AI *use* can grow while this firm’s earnings fall 20–40% via hyperscaler capex pause, custom ASICs, model efficiency (tokens per watt up, capex/token down), China stack, accelerator competition, or power bottlenecks. That is how the complex “xì hơi” — not “AI dies.”

**Checklist:** customer capex vs D&A for 2–3y; cancelable backlog; training vs inference; China/export-control share; top-1 / top-4 concentration; utilization or GPU lead times; GM vs 10y range (haircut records); capex/sales; reverse DCF vs through-cycle growth at local 10y+4–6%.

**Hard-fail:** reverse DCF needs peak hyperscaler capex for 3+ years; top customer ≥ ~25–30% and that customer is cutting capex; GM/bookings at a cycle record and multiple still above 10y median; thesis is only “AI TAM”; China share material and unmodeled; foundry/equipment valued on peak utilization; hyperscaler AI ROIC unproven but fully capitalized.

**Soft-fail:** franchise OK but FCF yield < local 10y+2%, or drawdown from ATH < 25% with no earnings reset.

A fortress foundry or EUV monopoly can still be Watch / Avoid on valuation.

---

## 7. Real assets (`MODE=REAL_ASSETS`)

Fallback **sleeve**, not a substitute for a great business. Size so you can still buy stocks when a sale-off appears. Cash in the listing currency (USD T-bills, VND deposits) is a valid waiting room — do not “do something” with commodities.

**Instrument order:** (1) physically allocated bullion ETF (2) royalty/stream only if underwritable, then score as a business (3) first-quartile producer at a **low** price deck (4) avoid juniors, explorers, 2x/3x ETFs.

**Mid-cycle:** never value oil, urea, iron ore, copper, lithium on a top-quartile real-price year. State the low/mid/high deck. Futures oil ETFs: show roll yield; steep contango ⇒ skip or use a producer. Gold has **no earnings yield** — opportunity cost vs real rates and vs cash; a miner is high-beta, not “safer gold.” Silver smaller than gold. Fertilizer: nitrogen vs potash vs phosphate are different cycles (same trap as VN DCM/DPM). Do not stack gold + miners + AUD + iron ore + oil.

**Trim rule:** sell/trim this sleeve when an equity name enters the good/very-good zone.

---

## 8. Sector modules (all markets)

**Banks** — P/B vs sustainable ROE vs COE. `VN`: NPL, group-2, LLR, CAR, LDR, CRE. `US`: CET1, NCO, AOCI, HTM. Through-cycle ROE, not this year.

**Tech / IT services / software** — recurring mix, FCF after SBC, concentration. `VN` FPT/CMG = outsourcing/SI, not AI product. Software Rule of 40 is marketing.

**Semis / hyperscaler AI capex** — stop, run §6.

**Consumer** — share, pricing power, volume vs price, WC, private-label/online substitution.

**Steel, chemicals, fertilizer, energy, miners** — mid-cycle volume and price, cost curve / AISC, sustaining capex, balance sheet at a **low** deck. Peak-year P/E is a trap. If the “business” *is* the commodity, prefer §7 unless the producer has a true low-cost moat.

**Property / REITs** — legal/`VN` project papers, presales cash, NAV-to-cash, LTV, refi wall. Default high bar.

**Brokers** — mix of brokerage, margin, prop. Never value one boom quarter.

---

## 9. True sale-off vs not

**True sale-off:** price down hard, earning power intact, cash and balance sheet healthy, issue temporary or over-discounted, below own reasonable history **and** below intrinsic, no hero growth needed, bear case is an acceptable loss.

**Down but not cheap:** was 40×, now 28×; Mag-7 −15%; `VN` quality names −20% from a 31× bubble.

**Value trap:** peak margins, peak cycle, weak cash, substitution (including AI), dilution, or a commodity at the top.

Developed markets rarely offer crisis multiples on fortress businesses. A 20–30% discount to conservative value on a high-quality compounder can be enough if the bear is bounded. A 10% dip on an “AI winner” is not.

---

## 10. Required output per name

1. One-sentence verdict (and `MARKET` + `MODE` you used)
2. Tier S/A/B/C/D, total /100, score by group
3. Buy thesis: 3–5 real drivers
4. Moat and substitution (include AI)
5. Financial quality (FCF after SBC, or bank metrics)
6. Dilution and capital allocation (economic %/year)
7. Valuation: local price; bear/base/bull; upside/downside; history; peers; reverse DCF vs MARKET hurdle
8. Sale-off: true / moderately attractive / fair / not cheap / potential value trap
9. Price zones in local currency (very good / good / fair / expensive)
10. Thesis breakers (numbers)
11. Action: % of a position, wait for next print?, add, do-not-average-down, hold period, FX note

Committee line (mandatory): Strong buy / Accumulate / Probe / Hold no add / Watch wait for price / Avoid on valuation / Avoid on quality / Cycle-trade only.

If the whole screen is empty: say so, then either wait in cash or run §7. Do not fill the page.

---

## 11. Final rules

Do not buy because the market is developed, because VNIndex is “cheap vs history,” because of an upgrade list, a strong quarter, a broker target, low P/E, Mag-7, or “everyone needs AI.” Do not ignore dilution or cash. Do not treat high GDP as shareholder returns. Do not treat a falling price as an opportunity when the model is in structural decline. Do not fear concluding that **cash or real-asset ballast** is better.

The goal is not many tickers and not “have US exposure.” The goal is the right business, at the right price, with the right asymmetry, for long accumulation.
