# Spark - Wallet and Proxy Addresses

> Last verified: 2026-02-21
> Source: `TOKENS.ts:972-988` (STAR_ALLOCATION_DATA), `TOKENS.ts` (wallet_address fields)

## ALM Proxy Addresses

These are the addresses that hold Spark's allocated funds on each chain.

| Chain | ALM Proxy Address | Notes |
|-------|-------------------|-------|
| Ethereum | `0x1601843c5e9bc251a3272907010afa41fa18347e` | Primary proxy |
| Base | `0x2917956eff0b5eaf030abdb4ef4296df775009ca` | |
| Arbitrum | `0x92afd6f2385a90e44da3a8b60fe36f6cbe1d8709` | |
| Optimism | `0x876664f0c9ff24d1aa355ce9f1680ae1a5bf36fb` | |
| Unichain | `0x345e368fccd62266b3f5f37c9a131fd1c39f5869` | |
| Avalanche | `0xece6b0e8a54c2f44e066fbb9234e7157b15b7fec` | Not in debt PnL STAR_CHAINS |

## Vault Proxy Address

| Chain | Vault Address | Notes |
|-------|---------------|-------|
| Ethereum | `0x691a6c29e9e96dd897718305427ad5d534db16ba` | MCD vault proxy |

## PSM3 Contract Addresses

| Chain | PSM3 Address |
|-------|--------------|
| Base | `0x1601843c5e9bc251a3272907010afa41fa18347e` |
| Arbitrum | `0x2b05f8e1cacc6974fd79a673a341fe1f58d27266` |
| Optimism | `0xe0f9978b907853f354d79188a3defbd41978af62` |
| Unichain | `0x7b42ed932f26509465f7ce3faf76ffce1275312f` |

## sUSDS Oracle Addresses (L2)

Used for sUSDS price conversion on L2 chains where sUSDS is a plain ERC20.

| Chain | Oracle Address | Source |
|-------|----------------|--------|
| Base | `0xeC0C14Ea7fF20F104496d960FDEBF5a0a0cC14D0` | `TOKENS.ts` extra_data |
| Arbitrum | `0x73750DbD85753074e452B2C27fB9e3B0E75Ff3B8` | `TOKENS.ts` extra_data |
| Optimism | `0x15ACEE5F73b36762Ab1a6b7C98787b8148447898` | `TOKENS.ts` extra_data |
| Unichain | `0x93c81ADc7F98FdBC8C7a15eCBeD312c8F6adbcB3` | `TOKENS.ts` extra_data |
