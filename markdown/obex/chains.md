# Obex - Chain Configuration

> Last verified: 2026-02-21
> Source: `src/lib/debt-pnl/constants.ts:14`, `TOKENS.ts`

## Active Chains

| Chain | ALM | PSM3 | Assets | Notes |
|-------|-----|------|--------|-------|
| Ethereum | Yes | No | Maple syrupUSDC | Only chain. Simplest star configuration. |

**Note**: `STAR_CHAINS.obex` in `constants.ts` lists only `['ethereum']`.

## Debt Source

Obex debt is sourced from the MCD Vat contract on Ethereum only.

| Parameter | Value |
|-----------|-------|
| Vat Address | `0x35d1b3f3d7966a1dfe207aa4514c12a259a0492b` |
