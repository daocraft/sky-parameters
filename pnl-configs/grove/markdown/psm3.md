# Grove - PSM3 Configuration

> Last verified: 2026-02-21

## PSM3 Chains

> Source: `src/lib/debt-pnl/debt-pnl.service.ts:118`

Grove uses PSM3 on L2 chains only (not on Ethereum). These are hardcoded in the debt PnL service.

| Chain | PSM3 Active | Notes |
|-------|-------------|-------|
| Base | Yes | Uses shared PSM3 infrastructure |
| Arbitrum | Yes | Uses shared PSM3 infrastructure |
| Optimism | Yes | Uses shared PSM3 infrastructure |
| Unichain | Yes | Uses shared PSM3 infrastructure |

**Note**: Grove doesn't have its own PSM3 contract addresses in `STAR_ALLOCATION_DATA`. The PSM3 processing uses the shared PSM3 token addresses from `constants.ts` (see `shared/susds-addresses.md`).

## PSM3 Token Addresses Used

Same as shared PSM3 addresses. See `shared/susds-addresses.md` and `shared/stablecoin-addresses.md` for the full address list per chain.

| Token Type | Module | Treatment |
|------------|--------|-----------|
| USDC | Sky Direct Exposure | `MAX(0, baseCost - actualYield)` reimbursement |
| USDS | PSM3 Idle | Idle reimbursement |
| sUSDS | PSM3 sUSDS | 30bps spread credit |
