# [Star Name] - Chain Configuration

> Last verified: YYYY-MM-DD
> Source: `src/lib/debt-pnl/constants.ts` (STAR_CHAINS), `TOKENS.ts`

## Active Chains

| Chain | ALM | PSM3 | Lending | Other | Notes |
|-------|-----|------|---------|-------|-------|
| Ethereum | Yes/No | Yes/No | Yes/No | | |

## Debt Source

| Parameter | Value |
|-----------|-------|
| Vat Address | `0x35d1b3f3d7966a1dfe207aa4514c12a259a0492b` |

## Code Changes Required

When adding a new star:
1. Add to `STAR_CHAINS` in `src/lib/debt-pnl/constants.ts`
2. Add allocation data in `TOKENS.ts` under `STAR_ALLOCATION_DATA`
3. Add token entries in `TOKENS.ts` per chain
4. If eligible for borrow subsidy, add to `BORROW_RATE_SUBSIDY_ELIGIBLE_STARS`
