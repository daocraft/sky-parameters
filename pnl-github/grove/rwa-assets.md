# Grove - RWA Assets

> Last verified: 2026-02-21
> Source: `src/lib/debt-pnl/constants.ts:179-209`

## RWA Positions (Debt PnL Step 4 - Sky Direct Exposure)

These are Grove's Real World Asset positions used in the Sky Direct Exposure module. Revenue is calculated from NAV price change over the period, then compared to Base Rate cost.

| Symbol | Name | Protocol | Chain | Address | Cap | Notes |
|--------|------|----------|-------|---------|-----|-------|
| JHLCO | Janus Henderson Anemoy AAA CLO Fund Token | Centrifuge | Ethereum | `0x5a0f93d040de44e78f251b03c43be9cf317dcf64` | **$325,000,000** | Largest RWA position. Pro-rata when over cap. |
| JHST | Janus Henderson Anemoy Treasury Fund | Centrifuge | Ethereum | `0x8c213ee79581ff4984583c6a801e5263418c4b86` | None | |
| BUIDL | BlackRock USD Institutional Digital Liquidity Fund | Blackrock | Ethereum | `0x6a9da2d710bb9b700acde7cb81f10f1ff8c89041` | None | On-chain pricing |
| USTB | Superstate US Treasury Bills | Superstate | Ethereum | `0x43415eb6ff9db7e26a15b704e7a3edce97d31c4e` | None | On-chain pricing |

## Centrifuge Token Mappings

> Source: `src/lib/debt-pnl/calculations/grove-rwa-exposure.ts:17-22`

Used to query NAV prices from the Centrifuge GraphQL API.

| Ethereum Address | Centrifuge Token ID | Asset |
|-----------------|---------------------|-------|
| `0x5a0f93d040de44e78f251b03c43be9cf317dcf64` | `0x00010000000000070000000000000001` | JHLCO |
| `0x8c213ee79581ff4984583c6a801e5263418c4b86` | `0x00010000000000060000000000000001` | JHST |

## Centrifuge Vault Addresses

> Source: `TOKENS.ts` extra_data.vault_address

| Asset | Chain | Vault Address |
|-------|-------|---------------|
| JHLCO | Ethereum | `0x4880799eE5200fC58DA299e965df644fBf46780B` |
| JHST | Ethereum | `0xFE6920eB6C421f1179cA8c8d4170530CDBdfd77A` |
| Centrifuge | Avalanche | `0x1121F4e21eD8B9BC1BB9A2952cDD8639aC897784` |
| Centrifuge | Plume | `0x354a9222571259457B2e98b2285B62e6a9bf4eD3` |

## Pricing Sources

| Asset | Source | Method |
|-------|--------|--------|
| JHLCO | Centrifuge GraphQL API | NAV price from `https://api.centrifuge.io/graphql` |
| JHST | Centrifuge GraphQL API | NAV price from `https://api.centrifuge.io/graphql` |
| BUIDL | On-chain | ERC4626 `convertToAssets()` or direct price feed |
| USTB | On-chain | Direct price feed |

## Price Data Buffers

> Source: `src/lib/debt-pnl/calculations/grove-rwa-exposure.ts:377-378`

| Parameter | Value | Description |
|-----------|-------|-------------|
| Pre-period buffer | 7 days | Fetches price data starting 7 days before period start |
| Post-period buffer | 1 day | Fetches price data up to 1 day after period end |

## All Grove Ethereum Allocations (from TOKENS.ts)

Beyond the core RWA assets, Grove has these additional Ethereum positions:

| Contract | Protocol | Type | Underlying/Asset | Notes |
|----------|----------|------|-------------------|-------|
| `0xfa82580c16a31d0c1bc632a36f82e83efef3eec0` | Aave | atoken | RLUSD (`0x8292b...`) | aEthRLUSD. Simple period return. Block 22319334. |
| `0xe3190143eb552456f88464662f0c0c4ac67a77eb` | Aave | atoken | RLUSD (`0x8292b...`) | aHorRwaRLUSD. Simple period return. Block 23132230. |
| `0x68215b6533c47ff9f7125ac95adf00fe4a62f79e` | Aave | atoken | USDC (`0xa0b86...`) | Block 23132230. |
| `0x8292bb45bf1ee4d140127049757c2e0ff06317ed` | Ripple | erc20 | - | RLUSD token |
| `0x51c2d74017390cbbd30550179a16a1c28f7210fc` | Securitize | securitize | USDC (`0xa0b86...`) | Block 24041058. |
| `0x00000000efe302beaa2b3e6e1b18d08d69a9012a` | Agora | erc20 | - | AUSD. Block 24380799. |
| `0xe79c1c7e24755574438a26d5e062ad2626c04662` | Curve | curve | AUSD (`0x00000...`) | Block 24380799. |
| `0xbafead7c60ea473758ed6c6021505e8bbd7e8e5d` | Uniswap | uni_v3_pool | USDC (`0xa0b86...`) | Block 99999999 (placeholder). |
| `0xbeef2b5fd3d94469b7782aebe6364e6e6fb1b709` | Steakhouse | erc4626 | USDC (`0xa0b86...`) | Block 24148141. |

## Grove Non-Ethereum Allocations

### Base

| Contract | Protocol | Type | Notes |
|----------|----------|------|-------|
| `0xbeef2d50b428675a1921bc6bbf4bfb9d8cf1461a` | Morpho | erc4626 | Multi-market USDC vault. 6 markets. |

### Avalanche

| Contract | Protocol | Type | Notes |
|----------|----------|------|-------|
| `0x58f93d6b1ef2f44ec379cb975657c132cbed3b6b` | Centrifuge | centrifuge | USDC vault |
| `0x2c0adff8e114f3ca106051144353ac703d24b901` | Arch | galaxy_clo | Block 72633046 |

### Plume

| Contract | Protocol | Type | Notes |
|----------|----------|------|-------|
| `0x9477724bb54ad5417de8baff29e59df3fb4da74f` | Centrifuge | centrifuge_feeder | |
| `0xa5d465251fbcc907f5dd6bb2145488dfc6a2627b` | Centrifuge | centrifuge_feeder | Block 41311106 |

### Monad

| Contract | Protocol | Type | Notes |
|----------|----------|------|-------|
| `0x00000000efe302beaa2b3e6e1b18d08d69a9012a` | Agora | erc20 | AUSD. Block 36870131. |
| `0x754704bc059f8c67012fed69bc8a327a5aafb603` | Circle | erc20 | USDC |
| `0x32841a8fb53b741a8fd78c0fb9a6b2393d896a43d` | Morpho | erc4626 | 6 markets. |
| `0x7197e214c0b767cfb76fb734ab638e2c192f4e53` | Uniswap | uni_v3_lp | Block 39598901. |
