# Spark - Business Parameters

> Last verified: 2026-02-21

## PnL Calculation Modules

Spark uses the most modules of any star:

| Module | Enabled | Notes |
|--------|---------|-------|
| Step 1: Max Debt Fees | Yes | TWA Debt x Base Rate |
| Step 2: Idle Stablecoins | Yes | USDS, DAI, USDC on all chains |
| Step 3: sUSDS Profit | Yes | 30bps spread credit (L2 only, Ethereum implicit) |
| PSM3 Idle | Yes | USDS in PSM3 on L2 chains |
| PSM3 sUSDS | Yes | sUSDS in PSM3 on L2 chains |
| Step 4: Sky Direct Exposure | Yes | USDC in PSM3 |
| Borrow Rate Subsidy | Yes | Eligible per `BORROW_RATE_SUBSIDY_ELIGIBLE_STARS` |
| Curve Pool Handling | Yes | sUSDS/USDT and PYUSD/USDS pools |

## Borrow Rate Subsidy

| Parameter | Value |
|-----------|-------|
| Eligible | Yes |
| Cap | $1,000,000,000 per day |
| Start | 2026-01-01 |
| Duration | 24 months |

## Curve Pool Special Handling

### sUSDS/USDT Pool

| Parameter | Value |
|-----------|-------|
| LP Address | `0x00836fe54625be242bcfa286207795405ca4fd10` |
| Active From | November 1, 2025 |
| Split Logic | USDT portion: base rate treatment. sUSDS portion: 30bps spread credit. |

### PYUSD/USDS Pool

| Parameter | Value |
|-----------|-------|
| LP Address | `0xa632d59b9b804a956bfaa9b48af3a1b74808fc1f` |
| Treatment | Full Agent Credit Line Borrow Rate, no idle reimbursement on PYUSD |

## One-Time Revenue Adjustments

> Source: `src/lib/pnl-utils/constants/addresses.ts:66-80`

| Month | Address | Amount | Description |
|-------|---------|--------|-------------|
| 2025-12 | `0x6c3ea9036406852006290770bedfcaba0e23a0e8` (PYUSD) | $5,815,000 | PayPal PYUSD bulk payments ($1.815M Dec 2 + $4M Dec 29) |

## PYUSD Prepayment

> Source: `TOKENS.ts:344`

| Parameter | Value |
|-----------|-------|
| PYUSD Address | `0x6c3ea9036406852006290770bedfcaba0e23a0e8` |
| Prepayment Amount | $2,000,000 |

## Ethereum sUSDS Treatment

On Ethereum, sUSDS (`0xa3931d71877c0e7a3148cb7eb4463524fec27fbd`) is **excluded** from the explicit 30bps spread calculation. This is intentional:
- On Ethereum, sUSDS is an ERC4626 vault earning SSR via token appreciation
- The debt module charges SSR + 30bps (Base Rate)
- The implicit difference is the 30bps spread
- Adding an explicit credit would double-count, resulting in net charge of 0
