# Grove - Chain Configuration

> Last verified: 2026-02-21
> Source: `src/lib/debt-pnl/constants.ts:13`, `TOKENS.ts`

## Active Chains

| Chain | ALM | PSM3 | RWA | Other Allocations | Notes |
|-------|-----|------|-----|-------------------|-------|
| Ethereum | Yes | No | Yes (JHLCO, JHST, BUIDL, USTB) | Aave, Ripple, Securitize, Agora, Curve, Uniswap, Steakhouse | Primary chain. Debt sourced from Vat. |
| Base | Yes | Yes* | No | Morpho | *PSM3 used for debt PnL on L2 |
| Avalanche | Yes | No | No | Centrifuge, Arch (Galaxy CLO) | Not in STAR_CHAINS for debt PnL |
| Plume | Yes | No | No | Centrifuge | Not in STAR_CHAINS for debt PnL |
| Monad | Yes | No | No | Agora, Morpho, Uniswap | Not in STAR_CHAINS for debt PnL |

**Note**: `STAR_CHAINS.grove` in `constants.ts` lists only `['ethereum']` for debt PnL purposes. However, the debt PnL service adds PSM3 processing for L2 chains `['base', 'arbitrum', 'optimism', 'unichain']` for Grove (see `debt-pnl.service.ts:118`).

## Debt Source

Grove debt is sourced from the MCD Vat contract on Ethereum only.

| Parameter | Value |
|-----------|-------|
| Vat Address | `0x35d1b3f3d7966a1dfe207aa4514c12a259a0492b` |
