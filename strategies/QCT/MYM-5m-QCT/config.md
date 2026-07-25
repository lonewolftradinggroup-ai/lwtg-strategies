# MYM-5m-QCT

## Configuration

| Field | Value |
|---|---|
| Preset | MYM-5m-QCT |
| Strategy | QC Trend |
| Instrument | MYM (Micro E-mini Dow) |
| Timeframe | 5m |
| Contracts | 7 |
| Stop Loss | ATR 3.0 |
| Take Profit | ATR 1.4 |
| Block Windows | None |
| Day Filter | Mon / Wed / Fri / Sun (Tue & Thu excluded) |
| Submitted By | @LoneWolfTradingGroup |
| Verified By | @LoneWolfTradingGroup |
| Status | 📄 Paper |
| Paper Since | 2026-07-27 |
| Live Since | — |

## Notes

- Day filter is load-bearing — Tue/Thu exclusion materially improves PF (1.38 → 2.36)
- ATR stop works well on MYM — do not switch to percent stop
- Tick value: $0.50/tick
- GAS preset tag: `?preset=MYM-5m-QCT`

## Sweep Validation (2026-06-01 to 2026-07-25)

| Config | Trades | WR | PF | Net % |
|---|---|---|---|---|
| No day filter | 199 | 73.9% | 1.38 | 3.6% |
| Mon/Wed/Thu/Fri/Sun | 160 | 75.0% | 1.46 | 3.3% |
| **Mon/Wed/Fri/Sun (selected)** | **119** | **80.7%** | **2.36** | **5.0%** |
| Mon/Tue/Wed/Fri/Sun | 158 | 77.8% | 1.90 | 5.2% |

Selected: Mon/Wed/Fri/Sun — peak PF at 2.36, strong WR, 119 trades (meaningful sample).

## Version History

| Date | Change |
|---|---|
| 2026-07-27 | Config locked post-sweep. Paper trading started. |
