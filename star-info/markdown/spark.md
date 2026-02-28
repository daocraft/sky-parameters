# Spark

## Chains

| Chain | ALM Proxy | Vault Proxy |
|-------|-----------|-------------|
| Ethereum | `0x1601843c5e9bc251a3272907010afa41fa18347e` | `0x691a6c29e9e96dd897718305427ad5d534db16ba` |
| Base | `0x2917956eff0b5eaf030abdb4ef4296df775009ca` | — |
| Arbitrum | `0x92afd6f2385a90e44da3a8b60fe36f6cbe1d8709` | — |
| Optimism | `0x876664f0c9ff24d1aa355ce9f1680ae1a5bf36fb` | — |
| Unichain | `0x345e368fccd62266b3f5f37c9a131fd1c39f5869` | — |
| Avalanche | `0xece6b0e8a54c2f44e066fbb9234e7157b15b7fec` | — |

## PSM3 Contracts

| Chain | PSM3 Address |
|-------|--------------|
| Base | `0x1601843c5e9bc251a3272907010afa41fa18347e` |
| Arbitrum | `0x2b05f8e1cacc6974fd79a673a341fe1f58d27266` |
| Optimism | `0xe0f9978b907853f354d79188a3defbd41978af62` |
| Unichain | `0x7b42ed932f26509465f7ce3faf76ffce1275312f` |

## Allocations

### Ethereum

| Contract | Protocol | Type | Underlying | Notes |
|----------|----------|------|------------|-------|
| `0x4dedf26112b3ec8ec46e7e31ea5e123490b05b8b` | SparkLend | atoken | DAI | spDAI |
| `0xc02ab1a5eaa8d1b114ef786d9bde108cd4364359` | SparkLend | atoken | USDS | spUSDS |
| `0x377c3bd93f2a2984e1e7be6a5c22c525ed4a4815` | SparkLend | atoken | USDC | spUSDC |
| `0xe7df13b8e3d6740fe17cbe928c7334243d86c92f` | SparkLend | atoken | USDT | spUSDT |
| `0x779224df1c756b4edd899854f32a53e8c2b2ce5d` | SparkLend | atoken | PYUSD | spPYUSD |
| `0x73e65dbd630f90604062f6e02fab9138e713edd9` | Morpho | erc4626 | DAI | 22 markets |
| `0xe41a0583334f0dc4e023acd0bfef3667f6fe0597` | Morpho | erc4626 | USDS | 4 markets |
| `0x56a76b428244a50513ec81e225a293d128fd581d` | Morpho | erc4626 | USDC | 3 markets |
| `0x09aa30b182488f769a9824f15e6ce58591da4781` | Aave | atoken | USDS | |
| `0x32a6268f9ba3642dda7892add74f1d34469a4259` | Aave | atoken | USDS | |
| `0x98c23e9d8f34fefb1b7bd6a91b7ff122f4e16f5c` | Aave | atoken | USDC | |
| `0x2bbe31d63e6813e3ac858c04dae43fb2a72b0d11` | Fluid | erc4626 | sUSDS | |
| `0x00836fe54625be242bcfa286207795405ca4fd10` | Curve | LP | USDT | sUSDS/USDT pool |
| `0xa632d59b9b804a956bfaa9b48af3a1b74808fc1f` | Curve | LP | PYUSD | PYUSD/USDS pool |
| `0x80ac24aa929eaf5013f6436cda2a7ba190f5cc0b` | Maple | erc4626 | USDC | syrupUSDC |
| `0x6a9da2d710bb9b700acde7cb81f10f1ff8c89041` | Blackrock | buidl | USDC | BUIDL |
| `0x43415eb6ff9db7e26a15b704e7a3edce97d31c4e` | Superstate | superstate | USDC | USTB |
| `0x14d60e7fdc0d71d8611742720e4c50e7a974020c` | Superstate | superstate | USDC | |
| `0x8c213ee79581ff4984583c6a801e5263418c4b86` | Centrifuge | centrifuge | USDC | JHST. Vault: `0xFE6920eB6C421f1179cA8c8d4170530CDBdfd77A` |
| `0x38464507e02c983f20428a6e8566693fe9e422a9` | Arkis | erc4626 | USDC | |
| `0x49506c3aa028693458d6ee816b2ec28522946872` | Anchorage | anchorage | — | |
| `0x4c9edd5852cd905f086c759e8383e09bff1e68b3` | Ethena | ethena | — | USDe |
| `0x9d39a5de30e57443bff2a8307a4256c8797a3497` | Ethena | erc4626 | USDe | sUSDe |
| `0x6c3ea9036406852006290770bedfcaba0e23a0e8` | PayPal | erc20 | — | PYUSD in-wallet. Prepayment: $2M |

### Base

| Contract | Protocol | Type | Underlying | Notes |
|----------|----------|------|------------|-------|
| `0x4e65fe4dba92790696d040ac24aa414708f5c0ab` | Aave | atoken | USDC | |
| `0x7bfa7c4f149e7415b73bdedfe609237e29cbf34a` | Morpho | erc4626 | USDC | 2 markets |
| `0xf62e339f21d8018940f188f6987bcdf02a849619` | Fluid | erc4626 | sUSDS | |

### Arbitrum

| Contract | Protocol | Type | Underlying | Notes |
|----------|----------|------|------------|-------|
| `0x724dc807b04555b71ed48a6896b6f41593b8c637` | Aave | atoken | USDC | |
| `0x3459fcc94390c3372c0f7b4cd3f8795f0e5afe96` | Fluid | erc4626 | sUSDS | |

### Avalanche

| Contract | Protocol | Type | Underlying | Notes |
|----------|----------|------|------------|-------|
| `0x28b3a8fb53b741a8fd78c0fb9a6b2393d896a43d` | Spark | erc4626 | USDC | |
| `0x625e7708f30ca75bfd92586e17077590c60eb4cd` | Aave | atoken | USDC | |
