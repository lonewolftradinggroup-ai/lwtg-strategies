# QC Signals — Community Settings from Discord

Community-shared QCS configurations. These are **not formally validated presets** — they are shared by members for reference and discussion only.

> ⚠️ These configs have not been reviewed or endorsed by @LoneWolfTradingGroup. Do your own validation before running any of these live. Minimum 50 backtest trades before drawing conclusions.

**Last updated:** 2026-08-06

---

## Master Settings Table

Sorted by Win Rate descending. Click a contributor name to jump to their full section.

| Contributor | Ticker | TF | SL | TP | Session | Trades | WR | PF | Net % |
|---|---|---|---|---|---|---|---|---|---|
| [@Ferousity](#ferousity) | MNQ | 4m + 5m | ATR | ATR | Hybrid Asia/London/NYSE | 313 | 83.7% | 2.405 | — |
| [@LoneWolfTradingGroup](#lonewolftradinggroup) | MNQ | 4m | Aaron default | Aaron default | Asia only 17:15–01:59 CT | TBC | TBC | TBC | TBC |
| [@LoneWolfTradingGroup](#lonewolftradinggroup) | MNQ | 5m | Aaron default | Aaron default | London + NYSE | TBC | TBC | TBC | TBC |
| [@LoneWolfTradingGroup](#lonewolftradinggroup) | MNQ | 415m | Aaron default | Aaron default | London + NYSE | TBC | TBC | TBC | TBC |
| [@LoneWolfTradingGroup](#lonewolftradinggroup) | MES | 5m | Aaron default | Aaron default | London + NYSE | TBC | TBC | TBC | TBC |

> ⚠️ QCS SL/TP params are Aaron's proprietary presets — not published here.
> Session filters are the primary tuning lever available to community members.

---

## @Ferousity

> Data nerd. Ran Claude-assisted session window analysis on QCS and published results to community Jul 27, 2026.

**Hybrid Session Approach — 313 trades, 83.7% WR, PF 2.405, Sharpe 10.27**

| Window | Chart | Session (ET) | Session (CT) | Trades | WR | PF | Net/mo |
|---|---|---|---|---|---|---|---|
| Asia | 4m | 18:15–02:59 ET | 17:15–01:59 CT | 202 | 81.7% | 2.230 | $578 |
| London | 5m | 06:00–08:59 ET | 05:00–07:59 CT | 28 | 92.9% | 5.070 | $128 |
| NYSE | 5m | 10:00–15:59 ET | 09:00–14:59 CT | 83 | 85.5% | 2.399 | $251 |
| **Combined** | | | | **313** | **83.7%** | **2.405** | **$957** |

**Per-hour breakdown highlights (ET):**

| Hour | Session | WR | PF | Net/mo |
|---|---|---|---|---|
| 06:00 | London | 100% | ∞ | $55 |
| 07:00 | London | 100% | ∞ | $37 |
| 20:00 | Asia | 90.9% | 5.000 | $102 |
| 12:00 | NYSE | 90.0% | 3.510 | $39 |
| 14:00 | NYSE | 100% | ∞ | $37 |

**Blocked windows (off between sessions):**
- 03:00–05:59 ET / 02:00–04:59 CT — pre-European open
- 09:00–09:59 ET / 08:00–08:59 CT — opening hour noise
- 16:00–18:14 ET / 15:00–17:14 CT — post-close chop

**Configuration:**
- Instrument: MNQ
- Contracts: 2
- Force-flat when window ends: ON
- Opening hour 09:00–09:59 ET excluded (session starts at 10:00 ET)
- Sat excluded

**365-day backtest:** +$4,102 total PnL, 81.68% WR, PF 2.177, max DD $585

| Date Added | Notes |
|---|---|
| 2026-07-27 | MNQ hybrid 4m/5m, 313 trades, 8.5 months validated |
| 2026-08-06 | Per-hour breakdown added from Week 2 community report |

**Split-Use Philosophy — Two Charts, Two Sessions, One Strategy**

Ferousity's key insight is that QCS performs differently across market sessions — the Asia session favors the 4m chart while London and NYSE favor the 5m chart. Rather than running one chart 24/5 with a single config, he runs two separate QCS presets in parallel:

| Chart | TF | Active Session | Rationale |
|---|---|---|---|
| Chart 1 | 4m | Asia (17:15–01:59 CT) | 4m signals better suited to slower overnight Asian session price action |
| Chart 2 | 5m | London + NYSE (05:00–14:59 CT) | 5m signals better suited to faster European and US session volatility |

**Key rules:**
- Each chart has its own session window — they never overlap
- Force-flat ON for both — no positions carry into the dead windows
- The gap 02:00–04:59 CT is intentionally dark — pre-European open is noise
- The opening hour 08:00–08:59 CT is excluded — NYSE open spike risk
- Sat excluded on both charts — thin liquidity

**Why it works:** Rather than fighting the market with the wrong timeframe at the wrong time, each chart is tuned to its session characteristics. The result is a higher combined WR (83.7%) than either chart achieves alone in a 24/5 run.

---

## @LoneWolfTradingGroup

### Current Settings (Aug 6, 2026)

> ⚠️ Session windows adopted from Ferousity's hybrid approach Aug 6 2026.
> SL/TP are Aaron's proprietary QCS preset defaults — not published.
> All configs are LIVE on prop firm accounts.

**Session Architecture — Hybrid 4m Asia / 5m London+NYSE**

| Preset | TF | Contracts | Session 1 CT | Session 2 CT | Blocked CT | Force-Flat | Status |
|---|---|---|---|---|---|---|---|
| MNQ-4m | 4m | 2 | 17:15–01:59 (Asia) | — | 02:00–04:59, 15:00–17:14 | ON | Live |
| MNQ-5m | 5m | 2 | 05:00–07:59 (London) | 09:00–14:59 (NYSE) | 02:00–04:59, 08:00–08:59, 15:00–17:14 | ON | Live |
| MNQ-415m | 415m | 2 | 05:00–07:59 (London) | 09:00–14:59 (NYSE) | 02:00–04:59, 08:00–08:59, 15:00–17:14 | ON | Live |
| MES-5m | 5m | 3 | 05:00–07:59 (London) | 09:00–14:59 (NYSE) | 02:00–04:59, 08:00–08:59, 15:00–17:14 | ON | Live — Watch |

**Notes:**
- MNQ-4m runs Asia session only — hands off to MNQ-5m at 05:00 CT
- MNQ-5m picks up London open and runs through NYSE close
- MNQ-415m mirrors 5m session windows (different TF, same hours)
- MES-5m — red across all TFs, running to Oct 1 refit for evaluation
- Session design based on Ferousity's 313-trade community analysis
- Oct 1 refit will evaluate whether MES-5m should be retired

**Live Performance (week of Aug 2–6, 2026):**

| Preset | Week Trades | WR | Net P&L |
|---|---|---|---|
| MNQ-4m | TBC | TBC | TBC |
| MNQ-5m | TBC | TBC | TBC |
| MNQ-415m | TBC | TBC | TBC |
| MES-5m | TBC | TBC | TBC |

> Session filters applied Aug 6 — live data accumulating. Update at weekend debrief.

| Date Updated | Notes |
|---|---|
| 2026-08-06 | Session windows applied, Ferousity hybrid approach adopted, contracts 2ct MNQ / 3ct MES |

---

*Not financial advice. Community-shared configs are for reference only.*
