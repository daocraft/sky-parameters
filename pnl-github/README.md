# Debt PnL Input Registry

This registry documents all inputs used in the debt-based PnL calculation. It serves as a transparent, auditable reference for stars/primes to review and propose changes to their configuration.

## Structure

```
pnl-github/
├── shared/           # Cross-star constants (token addresses, rates, subsidy config)
├── spark/            # Spark star configuration
├── grove/            # Grove star configuration
├── obex/             # Obex star configuration
└── _template/        # Template for adding a new star
```

Each star directory contains:

| File | Contents |
|------|----------|
| `chains.md` | Active chains and what's enabled per chain (ALM, PSM3, etc.) |
| `wallets.md` | ALM proxy, vault proxy, and wallet addresses per chain |
| `assets.md` / `lending-positions.md` / `rwa-assets.md` | Star-specific asset positions with protocols and addresses |
| `psm3.md` | PSM3 contract addresses and token addresses within PSM3 |
| `business-params.md` | Rates, caps, eligibility, date gates, one-time adjustments |

## Source Code References

All inputs are extracted from:

| Source File | What It Contains |
|-------------|------------------|
| `src/lib/debt-pnl/constants.ts` | Primary constants: chain mappings, rates, all address registries |
| `TOKENS.ts` | Root-level star allocation data with wallet addresses and protocol mappings |
| `src/lib/pnl-utils/constants/addresses.ts` | PnL-specific address sets (bill-always, sky-takes-all, SSR, SparkLend) |
| `src/lib/debt-pnl/calculations/grove-rwa-exposure.ts` | Centrifuge API and token mappings |
| `src/lib/debt-pnl/calculations/borrow-rate-subsidy.ts` | T-Bill rate API and subsidy ramp logic |
| `src/lib/settlement/revenue/utils.ts` | Base rate fallback |

## How to Propose Changes

1. Identify the input you want to change in the relevant file
2. Note the source code reference
3. Open a PR with the proposed change and rationale
4. Changes require corresponding code updates in the source files listed above

## Methodology Reference

Full methodology documentation: https://ori.amatsu.io/article/debt-pnl-methodology
