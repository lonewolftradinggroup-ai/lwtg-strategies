# QC Trend — Community Settings from Discord

Community-shared QCT configurations. These are **not formally validated presets** — they are shared by members for reference and discussion only.

> ⚠️ These configs have not been reviewed or endorsed by @LoneWolfTradingGroup. Do your own validation before running any of these live. Minimum 50 backtest trades before drawing conclusions.

**Last updated:** 2026-07-27

---

## Settings Table

| Rank | Ticker | TF | SL | TP | B/E | Days | Trades | WR | PF | Net % | Contributor |
|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | MCL | 3m | ATR 2.9 | ATR 1.2 | OFF | Sun–Fri | 132 | 79.5% | 1.72 | 10.10% | @ChicagoSid |
| 2 | SIL | 15m | OFF | ATR 0.7 | 75% of TP | Sun–Fri | 26 | 100% | MAX | 8.00% | @ChicagoSid |
| 3 | MNQ | 3m | 91pts or OFF | 20.5pts | OFF | Sun–Fri | 72 | 93.1% | 3.36 | 3.30% | @ChicagoSid |
| 4 | MYM | 5m | ATR 2.9 or OFF | ATR 1.2 | OFF | Sun–Fri | 74 | 87.8% | 2.34 | 2.80% | @ChicagoSid |
| 5 | MGC | 9m | 28.5pts or OFF | 2.5pts | OFF | Sun–Fri | 47 | 97.9% | 5.26 | 2.30% | @ChicagoSid |
| 6 | MES | 5m | ATR 5.4 or OFF | ATR 0.7 | OFF | Sun–Fri | 70 | 92.9% | 2.7 | 2.00% | @ChicagoSid |

**Sample period:** 30 days

---

## Notes

- **SIL** — SL is OFF, B/E set to 75% of TP. No hard stop — position exits at breakeven trigger or TP. 100% WR / MAX PF on 26 trades is a very small sample; treat with caution.
- **MCL** — Micro Crude Light. Not currently in the LWTG instrument stack. Tick value and margin requirements differ — verify before running.
- **MNQ** — Fixed point SL (91pts) rather than ATR. Different approach from LWTG standard config.
- **MGC** — 9m timeframe, fixed point SL/TP. Compare to LWTG MGC-5m config.
- All configs ranked by Net % over 30-day sample. All Sat excluded from day filter.

---

## Contributor Log

| Contributor | Date Added | Notes |
|---|---|---|
| @ChicagoSid | 2026-07-27 | 6 tickers, 30-day sample, ranked by Net % |

---

*Not financial advice. Community-shared configs are for reference only.*

---

## @Dryeyel / @Jim Settings

| Field | Value |
|---|---|
| SL | ATR 4.0 |
| TP | ATR 1.0 |
| Trailing Stop (ATR) | 6.0 ✅ |
| Time Filter | 16:15 – 15:30 Europe/? TZ (full timezone not visible) |
| Day Filter | Mon / Tue / Wed / Thu (Fri/Sat/Sun excluded — day filter disabled but days checked) |
| Contracts | 3 |
| Exit on Flip | OFF |
| Breakeven | Off |
| Trigger at % TP | 50 |
| Trigger at R multiple | 1 |
| Max Trades Per Day | 5 |
| Daily Loss Limit ($) | 500 |
| Ticker | MGC (2m) |

**Notes:** Trailing stop active at ATR 6.0 — wider trail than SL. Time filter suggests European session focus. Daily loss limit and max trades per day both set — more conservative risk management than standard config.

## @Dryeyel / @Jim — Trailing Stop Comparison

| Config | Trades | WR | PF | Net % |
|---|---|---|---|---|
| With trailing stop ATR 6 ✅ | 153 | 86.3% | 1.72 | 3.9% |
| Without trailing stop | 153 | 86.3% | 1.55 | 3.4% |

Period: Jul 3 – Jul 24, 2026. Trailing stop adds +0.5% net / +0.17 PF — keep it on.

| Contributor | Date Added | Notes |
|---|---|---|
| @Dryeyel / @Jim | 2026-07-27 | MGC 2m, European TZ, trailing stop active, 3 contracts, day filter off |

---

## @VettiTrader Settings

| Field | Value |
|---|---|
| Ticker | MNQ (4m) |
| Contracts | 5 |
| Time Filter | 21:00–13:30 Europe/? TZ ✅ |
| Day Filter | Disabled (Mon–Fri active, Sat/Sun excluded) |
| Breakeven | At R multiple — trigger 50% to TP, R multiple 1 |
| Exit on Flip | OFF |
| Max Trades/Day | 2 (disabled) |
| Daily Loss Limit | $850 (disabled) |
| Ghost | Enabled |

**SL/TP not visible in screenshots — to be confirmed.**

## @VettiTrader — Performance

| Period | Trades | WR | PF | Net % |
|---|---|---|---|---|
| May 4 – Jul 24, 2026 | 236 | 92.4% | 2.3 | 8.5% |

**Notes:** Strongest result in the community doc so far — 92.4% WR on 236 trades is a meaningful sample. Time filter covering overnight into early European session suggests edge in low-liquidity trending conditions on MNQ. Breakeven active at 1R — likely contributing to the high WR by protecting winners. SL/TP params needed to complete the picture.

| Contributor | Date Added | Notes |
|---|---|---|
| @VettiTrader | 2026-07-27 | MNQ 4m, European TZ, 236 trades, SL/TP unknown |
