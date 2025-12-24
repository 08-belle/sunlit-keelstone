# Sunlit Keelstone — Architecture Notes

High-level description of the project structure, Base alignment, and design tradeoffs.

---

## Read-Only Model

Sunlit Keelstone is designed around a **read-only first** approach:

- Balance checks
- Block and chain metadata inspection
- Token symbol / decimals reads

No write operations are required for core validation paths.

---

## Base Alignment

The project is Base-first by design:

- Supports **Base Mainnet** and **Base Sepolia** only
- Uses official public Base RPC endpoints
- Explorer links resolve to BaseScan domains
- Chain metadata is centralized in `config/base.networks.json`

No network constants should be duplicated in code.

---

## Project Structure

- `config/` — static network and environment configuration
- `scripts/` — sample inputs and helpers for validation
- `docs/` — internal documentation and operational notes

This separation keeps logic simple and reviewable.

---

## Design Tradeoffs

- **Pros**
  - Minimal risk surface
  - Easy validation and auditing
  - No wallet-type assumptions (EOA vs smart account)

- **Cons**
  - No transaction execution paths
  - Limited coverage of write-side edge cases

These tradeoffs are intentional for the current scope.

---

_Last updated: initial scaffold_
