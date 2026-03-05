# [Star Name] - Business Parameters

> Last verified: YYYY-MM-DD

## PnL Calculation Modules

| Module | Enabled | Notes |
|--------|---------|-------|
| Step 1: Max Debt Fees | Yes/No | TWA Debt x Base Rate |
| Step 2: Idle Stablecoins | Yes/No | |
| Step 3: sUSDS Profit | Yes/No | 30bps spread credit |
| PSM3 Idle | Yes/No | USDS in PSM3 |
| PSM3 sUSDS | Yes/No | sUSDS in PSM3 |
| Step 4: Sky Direct Exposure | Yes/No | |
| Borrow Rate Subsidy | Yes/No | |

## Borrow Rate Subsidy

| Parameter | Value |
|-----------|-------|
| Eligible | Yes/No |
| Cap | $1,000,000,000 per day (if eligible) |

## Asset Caps (if applicable)

| Asset | Cap | Effect |
|-------|-----|--------|
| | | |

## One-Time Revenue Adjustments (if applicable)

| Month | Address | Amount | Description |
|-------|---------|--------|-------------|
| | | | |

## Settlement Formula

```
Net Amount = Maximum Debt Fees
           - Idle Stablecoin Reimbursement (if enabled)
           - sUSDS Profit (if enabled)
           - PSM3 Idle (if enabled)
           - PSM3 sUSDS (if enabled)
           - Sky Direct Exposure Adjustment (if enabled)
           - Borrow Rate Subsidy (if eligible)
```
