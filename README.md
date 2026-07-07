# QuantForge Pine Script Portfolio

Original TradingView Pine Script v6 demos. Written to showcase engineering
practices: confirmed-bar logic (no repainting), realistic commission and
slippage in every backtest, explicit risk management, and honest reporting
of where each approach works and where it does not.

## Scripts

### VWAP Reversion Bands (vwap_reversion_bands_v3.pine)
Anchored VWAP with standard deviation bands. Long-only dip-buying engine:
EMA trend filter, short-length RSI confluence, mean-touch exit, time stop,
catastrophic ATR stop. Tested on SPY 1h, Jan 2023 to Jul 2026, with 0.05%
commission and 2 ticks slippage per side.

### ATR Breakout Channel (atr_breakout_channel_v1.pine)
Donchian-style breakout with an EMA trend gate and a ratcheting
chandelier ATR trailing stop. Risk is frozen at entry and the stop
only tightens, never loosens. Tested on BTCUSDT 4h, Jan 2024 to Jul
2026, with 0.05% commission and 2 ticks slippage per side. The same
engine tested flat-to-negative on SPY 1h over the same period: gap-
prone session charts are poor terrain for breakout systems, and we
report that rather than hide it.

### Multi-Condition Alert Manager (multi_condition_alert_manager_v1.pine)
Utility indicator that unifies EMA cross, price level, and RSI alerts
behind a single "Any alert() function call" alert, designed to emit
webhook-ready JSON payloads on confirmed bars only (payload format
validated externally). Includes an on-chart status table showing which
modules are armed. JSON is built by string concatenation because
str.format treats braces as placeholder syntax and fails at runtime on
JSON-shaped strings.

Nothing in this repository is financial advice. These are programming
demonstrations. Trading involves substantial risk of loss.
