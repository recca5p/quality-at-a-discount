# Core committee

Shared across every equity market. Market-specific filings, hurdles, and traps live in `markets/*.md`. Do not import those here.

## Do not confuse

- Good company vs stock worth buying
- Falling price vs cheap price
- Low P/E vs attractive valuation
- Revenue growth vs owner-value growth
- Accounting profit vs cash to owners
- Bonus shares / splits vs new value
- Buybacks vs value creation (buying above intrinsic **destroys** value)
- SBC / ESOP “non-cash” vs real dilution
- Index / Mag-7 / “AI winner” / upgrade lists vs a moat
- Cyclical upside vs a durable franchise
- Developed market vs safer stock (more professional capital → obvious cheapness is rarer)

Never force a pick. Goal is the right business, at the right price, with the right asymmetry — not “have exposure.”

## Data

Each full name: ~6–12 sources. Always: latest annual + last two interims; IR / proxy / AGM; exchange or regulator for price and **fully diluted** shares; independent industry data; fresh corporate actions. Press only to verify events. Forums / Glassdoor / Twitter are leads, then confirm or kill with filings.

Fully diluted = options + RSU/PSU + converts + ESOP + rights + pending bonus. Never compare a pre-bonus price to post-dilution EPS. Adjust for splits, rights, one-offs, restatements, M&A, consolidation changes.

Investigate-then-verify examples: “workload up” → revenue/employee, headcount, margin, attrition; “orders up” → receivables, prepayments, CFO; “healthy loan growth” → group-2/NPL, provisions, deposit growth, NIM; “AI demand exploding” → customer capex vs D&A, cancelable backlog, concentration.

## Ten agents (do not skip)

Do not average opinions. Name the data that matters and unresolved conflicts.

**1 Data & filings** — price, fully diluted shares, mcap, EV (leases, unfunded pensions), book / tangible book; 5–10y revenue, EBIT, NI, CFO, FCF, SBC; debt, cash, maintenance vs growth capex, receivables, inventory, deferred revenue; issuance / buybacks / insiders; latest quarter vs year-ago (and vs 8 quarters if cyclical).

**2 Moat** — where cash actually comes from; mix by segment; recurring vs re-sold every period; switching costs; brand / network / license / data / scale / cost / IP; concentration; substitution (AI, imports, policy). Classify honestly: product/IP, implementation, outsourcing, distributor, or only *using* AI. Moat in 5–10y: stronger / stable / weaker. Cheap labor, cheap land, cheap credit, or a customer’s capex binge is not a moat.

**3 Earnings & cash** (non-banks) — 5–10y CFO/NI; FCF after **SBC** and maintenance capex (SBC is cash); receivables vs sales; inventory vs sales/volume; one-offs, revals, reversals; margin from productivity vs deferred cost; associate cash actually reaching the parent; EPS vs share count. Rising profit + weak CFO, ballooning receivables, borrow-to-dividend, or issue-to-fund-ops → not sustainable cash. Banks: skip CFO, use `sectors.md`.

**4 Balance sheet** — net debt/EBITDA on **mid-cycle** earnings, interest cover, maturity wall, covenants, collateral, leases, pensions, related-party guarantees, FX. A true sale-off requires the firm can live through the mispricing, including a local recession.

**5 Governance & dilution** — **economic** dilution %/year, not share-count theatre. ESOP/RSU strike vs market; lockups; private placements (to whom, why); related-party deals; pay vs owners; dividend covered by FCF; ROIC on retained earnings; buybacks when cheap vs issuance when cheap. Bonus shares to all holders are not profit. Developed-market twin of VN par-ESOP: cheap RSUs + buybacks that only offset dilution = **zero net shrink**.

**6 Sector & macro** — trough / mid / peak; real demand vs credit/fiscal; policy durability; rates, FX, CPI, inputs. High GDP does not make every bank, steel, property, retailer, or Mag-7 a buy. Story attachment ≠ direct beneficiary.

**7 Valuation** — at least two of: P/E on **normalized** earnings; P/B × sustainable ROE (banks); EV/EBIT or EV/EBITDA mid-cycle; FCF yield on owner earnings; DCF with fading ROIC; SOTP; NAV (assets/REITs); mid-cycle for commodities/brokers; reverse DCF vs **this MARKET’s hurdle**. Compare to own history, close peers, and current local cost of capital. Bear / base / bull. Answer: sentiment or decaying internals? Can normalized earnings hold? Can the balance sheet wait? How much of bear is in the price? Base upside should be ≥ ~2× realistic downside over 3–5 years.

**8 Red team** — ≥3 ways the buy is wrong; one −25% to −40% path; numeric watchpoints. Hunt: structural decline under short-term growth; sales up / cash down; under-provisioning; dependence on cheap credit, land, policy, one customer, or hyperscaler capex; AI substitution; dilution-for-growth; good business still too expensive; peak-cycle earnings; catalyst already priced.

**9 Portfolio** — core / cyclical / tactical / avoid; max weight; deploy now vs wait; very-good / good / fair / expensive in **local currency**, split-adjusted; add rules; **do-not-average-down** rules; trim/exit. Weight by certainty, MOS, leverage, cyclicity, liquidity, FX, correlation. A world-index mega-cap is worse diversification than it looks.

**10 Committee** — do not average. Run `lenses.md` before a buy label. One label: Strong buy / Accumulate / Probe / Hold no add / Watch wait for price / Avoid on valuation / Avoid on quality / Cycle-trade only. AI overlay hard-fail **or** competence=`cannot` blocks Strong buy / Accumulate. If recommending an action, Read `sizing.md` and emit expected value (no single target price).

## Score / 100

| Group | W |
|---|---|
| Moat | 20 |
| Growth / unit economics | 10 |
| Earnings & cash quality | 15 |
| Balance sheet / survivability | 10 |
| Governance, allocation, dilution | 10 |
| Valuation & MOS | **25** |
| Catalyst | 5 |
| Asymmetry | 5 |

S strong buy · A accumulate · B watchlist · C tactical · D avoid. Score cannot hide a hard fail.

## Hard fails (no Strong buy / Accumulate)

Going-concern, material weakness, serial restatement, weak disclosure; profit/FCF dominated by one-offs; chronic weak FCF/CFO without a clean WC story (non-banks); ST liquidity or an unpayable maturity wall in the bear; opaque related parties; repeated dilution without ROIC lift; structurally declining industry; price only works in a perfect scenario; cannot estimate intrinsic value; realistic downside ≥ base upside; reverse DCF needs growth never earned through a full cycle; AI overlay hard-fail.


## Soft gates (do not promote to hard fail)

These **cap** the label; they do **not** force BUY=0 by themselves:

- competence=`partial` → Probe max (not Avoid)
- sale-off = moderately attractive (not true) → Probe or small Accumulate if zones good/very-good and bear bounded
- `excess_vs_index_bp` thin but `excess_vs_rf_bp` healthy → no Accumulate; Probe still allowed if other bars clear
- one behavior-gate miss → no Accumulate; may still Watch / Probe
- base upside < ~2× downside → prefer Probe / Wait for price; only hard-fail if realistic downside dominates EV / `p_ruin` (see `sizing.md`)

Hard fails above remain the only automatic “no Strong buy / Accumulate” quality vetoes. Do not AND every soft preference into a silent empty book.

## Sale-off test

**True sale-off:** price down hard, earning power intact, cash and balance sheet healthy, issue temporary or over-discounted, below own reasonable history **and** below intrinsic, no hero growth needed, bear case is an acceptable loss.

**Down but not cheap:** was 40× now 28×; Mag-7 −15–20% from ATH; a quality compounder −30% from a 31× bubble.

**Value trap:** peak margins/cycle, weak cash, high debt, substitution (including AI), adverse dilution, cheap with no owner-value mechanism, catalyst is a market-wide hope.

Developed markets rarely offer crisis multiples on fortress businesses. A 20–30% discount to conservative value on a high-quality compounder can be enough if the bear is bounded. A 10% dip on an “AI winner” is not.


**BUY-WHEN (affirmative):** quality underwritable + balance sheet can wait + price in **good / very-good** (corporate-action adjusted) + bear acceptable → emit Probe or Accumulate. True sale-off is ideal for sizing up; it is **not** required before any buy label. Moderately attractive + good zone = valid Probe (and Accumulate if competence=`full` and lenses soft caps allow).

## Output per name (required)

1. One-sentence verdict + `MARKET` + `MODE`
2. Tier, /100, score by group
3. Buy thesis: 3–5 real drivers
4. Moat and substitution (include AI)
5. Financial quality (FCF after SBC, or bank metrics)
6. Dilution / allocation (economic %/year)
7. Valuation: local price; bear/base/bull; upside/downside; history; peers; reverse DCF vs hurdle
8. Sale-off label: true / moderately attractive / fair / not cheap / potential value trap
9. Price zones (very good / good / fair / expensive), corporate-action adjusted — **rebase numeric hooks on every bonus/split** (`zone/(1+ratio)`); ex-rights ref ≠ zone entry; never treat a mechanical print drop as cheapness
10. Thesis breakers (numbers)
11. Action: % of a position, wait for next print?, add, do-not-average-down, hold period, FX

Empty screen: BUY list may be zero, but **show the work** — a bare “empty / keep cash” is a failed delivery. Required:

0. **Macro pulse** (`overlays/macro.md`) — Fed/rates/labor/fiscal/tariffs/AI as relevant, SBV/VN, pre-sale-off line.
1. **Tape** + live hurdle (deposit / UST / gilt / Bund / ACGB) and CPI/real yield when relevant. **Every MARKET screened** gets the same table depth (no stub UK/DE/AU while VN is full).
2. **Universe table** — every ticker actually opened (not a mental list): price, % vs 52w/ATH, key multiple (P/B×ROE banks; FCF yield or PE others), one filing/IR quality fact, committee label, one-line vs **price zones** (and vs true sale-off if claimed), vs hurdle; Probe / Watch wait for price are successful outputs, not empty.
3. **Shortlist** — 4–6 closest maybes with denser reasons (moat, cash/bank metrics, valuation vs crisis bar or deposit, red-team).
4. Explicit **BUY = 0** (or survivors with the 11-point block).
5. Then cash / `overlays/real-assets.md` / `overlays/waiting-room.md` as the router requires.


**Calibration:** BUY=0 on one tape does not mean “this skill never buys.” If 4–6 shortlist names sit just above good-zone with clear triggers, say so and NOTIFY when price hits (router sale-off NOTIFY). Historical feel-check: VN bank crisis 2022-style prints on fortress banks were buys; a quality VN IT compounder at deposit-beating FCF yield in good zone can be Probe/Accumulate without matching 2022 bank P/B; a Mag-7 −15% from ATH is usually still Avoid on valuation. Use those shapes — do not require every market to reprint 2022.


Do not fill with forced buys. Action recommendations also need the `sizing.md` block (EV, excess vs index, size_rec).

## Final rules

Do not buy because of an upgrade list, low P/E, a hot quarter, a management story (including AI), a broker target, high GDP, or “the market is developed.” Do not ignore dilution or cash. Do not treat a falling price as an opportunity when the model is in structural decline. Do not fear cash, T-bills, or ballast.
