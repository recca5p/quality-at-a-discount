# Quality-at-a-Discount

Long-term accumulation playbook: high-quality business, hard to replace, **true sale-off**. Valid output is zero names.

Split on purpose so an agent **does not load every market**.

```
SKILL.md                 <- router only (always)
core.md                  <- 10-agent committee, score, output
lenses.md                <- extra investor/institution gates (with core)
sizing.md                <- buy/sell/size/EV, only when recommending action
sectors.md               <- banks / tech / cyclicals / property / brokers
markets/vn.md            <- only if MARKET=VN
markets/us.md            <- only if MARKET=US
markets/uk.md
markets/de.md
markets/au.md
overlays/ai-semis.md     <- only if AI/chip/hyperscaler-capex
overlays/real-assets.md  <- gold/metals/oil, or empty equity screen
.cursor/rules/quality-at-a-discount.mdc
```

## Load graph

| User asks | Read |
|---|---|
| VN stocks | `SKILL.md` → `core.md` → `lenses.md` → `sectors.md` → `markets/vn.md` |
| US stock, not semis | those with `markets/us.md` |
| Buy/sell/size/target | those + `sizing.md` |
| NVDA / TSM / ASML | those + `overlays/ai-semis.md` |
| Gold / oil / empty screen | `overlays/real-assets.md` |

## Grok Bot / Cursor

Type `/Quality-at-a-Discount` or just ask (“screen the US”, “is FPT cheap”, “is NVDA a chip bubble”). The router picks files. Do not paste this repo into chat.

## License

MIT. Not investment advice. Numbers must come from dated filings.

## Related

Same owner, different job. Do not mix this playbook with session LONG/SHORT.

- Codex trading skills (manual advisory, Hybrid M5): https://github.com/recca5p/market-data-acquisition
- Discover both under GitHub topic [`skills`](https://github.com/search?q=topic%3Askills+user%3Arecca5p) on `recca5p`.
