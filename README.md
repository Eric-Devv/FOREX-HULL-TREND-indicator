# 📊 Universal HMA Strategy (FX, Crypto, Stocks) — Pine Script v6

A multi-asset Pine Script strategy designed for **trend-following with adaptive stop-loss/take-profit** logic, suited for **Forex**, **Crypto**, and **Stocks**. This system leverages **Hull Moving Averages**, **RSI confirmation**, and **ATR-based volatility management** to create consistent, backtestable signals.

---

## 🚀 Features

### ✅ Strategy Logic
- **Hull MA Crossovers**: Core entry logic based on crossovers of standard and smoothed Hull Moving Averages.
- **Strong Confirmation Filter**: Uses a second HMA pair to confirm trend strength and filter false signals.
- **RSI Filter**: Prevents entries when momentum contradicts the trend (e.g., RSI below 50 for longs).
- **Multi-Timeframe Compatibility**: Works seamlessly from 1-minute charts up to daily timeframes.

### ✅ Risk Management
- **ATR-Based Stop Loss**: Automatically adjusts SL based on current volatility, ensuring scalability across asset classes.
- **Take Profit (TP)**: Dynamically calculated using your desired Risk:Reward ratio.
- **Tick-Size Normalization**: Ensures SL/TP precision across instruments like BTC/USD, AAPL, and EUR/USD.

### ✅ Alerts
- **Entry Alerts**: Triggers when Buy/Sell conditions are met.
- **Stop Loss Alerts**: Informs you when the price hits the SL level.
- **Take Profit Alerts**: Sends an alert when TP is reached.
- **Customizable Webhook Output**: Works great with automation bots.

### ✅ Strategy & Backtesting
- **Built-In Backtest Support**: Uses `strategy.entry` and `strategy.exit` for historical evaluation.
- **Full Performance Metrics**: See win rate, profit factor, drawdown, expectancy, and more.
- **Position Sizing**: Default uses percent-of-equity-based position sizing (customizable).

---

## ⚙️ User Inputs

| Input                | Description                                         |
|---------------------|-----------------------------------------------------|
| `HMA Length`         | Length of the fast Hull MA                         |
| `Strong HMA Length`  | Length of the confirmation Hull MA                 |
| `RSI Length`         | Lookback period for RSI filtering                  |
| `RSI Threshold`      | RSI > threshold to allow longs, < (100-threshold) for shorts |
| `ATR Length`         | Length for ATR-based SL calculation                |
| `ATR Multiplier`     | How far SL is set from entry (in ATRs)             |
| `Risk:Reward Ratio`  | Determines how far TP is set from entry            |

---

## 🧪 Entry Conditions

**Long Entry:**
- Fast HMA crossover upward
- Strong HMA crossover upward
- RSI above threshold

**Short Entry:**
- Fast HMA crossover downward
- Strong HMA crossover downward
- RSI below (100 - threshold)

---

## 🎯 Stop Loss & Take Profit

- **SL (Stop Loss)**: Set `X` ATRs away from entry price.
- **TP (Take Profit)**: Set by multiplying the SL distance by the Risk:Reward Ratio.
- These levels update dynamically based on asset volatility.

---

## 📍 Alerts

| Name             | Trigger Condition                      |
|------------------|----------------------------------------|
| `Long Entry`     | When long entry criteria are met       |
| `Short Entry`    | When short entry criteria are met      |
| `SL Long Hit`    | Price falls to stop loss on long       |
| `TP Long Hit`    | Price rises to take profit on long     |
| `SL Short Hit`   | Price rises to stop loss on short      |
| `TP Short Hit`   | Price falls to take profit on short    |

These alerts support webhook messages (e.g., for bot trading or integrations with Discord, Telegram, Notion, etc).

---

## 📦 Multi-Asset Compatibility

✅ Forex  
✅ Crypto  
✅ Stocks  
✅ Indices  
✅ Commodities

Thanks to ATR/tick-based logic and normalization, this strategy works without any code changes across nearly all TradingView-supported markets.

---

## 📈 Example Chart

_(Insert a screenshot here showing buy/sell signals, SL/TP lines, and backtest performance metrics)_

---

## 🔄 Coming Enhancements

- [ ] Trailing Stop feature
- [ ] Swing High/Low stop loss toggle
- [ ] MTF trend filter
- [ ] Dashboard UI overlay
- [ ] Trade journaling webhook (Notion / Google Sheets export)

---

## 🧠 Author & License

Created with ❤️ using Pine Script v6.  
MIT License — feel free to fork, extend, or integrate with your bot stack.

---

## 🤝 Contribute

Suggestions, PRs, and feature requests are welcome. Let’s make this a reliable base strategy for traders across all markets!

