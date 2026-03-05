# Shared Rates and Parameters

> Last verified: 2026-02-21

## SSR Spread

> Source: `src/lib/debt-pnl/constants.ts:17`

| Parameter | Value | Description |
|-----------|-------|-------------|
| `SUSDS_SPREAD_BPS` | 30 | sUSDS spread in basis points (0.30%). Applied as credit to stars holding sUSDS. |

This spread represents the difference between the Base Rate and the Sky Savings Rate (SSR).
Per Atlas A.3.1.2.2.1: SSR = Base Rate - 30bps.

## Fallback Rates

> Source: `src/lib/debt-pnl/calculations/debt-fees.ts:154,166,193`

| Parameter | Value | Description |
|-----------|-------|-------------|
| Fallback SSR | 4.5% annual | Used when no SSR event data is available for a period. Converted via `apyToPerSecondRate(0.045)`. |

> Source: `src/lib/settlement/revenue/utils.ts:4`

| Parameter | Value | Description |
|-----------|-------|-------------|
| `BASE_RATE_PERCENT` | 4.66% | Fallback base rate (SSR + 30bps approximation). Used when all SSR data sources fail. |

> Source: `src/lib/pnl-utils/services/ssr-calculator.ts:17`

| Parameter | Value | Description |
|-----------|-------|-------------|
| `SSR_SPREAD_BPS` | 30 | Duplicate of SUSDS_SPREAD_BPS in pnl-utils module. Same 30bps spread. |

## Borrow Rate Subsidy Program

> Source: `src/lib/debt-pnl/constants.ts:19-22`

| Parameter | Value | Description |
|-----------|-------|-------------|
| `BORROW_RATE_SUBSIDY_START` | 2026-01-01 | Program start date |
| `BORROW_RATE_SUBSIDY_MONTHS` | 24 | Duration in months (Jan 2026 - Dec 2027) |
| `BORROW_RATE_SUBSIDY_CAP_USD` | $1,000,000,000 | Maximum debt eligible for subsidy per star per day |
| `BORROW_RATE_SUBSIDY_ELIGIBLE_STARS` | `['spark', 'grove']` | Stars eligible for subsidy (Obex excluded) |

### Subsidy Formula

```
Subsidized Rate = T-Bill Rate + ((Base Rate - T-Bill Rate) * T / 24)
```

Where T = month counter (1 for Jan 2026, 24 for Dec 2027).

### T-Bill Rate Source

> Source: `src/lib/debt-pnl/calculations/borrow-rate-subsidy.ts:32-34`

| Parameter | Value | Description |
|-----------|-------|-------------|
| T-Bill API | US Treasury XML feed | `https://home.treasury.gov/resource-center/data-chart-center/interest-rates/pages/xml?data=daily_treasury_yield_curve&field_tdr_date_value={year}` |
| T-Bill Field | `BC_3MONTH` | 3-month Treasury Bill rate |
| Lookback Window | 10 days | Maximum days to look back for rate data on weekends/holidays |

## Time Constants

> Source: `src/lib/debt-pnl/calculations/debt-fees.ts:14-16` (repeated across calculation files)

| Parameter | Value | Description |
|-----------|-------|-------------|
| `SECONDS_PER_YEAR` | 31,536,000 | Used for annualized rate conversions |
| `SECONDS_PER_DAY` | 86,400 | Used for daily calculations |
| `RAY` | 1e27 | Ethereum Ray unit for SSR per-second rate conversion |

## Rate Hierarchy (from Methodology)

| Rate | Formula | Reference |
|------|---------|-----------|
| Sky Savings Rate (SSR) | Base Rate - 0.30% | Atlas A.3.1.2.2.1 |
| Agent Rate | Base Rate - 0.10% | Atlas A.3.1.2.3.1 |
| Agent Credit Line Borrow Rate | = Base Rate (default) | Atlas A.3.1.2.5.1 |
| Distribution Reward Fee | 0.20% (20bps of the 30bps spread) | Atlas A.2.9.2.2.2.3.1 |
| Sky Spread | 0.10% (10bps of the 30bps spread) | Atlas A.2.9.2.2.2.3.3 |

**Note**: The methodology specifies Agent Rate (Base Rate - 10bps) for idle stablecoin reimbursements, but the code currently uses the full Base Rate. This is a known divergence.
