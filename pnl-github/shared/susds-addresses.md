# sUSDS Contract Addresses

> Last verified: 2026-02-21
> Source: `src/lib/debt-pnl/constants.ts:86-92`

sUSDS (Sky USD Savings) token addresses per chain. Used by the sUSDS profit module (Step 3) to identify sUSDS holdings in ALM proxy balances and calculate the 30bps spread credit.

| Chain | Address | Notes |
|-------|---------|-------|
| Ethereum | `0xa3931d71877c0e7a3148cb7eb4463524fec27fbd` | ERC4626 vault earning SSR via token appreciation. **Excluded** from explicit spread calculation (implicit via debt/SSR interaction). |
| Base | `0x5875eee11cf8398102fdad704c9e96607675467a` | Plain ERC20 on L2. Needs explicit 30bps credit. |
| Arbitrum | `0xddb46999f8891663a8f2828d25298f70416d7610` | Plain ERC20 on L2. Needs explicit 30bps credit. |
| Optimism | `0xb5b2dc7fd34c249f4be7fb1fcea07950784229e0` | Plain ERC20 on L2. Needs explicit 30bps credit. |
| Unichain | `0xa06b10db9f390990364a3984c04fadf1c13691b5` | Plain ERC20 on L2. Needs explicit 30bps credit. |

## PSM3 USDS Addresses

> Source: `src/lib/debt-pnl/constants.ts:94-99`

USDS token addresses within PSM3 contracts (L2 only). Used by PSM3 idle module.

| Chain | Address |
|-------|---------|
| Base | `0x820c137fa70c8691f0e44dc420a5e53c168921dc` |
| Arbitrum | `0x6491c05a82219b8d1479057361ff1654749b876b` |
| Optimism | `0x4f13a96ec5c4cf34e442b46bbd98a0791f20edc3` |
| Unichain | `0x7e10036acc4b56d4dfca3b77810356ce52313f9c` |

## PSM3 sUSDS Addresses

> Source: `src/lib/debt-pnl/constants.ts:101-106`

sUSDS within PSM3 contracts (L2 only). Used by PSM3 sUSDS module.

| Chain | Address |
|-------|---------|
| Base | `0x5875eee11cf8398102fdad704c9e96607675467a` |
| Arbitrum | `0xddb46999f8891663a8f2828d25298f70416d7610` |
| Optimism | `0xb5b2dc7fd34c249f4be7fb1fcea07950784229e0` |
| Unichain | `0xa06b10db9f390990364a3984c04fadf1c13691b5` |
