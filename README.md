# Simple Grid Trading EA

This Expert Advisor (EA) implements a basic grid trading strategy for both buy and sell directions without using any indicators. The logic is based on placing new market orders at a fixed price distance (grid) and closing all orders in one direction when a target total profit is reached.

## Features

- Grid-based Buy and Sell entries
- Closes all Buy or Sell positions when cumulative profit exceeds target
- No martingale or lot multiplier
- Works with any symbol or timeframe

## Inputs

| Parameter             | Description                            |
|-----------------------|----------------------------------------|
| `magic`               | Unique ID to identify EA's orders      |
| `lot_buy`             | Lot size for Buy orders                |
| `grid_buy`            | Price gap (points) between Buy entries |
| `close_profit_buy`    | Profit threshold to close Buy orders   |
| `lot_sell`            | Lot size for Sell orders               |
| `grid_sell`           | Price gap (points) between Sell entries|
| `close_profit_sell`   | Profit threshold to close Sell orders  |

## How It Works

- **Initial Order**: A Buy or Sell order is placed if no orders of that type exist.
- **Grid Entry**: Additional orders are placed if price moves away by the grid distance.
- **Profit Close**: All positions of one type are closed once total profit in that direction exceeds the defined threshold.

## Notes

- Designed for ranging markets.
- Use with caution; no risk management or stop loss included.
