# Spark - Lending Positions

> Last verified: 2026-02-21

## Ethereum - Idle Lending Positions (Debt PnL)

> Source: `src/lib/debt-pnl/constants.ts:115-168`

These positions are used by the idle stablecoin reimbursement module. The utilization rate determines how much capital is "idle" (not lent out) and eligible for reimbursement.

| Label | Protocol | Underlying | Address | Notes |
|-------|----------|------------|---------|-------|
| spDAI | SparkLend | DAI | `0x4dedf26112b3ec8ec46e7e31ea5e123490b05b8b` | |
| morpho-DAI | Morpho | DAI | `0x73e65dbd630f90604062f6e02fab9138e713edd9` | ERC4626 vault |
| spUSDS | SparkLend | USDS | `0xc02ab1a5eaa8d1b114ef786d9bde108cd4364359` | SSR-funded idle capital |
| morpho-USDS | Morpho | USDS | `0xe41a0583334f0dc4e023acd0bfef3667f6fe0597` | ERC4626 vault |
| aUSDS | Aave | USDS | `0x09aa30b182488f769a9824f15e6ce58591da4781` | |
| aUSDS | Aave | USDS | `0x32a6268f9ba3642dda7892add74f1d34469a4259` | Second Aave position |
| curve-USDT-LP | Curve | USDT | `0x00836fe54625be242bcfa286207795405ca4fd10` | sUSDS/USDT pool. Active from Nov 1, 2025. |
| curve-PYUSD-LP | Curve | PYUSD | `0xa632d59b9b804a956bfaa9b48af3a1b74808fc1f` | PYUSD/USDS pool |

## Ethereum - All Allocation Positions (from TOKENS.ts)

Full list of Spark Ethereum allocations including protocols not in the debt PnL idle lending module.

| Contract | Protocol | Type | Underlying/Asset | Notes |
|----------|----------|------|-------------------|-------|
| `0x00836fe54625be242bcfa286207795405ca4fd10` | Curve | curve | USDT (`0xdac17...`) | sUSDS/USDT LP |
| `0x09aa30b182488f769a9824f15e6ce58591da4781` | Aave | atoken | USDS (`0xdc035...`) | |
| `0x2bbe31d63e6813e3ac858c04dae43fb2a72b0d11` | Fluid | erc4626 | sUSDS (`0xa3931...`) | |
| `0x32a6268f9ba3642dda7892add74f1d34469a4259` | Aave | atoken | USDS (`0xdc035...`) | |
| `0x377c3bd93f2a2984e1e7be6a5c22c525ed4a4815` | SparkLend | atoken | USDC (`0xa0b86...`) | Direct rate |
| `0x38464507e02c983f20428a6e8566693fe9e422a9` | Arkis | erc4626 | USDC (`0xa0b86...`) | |
| `0x43415eb6ff9db7e26a15b704e7a3edce97d31c4e` | Superstate | superstate | USDC (`0xa0b86...`) | USTB |
| `0x49506c3aa028693458d6ee816b2ec28522946872` | Anchorage | anchorage | - | |
| `0x14d60e7fdc0d71d8611742720e4c50e7a974020c` | Superstate | superstate | USDC (`0xa0b86...`) | |
| `0x4c9edd5852cd905f086c759e8383e09bff1e68b3` | Ethena | ethena | - | USDe. Sky takes all. |
| `0x4dedf26112b3ec8ec46e7e31ea5e123490b05b8b` | SparkLend | atoken | DAI (`0x6b175...`) | |
| `0x56a76b428244a50513ec81e225a293d128fd581d` | Morpho | erc4626 | USDC (`0xa0b86...`) | Multi-market vault |
| `0x6a9da2d710bb9b700acde7cb81f10f1ff8c89041` | Blackrock | buidl | USDC (`0xa0b86...`) | BUIDL. Sky takes all. |
| `0x73e65dbd630f90604062f6e02fab9138e713edd9` | Morpho | erc4626 | DAI (`0x6b175...`) | Multi-market vault |
| `0x779224df1c756b4edd899854f32a53e8c2b2ce5d` | SparkLend | atoken | PYUSD (`0x6c3ea...`) | Bill always. Direct rate. |
| `0x80ac24aa929eaf5013f6436cda2a7ba190f5cc0b` | Maple | erc4626 | USDC (`0xa0b86...`) | syrupUSDC |
| `0x8c213ee79581ff4984583c6a801e5263418c4b86` | Centrifuge | centrifuge | USDC (`0xa0b86...`) | JHST |
| `0x98c23e9d8f34fefb1b7bd6a91b7ff122f4e16f5c` | Aave | atoken | USDC (`0xa0b86...`) | |
| `0x9d39a5de30e57443bff2a8307a4256c8797a3497` | Ethena | erc4626 | USDe (`0x4c9ed...`) | sUSDe with cooldown |
| `0xa632d59b9b804a956bfaa9b48af3a1b74808fc1f` | Curve | curve | PYUSD (`0x6c3ea...`) | PYUSD/USDS LP |
| `0xc02ab1a5eaa8d1b114ef786d9bde108cd4364359` | SparkLend | atoken | USDS (`0xdc035...`) | SSR address |
| `0xe41a0583334f0dc4e023acd0bfef3667f6fe0597` | Morpho | erc4626 | USDS (`0xdc035...`) | Multi-market vault |
| `0xe7df13b8e3d6740fe17cbe928c7334243d86c92f` | SparkLend | atoken | USDT (`0xdac17...`) | Bill always. Direct rate. SSR funded. |

## Base - Allocation Positions

| Contract | Protocol | Type | Underlying/Asset | Notes |
|----------|----------|------|-------------------|-------|
| `0x4e65fe4dba92790696d040ac24aa414708f5c0ab` | Aave | atoken | USDC (`0x83358...`) | |
| `0x7bfa7c4f149e7415b73bdedfe609237e29cbf34a` | Morpho | erc4626 | USDC (`0x83358...`) | Multi-market |
| `0xf62e339f21d8018940f188f6987bcdf02a849619` | Fluid | erc4626 | sUSDS (`0x5875e...`) | |

## Arbitrum - Allocation Positions

| Contract | Protocol | Type | Underlying/Asset | Notes |
|----------|----------|------|-------------------|-------|
| `0x724dc807b04555b71ed48a6896b6f41593b8c637` | Aave | atoken | USDC (`0xaf88d...`) | |
| `0x3459fcc94390c3372c0f7b4cd3f8795f0e5afe96` | Fluid | erc4626 | sUSDS (`0xddb46...`) | |

## Avalanche - Allocation Positions

| Contract | Protocol | Type | Underlying/Asset | Notes |
|----------|----------|------|-------------------|-------|
| `0x28b3a8fb53b741a8fd78c0fb9a6b2393d896a43d` | Spark | erc4626 | USDC (`0xb97ef...`) | |
| `0x625e7708f30ca75bfd92586e17077590c60eb4cd` | Aave | atoken | USDC (`0xb97ef...`) | |

## SparkLend-Specific Address Classifications

> Source: `src/lib/pnl-utils/constants/addresses.ts`

### Bill Always Addresses

These assets are always charged at the full base rate regardless of their APY.

| Address | Asset | Reason |
|---------|-------|--------|
| `0x779224df1c756b4edd899854f32a53e8c2b2ce5d` | spPYUSD | PYUSD SparkLend |
| `0xe7df13b8e3d6740fe17cbe928c7334243d86c92f` | spUSDT | USDT SparkLend |
| `0x6c3ea9036406852006290770bedfcaba0e23a0e8` | PYUSD (in-wallet) | PayPal asset |

### Sky Takes All Addresses

Sky takes all profit on these assets. Star doesn't pay for underperformance.

| Address | Asset | Reason |
|---------|-------|--------|
| `0x6a9da2d710bb9b700acde7cb81f10f1ff8c89041` | BUIDL | BlackRock |
| `0x4c9edd5852cd905f086c759e8383e09bff1e68b3` | USDe | Ethena |

### Simple Period Return Addresses

Period return treated as annual rate (not annualized).

| Address | Asset |
|---------|-------|
| `0xfa82580c16a31d0c1bc632a36f82e83efef3eec0` | aEthRLUSD |
| `0xe3190143eb552456f88464662f0c0c4ac67a77eb` | aHorRwaRLUSD |

### SparkLend Direct Rate Addresses

Use liquidity index growth instead of borrow rate conversion (governance-defined fixed rates).

| Address | Asset |
|---------|-------|
| `0xe7df13b8e3d6740fe17cbe928c7334243d86c92f` | spUSDT |
| `0x377c3bd93f2a2984e1e7be6a5c22c525ed4a4815` | spUSDC |
| `0x779224df1c756b4edd899854f32a53e8c2b2ce5d` | spPYUSD |

### SparkLend SSR-Funded Assets

Only these have idle capital SSR cost deducted from star_revenue.

| Address | Asset | Notes |
|---------|-------|-------|
| `0xe7df13b8e3d6740fe17cbe928c7334243d86c92f` | spUSDT | Has significant saving_V2 cost |

### USDS SSR Addresses

Use sUSDS price growth as custom base rate.

| Address | Asset |
|---------|-------|
| `0xc02ab1a5eaa8d1b114ef786d9bde108cd4364359` | spUSDS |

### SparkLend Pool Contract

| Parameter | Value |
|-----------|-------|
| SparkLend Pool | `0xc13e21b648a5ee794902342038ff3adab66be987` |

Used to fetch utilization rates for all SparkLend positions.

### SparkLend Asset Underlying Mapping

| spToken Address | Underlying Address | Symbol |
|-----------------|-------------------|--------|
| `0xe7df13b8e3d6740fe17cbe928c7334243d86c92f` | `0xdac17f958d2ee523a2206206994597c13d831ec7` | USDT |
| `0x779224df1c756b4edd899854f32a53e8c2b2ce5d` | `0x6c3ea9036406852006290770bedfcaba0e23a0e8` | PYUSD |
| `0xc02ab1a5eaa8d1b114ef786d9bde108cd4364359` | `0xdc035d45d973e3ec169d2276ddab16f1e407384f` | USDS |
| `0x4dedf26112b3ec8ec46e7e31ea5e123490b05b8b` | `0x6b175474e89094c44da98b954eedeac495271d0f` | DAI |
| `0x377c3bd93f2a2984e1e7be6a5c22c525ed4a4815` | `0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48` | USDC |

### Morpho Market IDs

> Source: `TOKENS.ts` extra_data.markets

**Morpho USDC (Ethereum)** - `0x56a76b428244a50513ec81e225a293d128fd581d`:
- `0xb323495f7e4148be5643a4ea4a8221eef163e4bccfdedc2a6f4696baacbc86cc`
- `0x54efdee08e272e929034a8f26f7ca34b1ebe364b275391169b28c6d7db24dbc8`
- `0x64d65c9a2d91c36d56fbc42d69e979335320169b3df63bf92789e2c8883fcc64`

**Morpho DAI (Ethereum)** - `0x73e65dbd630f90604062f6e02fab9138e713edd9`:
- 22 market IDs (see `TOKENS.ts` lines 356-377)

**Morpho USDS (Ethereum)** - `0xe41a0583334f0dc4e023acd0bfef3667f6fe0597`:
- `0x02e723fdfc0c26779c2c06bbf783e2f4d6aebd03cedc1806981b742f1a644105`
- `0x8cdb63a27a48ac27fadc0f158a732104bcc4e10bb61c9a5095ea7c127204e26c`
- `0x366bc0aa9aa70a1f075096e825e9b1c7221878a90edd52081d2af5cfca3beb89`
- `0xa79d8028dec527565028fd9fc075b02b498f2b69a1d519dff543ba99b812ff6b`

**Morpho USDC (Base)** - `0x7bfa7c4f149e7415b73bdedfe609237e29cbf34a`:
- `0x9103c3b4e834476c9a62ea009ba2c884ee42e94e6e314a26f04d312434191836`
- `0x38c846197ac32a752a60c25d4536ebb0c3920c532e9a859c38c91efb7b8c2abb`
