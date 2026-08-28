# Sizing, expected value, buy/sell (load only when recommending an action)

Load this **after** `core.md` + `lenses.md` when you will say buy, add, trim, sell, size, or a “target.” Skip on a pure Watch write-up with no action.

Professionals (CFA Challenge, sell-side) use a target price as a **communication device**. It is model-sensitive and a **bad final sell trigger** (Orbis; Dodge & Cox 3–5y owner horizon). This skill emits **expected value with probabilities**, not one TP.

## 1. Expected value (required)

State three scenarios with probabilities that sum to 1. Use **real** returns in the spending currency (usually VND):

| Scenario | Prob | Price / IV | 3–5y real total return |
|---|---|---|---|
| Bear | p_b | | |
| Base | p_base | | |
| Bull | p_u | | |

`EV_price = p_b·bear + p_base·base + p_u·bull`  
`EV_return` = probability-weighted 3–5y real return  
`p_ruin` = probability of permanent >30% real loss (thesis dead, not a quote dip)

Do **not** print a single target price. If the user asks for one, give `EV_price` and the band, and say it is not a sell trigger.

Haircut `p_base` by a **base rate**: what happened to similar names (same sector, same cycle, same quality) over 10–20 years. If you cannot name a base rate, cut expected growth. UNKNOWN is allowed; fake precision is not.

## 2. Hurdles already computed in `lenses.md`

Repeat in the action block: `excess_vs_rf_bp`, `excess_vs_index_bp`, `next_best`, competence.  
Accumulate requires competence=`full`, `excess_vs_index_bp` ≥ **+200**, behavior gate all-yes, and `p_ruin` not dominating EV.

## 3. Position caps (take the **min**)

| Cap | Default |
|---|---|
| Probe | **2%** of equity book |
| Tactical / cyclical | **6%** |
| Core quality, MOS intact | **10%** |
| Single-name liquidity | max 10 days of ADV to exit |
| Factor / country / Vin-or-Mag7 cluster | **15%** combined in one factor |
| Related names (same owner, same commodity) | treat as one risk |

**¼ Kelly** as a ceiling, not a target: if you can underwrite a probability-weighted edge, `kelly_frac ≈ edge / odds`, then `size_rec = min(caps, 0.25 × kelly_frac)`. If you cannot underwrite probabilities, **ignore Kelly** and use Probe 2%.

First ticket ≤ **40%** of `size_rec`. Scale in only inside the **good / very-good** zone from `core.md`. Do not average down in fair/expensive, or when a thesis breaker has printed.

## 4. Add / trim / sell taxonomy

Use the `core.md` price zones. Then:

| Action | When |
|---|---|
| **Do not buy** | Any hard-fail; competence `cannot`; behavior gate fail; `excess_vs_index_bp` < +200 |
| **Probe** | Partial competence or MOS thin; 2% cap; wait for next print if a number is UNKNOWN and material |
| **Accumulate** | Full competence, true sale-off or moderately attractive, EV skewed up, zones good/very-good |
| **Add** | Still in good/very-good **and** thesis intact **and** below `size_rec` |
| **Hold no add** | Fair zone, or MOS gone but fortress compounder (Buffett: do not sell See’s because someone offers a high quote) |
| **Trim** | Expensive zone **and** not a forever compounder; or position > cap; or `next_best` is clearly better |
| **Sell** | Thesis dead (moat, cash, governance, or AI-overlay breaker); or MOS gone on a non-fortress; or original analysis was wrong. **Sell at a loss** if thesis dies (Orbis). Late-Graham +50%/2-year rule is for cigar-butt baskets, **not** for accumulation compounders |
| **Never sell for the quote** | Volatility is not a thesis breaker (`core.md` sale-off test) |

Invalidation (write at t0): the **numeric** breakers from output item 10. If two fire, sell — do not “wait for the average.”

## 5. Time

The 1–2 year floor means: do not buy money you need inside 24 months. The **underwriting** horizon is 3–5y (Dodge & Cox) to 10y (Buffett circle). A 12-month price target is not a process.

## 6. Action block (append to the 11-point output)

- competence, behavior-gate pass/fail, pre-mortem one line
- `rf`, `cpi`, `index_er`, `idea_er`, `excess_vs_rf_bp`, `excess_vs_index_bp`, `next_best`
- scenario table + `EV_price` + `EV_return` + `p_ruin` (no single TP)
- `size_rec`, first ticket, caps that bound it
- add / do-not-average-down / trim / sell / invalidation
- what you are **not** copying from institutions (TE, closet index, forced sector weights)
