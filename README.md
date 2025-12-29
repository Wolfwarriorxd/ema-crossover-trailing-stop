# EMA Crossover Strategy with Trailing Stop

This repository contains a Python-based implementation of a simple rule-based trading strategy developed as part of an internship assignment.

The objective of the assignment was to design, implement, and evaluate a trading strategy based on moving average crossovers with a trailing stop-loss mechanism, using historical market data.

---

## Strategy Description

The strategy follows two straightforward rules:

1. **Buy Signal**
   - A buy trade is triggered when the 10-period Exponential Moving Average (EMA) crosses above the 50-period EMA.

2. **Sell Signal**
   - A sell trade is triggered when the 10-period EMA crosses below the 50-period EMA.

Once a trade is entered, it is managed using a **trailing stop-loss**. The position is exited only when the trailing stop is hit. No exit is taken on reverse signals.

To make the trailing stop adaptive to market conditions, the stop-loss distance is based on the **Average True Range (ATR)** rather than a fixed number of pips.

---

## Data Source

- Instrument: **EURUSD**
- Timeframe: **1 Hour (H1)**
- Data source: **MetaTrader 5 Python API**
- Period: 2019 to present

Historical price data is downloaded directly from the MetaTrader 5 terminal to ensure consistency with broker data and avoid data mismatch issues.

---

## Implementation Details

- Indicators used:
  - EMA (10)
  - EMA (50)
  - ATR (14)
- Only one position is allowed at a time (long, short, or flat).
- The strategy is backtested using a simple bar-by-bar simulation.
- No transaction costs or slippage are included, as the focus is on strategy logic rather than execution optimization.

---

## Results Summary

The strategy was evaluated using basic performance metrics such as:
- Number of trades
- Win rate
- Average profit and loss per trade
- Cumulative profit and loss (equity curve)

The results show that while the strategy captures trends during directional markets, it tends to underperform during sideways or low-momentum periods. This behavior is typical for moving-average-based trend-following strategies.

The purpose of this exercise was to ensure correctness, clarity of logic, and proper evaluation rather than to optimize for profitability.

---

## Repository Structure
ema-crossover-trailing-stop/
│
├── notebook/ # Jupyter notebook with full implementation
├── data/ # Historical EURUSD price data (CSV)
├── README.md
└── requirements.txt

pip install -r requirements.txt

3. Open the Jupyter notebook in the `notebook/` directory and run the cells sequentially.

---

## Notes

This project is intended for educational and evaluation purposes only and should not be considered financial advice or a production-ready trading system.
****
