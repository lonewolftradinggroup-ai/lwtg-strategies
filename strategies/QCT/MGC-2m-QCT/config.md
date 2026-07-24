# MGC-2m-QCT

## Configuration

| Field | Value |
|---|---|
| Preset | MGC-2m-QCT |
| Strategy | QC Trend |
| Instrument | MGC (Micro Gold) |
| Timeframe | 2m |
| Contracts | 3 |
| Stop Loss | % 0.8 |
| Take Profit | ATR 2.3 |
| Block Windows | None |
| Submitted By | @LoneWolfTradingGroup |
| Verified By | @LoneWolfTradingGroup |
| Status | 📄 Paper |
| Paper Since | 2026-07-23 |
| Live Since | — |

## Notes

- **Percent stop required** — ATR stops do not work well on MGC due to gold's volatility profile. Always use price-relative (%) stop on this instrument.
- TP remains ATR-based
- Config locked 2026-07-23 after sweep validation

## Sweep Validation (2026-07-03 to 2026-07-23)

| Param | Swept Values | Selected |
|---|---|---|
| Take Profit | ATR 1.0 / 1.5 / 2.0 / **2.3** / 2.5 / 3.0 | ATR 2.3 (peak PF) |
| Stop Loss | 0.5% / 0.6% / 0.7% / **0.8%** / 1.0% / 1.2% | 0.8% (peak PF) |

Backtest: 146 trades, 72.6% WR, PF 1.82, 7.9% Net %

## Version History

| Date | Change |
|---|---|
| 2026-07-23 | Config locked post-sweep. Paper trading started. |
