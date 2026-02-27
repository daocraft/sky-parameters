# Spark - Chain Configuration

> Last verified: 2026-02-21
> Source: `src/lib/debt-pnl/constants.ts:12`, `TOKENS.ts`

## Active Chains

| Chain | ALM | PSM3 | Lending | Idle Stablecoins | sUSDS | Notes |
|-------|-----|------|---------|------------------|-------|-------|
| Ethereum | Yes | No | Yes (SparkLend, Morpho, Aave, Curve) | Yes | Yes (excluded from spread) | Primary chain. Debt sourced from Vat. |
| Base | Yes | Yes | Yes (Aave, Morpho, Fluid) | Yes | Yes | |
| Arbitrum | Yes | Yes | Yes (Aave, Fluid) | Yes | Yes | |
| Optimism | Yes | Yes | No | Yes | Yes | |
| Unichain | Yes | Yes | No | Yes | Yes | |
| Avalanche | Yes | No | Yes (Spark, Aave) | No | No | Added later, not in STAR_CHAINS for debt PnL |

**Note**: `STAR_CHAINS.spark` in `constants.ts` lists `['ethereum', 'base', 'arbitrum', 'optimism', 'unichain']`. Avalanche is present in `TOKENS.ts` but not in the debt PnL chain configuration.

## Debt Source

Spark debt is sourced from the MCD Vat contract on Ethereum only.

| Parameter | Value |
|-----------|-------|
| Vat Address | `0x35d1b3f3d7966a1dfe207aa4514c12a259a0492b` |

Debt is read from `star_allocation_systems.debt` (hourly snapshots).
