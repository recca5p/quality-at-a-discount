# Extra lenses (always with `core.md` on EQUITY)

The user's QAD checklist is a **starting skeleton**, not scripture. It is Buffett-ish and subjective. Before Strong buy / Accumulate, run these gates. Do **not** load investor biographies. If a lens conflicts with `core.md`, **do not average**: name the conflict and let the stricter hard-fail win.

Sources distilled 28 Aug 2026 from primary letters/memos (Buffett 1986/1989/2007; Graham 1973/1976; Marks 2015; Fundsmith 2025; Klarman MiB 2026; Li Lu 2019; Nomad 2021) and official institutional process (Dodge & Cox ADV 2026; Morningstar moat; Yale/Swensen; Capital System; GMO; Orbis). Cite the lens by name in the memo; do not fake quotes.

## A. Competence (Buffett)

Can we describe, in numbers, how cash arrives and what it looks like in 10 years **without** a tech/regulatory forecast we cannot make? Outcomes: `full` / `partial` / `cannot`.

- `cannot` → no Strong buy / Accumulate (same severity as a quality hard-fail).
- `partial` → Probe cap only.
- Fast-changing industries, person-as-moat, thin listings, pre-revenue stories: default `cannot` unless mid-cycle owner earnings are underwritable from filings.
- **Policy-influenced banks:** default `partial` (Probe cap) when credit quality, NIM, LLR/NPL, and deposit franchise are underwritable from filings; use `cannot` only if those owner metrics cannot be estimated. “Policy bank” alone is not a hard fail.

## B. Opportunity cost (Buffett / Munger / Dodge & Cox)

Every dollar has a next use. Compute, all in **local currency**, then in the spender's currency (usually VND):

| ID | What |
|---|---|
| `rf` | This MARKET's hurdle (from the router) |
| `cpi` | Latest CPI; `real_rf = rf - cpi` |
| `index_er` | 5y expected **real** return of the boring default (VN30 / S&P or equal-weight / FTSE All-Share / DAX / ASX 200) — state the assumption, do not invent a precise model |
| `idea_er` | 5y expected **real** owner-earnings yield + growth you will actually underwrite (haircut by base rates) |
| `excess_vs_rf_bp` | (`idea_er` − `real_rf`) × 10000 |
| `excess_vs_index_bp` | (`idea_er` − `index_er`) × 10000 |
| `next_best` | Named: cash / ballast / a watchlist ticker |

**Label caps (severity):**

- `excess_vs_index_bp` < **+200** after costs/tax/FX → **no Accumulate / Strong buy**. Probe / Watch wait for price remain allowed if quality and price-zone bars clear.
- If `next_best` has equal-or-better quality at higher EV → prefer that name (or cash); do not force the weaker idea.

**When the default index is 2-sigma expensive / euphoric (Marks/GMO):** do **not** plug a long-run historical `index_er` (that falsely kills ideas). Set `index_er` to a **depressed forward real** assumption consistent with rich starting valuation (state it), *or* mark `index_er` UNKNOWN and gate Accumulate mainly on `excess_vs_rf_bp` ≥ **+200** plus MOS. Expensive tape makes cash/waiting-room more attractive; it must not make *relative* excess impossible by using optimistic index ER.

Leaving the home market is allowed only when the foreign name clears the **same** quality bar after country-risk, FX, and tax — not because GDP is high (GMO/Swensen). Home-index concentration (Vin-skew, Mag-7) is a reason to look, not a reason to buy junk abroad.

## C. Wonderful vs cigar (Buffett 1989; Graham eras)

- Time is the friend of a wonderful business and the enemy of the mediocre. A fair company at a wonderful price is usually **Cycle-trade**, not accumulation.
- Do not mix Graham eras: classic MOS + Mr Market ≠ 1976 mechanical P/E 7–10 on 30 names. Quality **does not waive** the price test (Graham would reject a 25–40× compounder that a naive QAD still likes).
- Name the moat **source** (cost, brand, network, license, switching, scale). A moat that must be rebuilt every year is no moat (Buffett 2007). A superstar manager is not a moat.

## D. Owner earnings (Buffett 1986)

Owner earnings = reported earnings + D&A − **maintenance** capex (and WC) to hold competitive position and unit volume. Adding back D&A without subtracting maintenance is how people “justify the unjustifiable.” If maintenance > D&A, GAAP overstates. This is the same spirit as `core.md` FCF-after-SBC; if they disagree, use the **lower** number.

## E. Cycle and second-level (Marks; GMO)

Write the cycle position: trough / mid / peak / unknown. Risk = more things can happen than will. A cheap multiple on peak-cycle earnings is not cheap. 2-sigma valuations **plus** euphoria is a leave-cash / leave-market signal, not a buy-the-dip signal.

## F. Cash, catalyst, scuttlebutt

- Klarman: cash is an option; a catalyst is nice, not required; MOS is required. Do not stretch quality to “do something.”
- Fisher: at least two **filing-checkable** scuttlebutt items (customers, competitors, ex-employees) — still verify with financials (`core.md` data bar).
- Lynch: “know what you own.” If the one-sentence business description needs a story deck, you do not know it. PEG is a warning light, not a religion.
- Fundsmith / Terry Smith: great companies, stay in the circle, do not overpay; sell when the thesis or the people break, not because a 12-month target was hit.
- Nick Sleep: scale-economies-**shared** (give efficiency to customers) vs extracted. Extraction often shows up as margin that cannot last.

## G. Institutional process (steal vs do not copy)

**Steal:** two prices (IV vs market); named moat; ROIC > WACC **duration**, not one year; recast earnings; leverage screen (~2.5× mid-cycle ND/EBITDA as a flag, not a law); written mispricing + what the market is missing; devil’s advocate (Agent 8 is the minimum — add one named disagreement); 3–5y downside in currency of spend; insider buys as a bonus, never a thesis; float/liquidity; country **operating** map + ERP, not the listing; agency/incentives.

Morningstar-style capital allocation (if you can score it from filings, do): balance sheet, reinvestment ROIC, distributions. Do not scrape a paywalled grade and pretend.

**Do not copy:** tracking-error / closet indexing; sector representation for its own sake; policy weights that force buying expensive assets; PE/VC tourism; 100-name books; 1-year relative performance; GDP-weighted EM; sell-side target theater; treating illiquidity as a virtue.

Orbis-style: **no hard target price as a sell trigger**. Gradual exit. Sell at a loss if the thesis dies.

## H. Naive-QAD rejects (run before a buy label)

A screen can still love these; these lenses usually should not:

| Pattern | Who objects |
|---|---|
| Mediocre business, optically cheap | Buffett 1989; Fundsmith |
| Peak-cycle ROIC on airlines/steel/fertilizer/brokers | Buffett 2007; `sectors.md` |
| 25–40× “quality” with no MOS vs rf or index | Graham defensive; Dodge & Cox starting price |
| Forecast PEG / recovery earnings | Late Graham (use reported) |
| Moat = person, fashion, or fast tech you cannot underwrite | Buffett Dexter/IBM |
| Thesis = AI TAM / Mag-7 / FTSE upgrade | `overlays/ai-semis.md`; `markets/vn.md` |
| Cheap bank leaving the coverage fortress, CRE accelerating | `markets/vn.md` + this file’s leverage flag |
| Foreign listing because “developed markets are wiser” | GMO / this file §B |

## I. Behavior gate (Accumulate / Strong buy)

Score each **pass/fail**. Accumulate requires **all pass**. One fail → cap at Probe / Watch / Hold — **not** automatic Avoid and **not** empty screen.

1. Am I using money I need in < 3 years? → **fail if yes** (that is trading, not accumulating). Pass = no.
2. Am I buying because it went down, or because IV is higher than price? → pass only if IV > price (MOS), not “it fell.”
3. Did I write the bear case before the bull? → pass = yes.
4. Is competence at least what the label needs? (`full` for Accumulate; `partial` OK for Probe only)
5. Is `next_best` worse on quality **and** EV? → pass = yes (idea wins).
6. Would I still buy if I could not sell for 5 years? → pass = yes.
7. Am I sizing from MOS + liquidity, not conviction theatre? → pass = yes.
8. Pre-mortem: “It is 2029 and this lost 40%. The reason was: ____.” If that reason is already visible in filings → **fail** (do not buy).

## J. BUY-WHEN checklist (anti-paralysis)

Before defaulting to waiting-room, run this. If all true, prefer an equity label over cash:

1. Moat / quality not hard-failed; earning power underwritable.
2. Balance sheet can survive the mispricing (local recession).
3. Price in **good / very-good** **or** sale-off `true` / `moderately attractive`.
4. Bear loss acceptable; `p_ruin` not dominating EV when sizing.
5. Competence ≠ `cannot` (partial → Probe only).
6. Vs hurdle: `excess_vs_rf_bp` clearly positive (index excess per §B rules, including 2-sigma index handling).

If (1–4) hold but (5) or (6) soft-cap: output **Probe** or **Watch wait for price** with zones — that is a **successful** equity result. Only if (1–3) fail across the universe is BUY=0 correct (then ballast / waiting-room + NOTIFY hooks on the Watch list).

