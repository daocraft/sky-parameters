# Grove - Business Parameters

> Last verified: 2026-02-21

## PnL Calculation Modules

| Module | Enabled | Notes |
|--------|---------|-------|
| Step 1: Max Debt Fees | Yes | TWA Debt x Base Rate |
| Step 2: Idle Stablecoins | No | Grove has no separate idle stablecoin module |
| Step 3: sUSDS Profit | No | No sUSDS positions for Grove |
| PSM3 Idle | Yes | USDS in PSM3 on L2 chains |
| PSM3 sUSDS | Yes | sUSDS in PSM3 on L2 chains |
| Step 4: Sky Direct Exposure | Yes | RWA assets (JHLCO, JHST, BUIDL, USTB) |
| Borrow Rate Subsidy | Yes | Eligible per `BORROW_RATE_SUBSIDY_ELIGIBLE_STARS` |

## Borrow Rate Subsidy

| Parameter | Value |
|-----------|-------|
| Eligible | Yes |
| Cap | $1,000,000,000 per day |
| Start | 2026-01-01 |
| Duration | 24 months |

## RWA Exposure Cap

| Asset | Cap | Effect |
|-------|-----|--------|
| JHLCO | $325,000,000 | When balance exceeds cap, Sky Direct Exposure reimbursement is calculated pro-rata. Excess reverts to standard allocation treatment. |

## Known Issue: Missing MAX(0,...) Clamp

> Source: `src/lib/debt-pnl/calculations/grove-rwa-exposure.ts:127`

The RWA reimbursement calculation does not apply `MAX(0, Base Rate Cost - Actual Revenue)` as specified by Laniakea. This means when RWA assets outperform the base rate, the reimbursement can go negative (star being charged extra rather than clamped to zero).

**Status**: Confirmed bug (BUG-1). Fix pending.
