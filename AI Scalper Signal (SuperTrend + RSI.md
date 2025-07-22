# Code_XAUUSD
// This Pine Script® code is subject to the terms of the Mozilla Public License 2.0 at https://mozilla.org/MPL/2.0/
// © okoloRomiz

//@version=6
indicator("AI Scalper Signal (SuperTrend + RSI)", overlay=true)

// === SuperTrend ===
atrPeriod = input.int(10, title="ATR Period")
factor = input.float(3.0, title="Multiplier")
[supertrend, direction] = ta.supertrend(factor, atrPeriod)
…
// === Shapes
plotshape(buySignal, title="BUY Signal", location=location.belowbar, color=color.green, style=shape.triangleup, size=size.small)
plotshape(sellSignal, title="SELL Signal", location=location.abovebar, color=color.red, style=shape.triangledown, size=size.small)

// === Alerts
alertcondition(buySignal, title="BUY Alert", message="Buy Signal")
alertcondition(sellSignal, title="SELL Alert", message="Sell Signal")
