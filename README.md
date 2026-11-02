# Investing Behavior Dataset (synthetic, for practice)

**All data here is made up.** It is built to feel realistic, but it is not real market data or real people.
Use it for learning and practice. For a portfolio piece, swap in real data later (see bottom).

## Tables

| File | Rows | What it is |
|---|---|---|
| `investors.csv` | 250 | One row per investor |
| `assets.csv` | 12 | One row per asset (ETFs and crypto) |
| `prices.csv` | 840 | Monthly closing price per asset, Jan 2021 to Oct 2026 |
| `trades.csv` | ~4,500 | Every buy/sell, linking investors to assets |

## Columns

**investors**: `investor_id, age_group, income_bracket, region, risk_profile, joined_date`
**assets**: `asset_id, ticker, name, asset_class, region, risk_level` (1 = low, 5 = high)
**prices**: `price_date, asset_id, close_price_usd`
**trades**: `trade_id, investor_id, asset_id, trade_date, trade_type, amount_php, units`

## How they connect

- `trades.investor_id` -> `investors.investor_id`
- `trades.asset_id` -> `assets.asset_id`
- `prices.asset_id` -> `assets.asset_id`

## Data quality issues to find and fix (no hints on counts)

- Duplicate rows
- Missing values
- Inconsistent text casing
- Suspicious outlier amounts

## Starter questions

1. Which asset class gets the most money, and does that change by `risk_profile`?
2. Which `age_group` invests the most per trade on average?
3. How does total monthly money flow (buys minus sells) change over time?
4. Which assets have the most buyers vs the most sellers?
5. Do higher-income investors take more risk (look at `risk_level` of what they buy)?
6. Which region has the most active investors?
7. Window functions: rank investors by total invested within each risk profile.
8. Price history: which asset had the best and worst return from Jan 2021 to Oct 2026?

## Swapping in real data later

Real data makes a stronger portfolio. Options: your own transaction history (remove account numbers, API keys and personal details before committing), or public price data such as Kaggle stock/crypto datasets. Keep the same table structure and your queries still work.
