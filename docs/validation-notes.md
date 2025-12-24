# Sunlit Keelstone — Validation Notes

Living record of Base Sepolia testnet validation steps and verification links.

---

## Initial Setup

- Network: `base-sepolia`
- Chain ID: `84532`
- RPC: `https://sepolia.base.org`

---

## Validation Steps

### 1) RPC Connectivity
- [ ] Connect using default RPC
- [ ] Switch to fallback RPC if needed
- [ ] Confirm latest block number advances

### 2) Read-Only Probes
Using `scripts/example-probes.json`:

- [ ] ETH balance lookup
- [ ] Token metadata read (symbol / decimals)
- [ ] Contract code presence check
- [ ] Zero address handling

---

## Explorer Verification

- Explorer base URL: https://sepolia.basescan.org
- [ ] Address pages load correctly
- [ ] Block numbers match RPC responses
- [ ] No mainnet links appear during testnet runs

---

## Notes & Issues

- Prefer fixing config issues before touching logic
- Treat chainId or RPC changes as high-risk
- Keep this document updated as validation evolves

---

_Last updated: initial scaffold_
