# Spark - PSM3 Configuration

> Last verified: 2026-02-21

## PSM3 Contract Addresses

> Source: `TOKENS.ts:972-988` (STAR_ALLOCATION_DATA)

| Chain | PSM3 Contract Address |
|-------|----------------------|
| Base | `0x1601843c5e9bc251a3272907010afa41fa18347e` |
| Arbitrum | `0x2b05f8e1cacc6974fd79a673a341fe1f58d27266` |
| Optimism | `0xe0f9978b907853f354d79188a3defbd41978af62` |
| Unichain | `0x7b42ed932f26509465f7ce3faf76ffce1275312f` |

## USDC in PSM3 (Sky Direct Exposure)

> Source: `src/lib/debt-pnl/constants.ts:32-61`

These USDC positions within PSM3 are treated as "Sky Direct Exposure" assets. The PnL calculation compares the Base Rate cost against the actual yield (USDC custodian yield, e.g., Coinbase Custody) and reimburses the difference via `MAX(0, Base Rate Cost - Actual Revenue)`.

| Chain | USDC Address | Description |
|-------|--------------|-------------|
| Base | `0x833589fcd6edb6e08f4c7c32d4f71b54bda02913` | USDC in PSM3 (Base) |
| Arbitrum | `0xaf88d065e77c8cc2239327c5edb3a432268e5831` | USDC in PSM3 (Arbitrum) |
| Optimism | `0x0b2c639c533813f4aa9d7837caf62653d097ff85` | USDC in PSM3 (Optimism) |
| Unichain | `0x078d782b760474a361dda0af3839290b0ef57ad6` | USDC in PSM3 (Unichain) |

All require `source: 'psm3'` filter to distinguish from ALM-held USDC.

## PSM3 Token Composition

Each PSM3 contract holds three token types. The debt PnL handles each differently:

| Token | Module | Treatment |
|-------|--------|-----------|
| USDC | PSM3 Sky Direct Exposure (Step 4) | `MAX(0, baseCost - actualYield)` reimbursement |
| USDS | PSM3 Idle (Step 2 variant) | Idle reimbursement at Agent Rate (currently Base Rate in code) |
| sUSDS | PSM3 sUSDS (Step 3 variant) | 30bps spread credit |
