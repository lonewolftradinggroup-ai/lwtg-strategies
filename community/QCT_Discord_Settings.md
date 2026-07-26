# QC Trend — Community Settings from Discord

Community-shared QCT configurations. These are **not formally validated presets** — they are shared by members for reference and discussion only.

> ⚠️ These configs have not been reviewed or endorsed by @LoneWolfTradingGroup. Do your own validation before running any of these live. Minimum 50 backtest trades before drawing conclusions.

**Last updated:** 2026-07-27

---

## Master Settings Table

Sorted by Win Rate descending. Click a contributor name to jump to their full section.

| Contributor | Ticker | TF | SL | TP | B/E | Trades | WR | PF | Net % |
|---|---|---|---|---|---|---|---|---|---|
| [@VettiTrader](#vettitrader) | MNQ | 4m | TBC | TBC | At 1R (50% TP) | 236 | 92.4% | 2.30 | 8.5% |
| [@ChicagoSid](#chicagosid) | MGC | 9m | 28.5pts | 2.5pts | OFF | 47 | 97.9% | 5.26 | 2.3% |
| [@ChicagoSid](#chicagosid) | MNQ | 3m | 91pts | 20.5pts | OFF | 72 | 93.1% | 3.36 | 3.3% |
| [@ChicagoSid](#chicagosid) | MES | 5m | ATR 5.4 | ATR 0.7 | OFF | 70 | 92.9% | 2.70 | 2.0% |
| [@Dryeyel / @Jim](#dryeyel--jim) | MGC | 2m | ATR 4.0 | ATR 1.0 | OFF | 153 | 86.3% | 1.72 | 3.9% |
| [@ChicagoSid](#chicagosid) | MYM | 5m | ATR 2.9 | ATR 1.2 | OFF | 74 | 87.8% | 2.34 | 2.8% |
| [@ChicagoSid](#chicagosid) | MCL | 3m | ATR 2.9 | ATR 1.2 | OFF | 132 | 79.5% | 1.72 | 10.1% |
| [@ChicagoSid](#chicagosid) | SIL | 15m | OFF | ATR 0.7 | 75% of TP | 26 | 100% | MAX | 8.0% |

> ⚠️ SIL has no hard SL — treat 100% WR / MAX PF with extreme caution at 26 trades.  
> All ChicagoSid configs: 30-day sample, Sun–Fri day filter, Sat excluded.

---

## @ChicagoSid

| Rank | Ticker | TF | SL | TP | B/E | Days | Trades | WR | PF | Net % |
|---|---|---|---|---|---|---|---|---|---|---|---|
| 1 | MCL | 3m | ATR 2.9 | ATR 1.2 | OFF | Sun–Fri | 132 | 79.5% | 1.72 | 10.10% |
| 2 | SIL | 15m | OFF | ATR 0.7 | 75% of TP | Sun–Fri | 26 | 100% | MAX | 8.00% |
| 3 | MNQ | 3m | 91pts or OFF | 20.5pts | OFF | Sun–Fri | 72 | 93.1% | 3.36 | 3.30% |
| 4 | MYM | 5m | ATR 2.9 or OFF | ATR 1.2 | OFF | Sun–Fri | 74 | 87.8% | 2.34 | 2.80% |
| 5 | MGC | 9m | 28.5pts or OFF | 2.5pts | OFF | Sun–Fri | 47 | 97.9% | 5.26 | 2.30% |
| 6 | MES | 5m | ATR 5.4 or OFF | ATR 0.7 | OFF | Sun–Fri | 70 | 92.9% | 2.70 | 2.00% |

**Sample period:** 30 days

**Notes:**
- **SIL** — No hard SL, B/E at 75% of TP. 26-trade sample is too small to draw conclusions.
- **MCL** — Micro Crude Light, not in the LWTG stack. Verify tick value and margin before running.
- **MNQ** — Fixed point SL (91pts) rather than ATR. Different from LWTG standard.
- **MGC** — 9m timeframe, fixed point SL/TP. Compare to LWTG MGC-5m and Dryeyel MGC-2m configs.

| Date Added | Notes |
|---|---|
| 2026-07-27 | 6 tickers, 30-day sample, ranked by Net % |

---

## @Dryeyel / @Jim

| Field | Value |
|---|---|
| Ticker | MGC (2m) |
| SL | ATR 4.0 |
| TP | ATR 1.0 |
| Trailing Stop (ATR) | 6.0 ✅ |
| Time Filter | 16:15–15:30 Europe/? TZ (full timezone TBC) |
| Day Filter | Disabled (Mon–Thu active, Fri/Sat/Sun excluded) |
| Contracts | 3 |
| Breakeven | OFF |
| Exit on Flip | OFF |
| Max Trades Per Day | 5 |
| Daily Loss Limit ($) | 500 |

**Trailing Stop Comparison:**

| Config | Trades | WR | PF | Net % |
|---|---|---|---|---|
| With trailing stop ATR 6 ✅ | 153 | 86.3% | 1.72 | 3.9% |
| Without trailing stop | 153 | 86.3% | 1.55 | 3.4% |

Period: Jul 3 – Jul 24, 2026. Trailing stop adds +0.5% net / +0.17 PF — keep it on.

**Notes:** Timezone not fully visible — Europe/London vs Europe/Berlin changes session window. To be confirmed.

| Date Added | Notes |
|---|---|
| 2026-07-27 | MGC 2m, European TZ, trailing stop active, 3 contracts |

---

## @VettiTrader

| Field | Value |
|---|---|
| Ticker | MNQ (4m) |
| SL | TBC |
| TP | TBC |
| Contracts | 5 |
| Time Filter | 21:00–13:30 Europe/? TZ ✅ |
| Day Filter | Disabled (Mon–Fri active, Sat/Sun excluded) |
| Breakeven | At R multiple — trigger 50% to TP, R multiple 1 |
| Exit on Flip | OFF |
| Max Trades/Day | 2 (disabled) |
| Daily Loss Limit | $850 (disabled) |
| Ghost | Enabled |

**Performance:**

| Period | Trades | WR | PF | Net % |
|---|---|---|---|---|
| May 4 – Jul 24, 2026 | 236 | 92.4% | 2.30 | 8.5% |

**Notes:** Strongest result in the community doc — 236 trades at 92.4% WR is a meaningful sample. Breakeven at 1R is likely contributing to the high WR by protecting winners early. Time filter covers overnight into early European session, suggesting edge in low-liquidity trending conditions on MNQ. SL/TP params still needed.

| Date Added | Notes |
|---|---|
| 2026-07-27 | MNQ 4m, European TZ, 236 trades, SL/TP TBC |

---

*Not financial advice. Community-shared configs are for reference only.*
