# Sunlit Keelstone (Built for Base)

Sunlit Keelstone is a medium-sized, browser-first Base workbench for confirming network identity (chainId 8453 / 84532) and running practical read-only probes across network state, addresses, and ERC-20 contracts, with direct Basescan references for verification.

---

## Base network context

Base Mainnet  
chainId (decimal): 8453  
Explorer: https://basescan.org  

Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

---

## Repository layout

- config/base.networks.json  
  Static Base network configuration (chainIds, RPC URLs, explorers).

- scripts/example-probes.json  
  Sample inputs for repeatable read-only checks.

- app/sunlit-keelstone.ts  
  Browser script that connects a Coinbase Wallet and performs Base RPC probes.

- docs/architecture.md  
  Notes describing the read-only model, Base alignment, and design tradeoffs.

- docs/validation-notes.md  
  A living record of testnet validation steps and verification links.

- contracts/  
  Solidity contracts deployed to Base Sepolia for testnet validation:
  - arrays.sol — defines dynamic or fixed-size arrays 
  - control.sol — restricts sensitive functions to authorized users 

- package.json  
  Dependency manifest referencing Coinbase SDKs and multiple Base + Coinbase repositories.

- README.md  
  Technical documentation and deployment records.

---

## Capabilities overview

Sunlit Keelstone is intentionally read-only:

- Coinbase Wallet connection (EIP-1193)  
- Base chainId validation (8453 / 84532)  
- Network snapshot (block height, timestamp, gas signals)  
- Address probe (ETH balance, nonce, bytecode presence)  
- ERC-20 probe (metadata + holder balance)  
- Basescan links for independent verification  

No transactions are created, signed, or broadcast.

---

## Tooling and dependencies

- Coinbase Wallet SDK for wallet access  
- OnchainKit references for Base-aligned primitives and account abstraction context  
- viem for typed, efficient read-only RPC communication  
- Multiple Base and Coinbase GitHub repositories included as direct Git dependencies  

---

## License

MIT License

Copyright (c) 2025 YOUR_NAME

---

## Author

GitHub: https://github.com/08-belle 

Email: 08-belle.jollier@icloud.com 

---

## Testnet Deployment (Base Sepolia)

As part of pre-production validation, one or more contracts may be deployed to the Base Sepolia test network to confirm correct behavior and tooling compatibility.

Network: Base Sepolia  
chainId (decimal): 84532  
Explorer: https://sepolia.basescan.org  

Contract arrays.sol address:  
0x13B7BD8D07eE35D62362d9a32174a0b6623ccD23

Deployment and verification:
- https://sepolia.basescan.org/address/0x13B7BD8D07eE35D62362d9a32174a0b6623ccD23
- https://sepolia.basescan.org/0x13B7BD8D07eE35D62362d9a32174a0b6623ccD23/0#code  

Contract control.sol address:  
0xc6B1301BD312dF2Bd2ca14d24a5e0C437dDe629D

Deployment and verification:
- https://sepolia.basescan.org/address/0xc6B1301BD312dF2Bd2ca14d24a5e0C437dDe629D
- https://sepolia.basescan.org/0xc6B1301BD312dF2Bd2ca14d24a5e0C437dDe629D/0#code  

These testnet deployments provide a controlled environment for validating Base tooling, account abstraction flows, and read-only onchain interactions prior to Base Mainnet usage.
