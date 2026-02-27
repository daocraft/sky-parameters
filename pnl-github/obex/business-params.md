# Obex - Business Parameters

> Last verified: 2026-02-21

## PnL Calculation Modules

Obex is the simplest star — Maximum Debt Fees equals the Net Amount with no reimbursements.

| Module | Enabled | Notes |
|--------|---------|-------|
| Step 1: Max Debt Fees | Yes | TWA Debt x Base Rate |
| Step 2: Idle Stablecoins | No | |
| Step 3: sUSDS Profit | No | |
| PSM3 Idle | No | |
| PSM3 sUSDS | No | |
| Step 4: Sky Direct Exposure | No | Maple position handled differently (see known issue) |
| Borrow Rate Subsidy | No | Not eligible |

## Borrow Rate Subsidy

| Parameter | Value |
|-----------|-------|
| Eligible | **No** |

Obex is excluded from `BORROW_RATE_SUBSIDY_ELIGIBLE_STARS`.

## Settlement Formula

```
Net Amount = Maximum Debt Fees
           (no reimbursements, no subsidies)
```

This is per the methodology specification. Obex pays the full base rate on its debt with no offsets.
