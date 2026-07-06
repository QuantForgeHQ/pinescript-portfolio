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

Nothing in this repository is financial advice. These are programming
demonstrations. Trading involves substantial risk of loss.
