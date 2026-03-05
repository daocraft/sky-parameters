# Star Configuration - What You Need to Provide

This folder contains the addresses and configuration that each star/prime is responsible for providing and keeping up to date. These are the inputs that **you control** — protocol-level infrastructure (token addresses, rates, shared contracts) is managed separately by Sky governance.

## What's in each file

Each star file lists:

1. **Your chains** — which blockchains you operate on
2. **Your wallets** — ALM proxy and vault addresses per chain
3. **Your allocations** — every position you hold, with contract address, protocol, and chain

## How to propose changes

If you add a new allocation, move to a new chain, or change a wallet address:

1. Update your star file in this folder
2. Open a PR with a description of the change
3. The engineering team will update the corresponding code

## Template

See `_template.md` for the format when onboarding a new star.
