# MNQ-4m-QCT

## Configuration

| Field | Value |
|---|---|
| Preset | MNQ-4m-QCT |
| Strategy | QC Trend |
| Instrument | MNQ (Micro E-mini Nasdaq-100) |
| Timeframe | 4m |
| Contracts | 3 |
| Stop Loss | ATR 3.1 |
| Take Profit | ATR 1.35 |
| Block Windows | None |
| Submitted By | @LoneWolfTradingGroup |
| Verified By | @LoneWolfTradingGroup |
| Status | 📄 Paper |
| Paper Since | 2026-07-21 |
| Live Since | — |

## Notes

- ATR-based stops work well on MNQ given its volatility profile
- No session block — trades across all sessions
- Do not tune TP/SL before 50-trade sample is reached

## Version History

| Date | Change |
|---|---|
| 2026-07-21 | Initial config — paper trading started |
