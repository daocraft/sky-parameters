# Obex - Maple Assets

> Last verified: 2026-02-21
> Source: `src/lib/debt-pnl/constants.ts:219-227`

## Maple Positions

Obex holds a single asset position in Maple's syrupUSDC vault.

| Symbol | Name | Protocol | Chain | Address | Asset Address | Notes |
|--------|------|----------|-------|---------|---------------|-------|
| syrupUSDC | Maple syrupUSDC | Maple | Ethereum | `0x80ac24aa929eaf5013f6436cda2a7ba190f5cc0b` | USDC (`0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48`) | ERC4626 vault |

## Pricing

| Method | Source |
|--------|--------|
| NAV pricing | ERC4626 `convertToAssets()` on-chain |

## All Obex Ethereum Allocations (from TOKENS.ts)

| Contract | Protocol | Type | Notes |
|----------|----------|------|-------|
| `0x80ac24aa929eaf5013f6436cda2a7ba190f5cc0b` | Maple | erc4626 | syrupUSDC. Primary allocation. |
| `0x6b175474e89094c44da98b954eedeac495271d0f` | Sky | erc20 | DAI. Asset (POL). |
| `0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48` | Circle | erc20 | USDC. Asset. |

## Known Issue: Inverted Reimbursement Formula

> Source: `src/lib/debt-pnl/calculations/obex-maple-exposure.ts:112`

The Obex reimbursement calculation uses an inverted formula (`revenue - maxDebtFees`) instead of `MAX(0, Base Rate Cost - Actual Revenue)` as specified by Laniakea. Additionally, it uses `maxDebtFeesUsd` as base cost instead of `principal x rate`.

**Status**: Confirmed bug (BUG-1 variant). Fix pending.
