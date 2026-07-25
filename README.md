# Quant Crawler Community — Strategy Library

**Powered by LWTG 🐺 · Built by the community**

Community-maintained collection of validated strategies, configurations, and results for the LWTG MITS framework.

**Maintained by:** @LoneWolfTradingGroup  
**Last updated:** 2026-07-27

🌐 [Strategy Library](https://lonewolftradinggroup-ai.github.io/lwtg-strategies) | 🏆 [Leaderboard](https://lonewolftradinggroup-ai.github.io/lwtg-strategies/leaderboard.html)

---

## Structure

```
/strategies
  /QCT          ← QC Trend presets
  /QCS          ← QC Signals presets
  /MITS         ← MITS instrument configs
/community
  SUBMISSION_TEMPLATE.md
```

---

## Active Strategies

### QC Trend

| Preset | Instrument | TF | Trades | WR | PF | Net P&L | Status |
|---|---|---|---|---|---|---|---|
| MNQ-4m-QCT | MNQ | 4m | 20 | 75.0% | 1.28 | +$663.00 | 📄 Paper |
| MGC-2m-QCT | MGC | 2m | 3 | 100% | — | +$537.90 | 📄 Paper |
| MYM-5m-QCT | MYM | 5m | 7 | — | — | — | 📄 Paper |

### QC Signals

| Preset | Instrument | TF | Trades | WR | PF | Net P&L | Status |
|---|---|---|---|---|---|---|---|
| MNQ-4m | MNQ | 4m | 7 | 85.7% | 2.67 | +$503.90 | ✅ Active |
| MES-5m | MES | 5m | 7 | 57.1% | 0.62 | -$437.12 | ⚠️ Watch |

### MITS

| Preset | Instrument | TF | Trades | WR | PF | Net P&L | Status |
|---|---|---|---|---|---|---|---|
| MGC-5m | MGC | 5m | 29 | 82.8% | 1.57 | +$576.50 | ✅ Active |
| MES-15m | MES | 15m | 24 | 91.7% | 8.05 | +$1,150.50 | ✅ Active |
| MNQ-15m | MNQ | 15m | 4 | 50.0% | 1.29 | +$91.00 | ✅ Active |
| M2K-15m | M2K | 15m | 54 | 70.4% | 0.69 | -$370.40 | ⚠️ Watch |

---

## Standards

- Minimum **50 backtest trades** to submit a new preset
- Paper results required before any live recommendation
- No TP/SL tuning on live or paper presets with fewer than 50 trades
- Percent stop required for MGC — ATR stops do not suit gold's volatility profile
- Refit cadence: quarterly

---

## Contributing

See [`community/SUBMISSION_TEMPLATE.md`](community/SUBMISSION_TEMPLATE.md).  
Post your completed submission in Discord for review.  
Minimum 50 backtest trades required to appear in the Validated section.

---

*Not financial advice. Past performance does not guarantee future results.*
