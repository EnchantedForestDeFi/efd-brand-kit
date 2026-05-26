# wRATR Fungible-Token Test — Contract Template

**Purpose:** Document the Alephium `IFungibleToken` interface requirement so wRATR's Ralph contract passes the same fungible-token validation that wSMT (the active Group 0 wSMT, currently listed in `alephium/token-list`) passed.

**Source-of-truth:** The active wSMT contract deployed on Alephium mainnet (its source is in EFD's bridge codebase). The on-chain contract is publicly inspectable via any Alephium explorer.

---

## The "fungible token test" in one sentence

The contract must declare `implements IFungibleToken` **and** define all four interface methods: `getSymbol`, `getName`, `getDecimals`, `getTotalSupply`.

If a Ralph contract does this, it's recognized as a fungible token by Alephium's token-list validator, AlphScan, Onixscan, Elexium, and any DApp using the `IFungibleToken` interface check.

---

## The interface (from Alephium core)

```ralph
Interface IFungibleToken {
  pub fn getSymbol() -> ByteVec
  pub fn getName() -> ByteVec
  pub fn getDecimals() -> U256
  pub fn getTotalSupply() -> U256
}
```

Note: Ralph doesn't have a native string type, so `symbol` + `name` are `ByteVec` (caller decodes to UTF-8).

Reference: [Alephium official documentation](https://docs.alephium.org/).

---

## The wSMT-pattern implementation that passed (template for wRATR)

```ralph
Contract WrappedSMT(
  symbol: ByteVec,
  name: ByteVec,
  decimals: U256,
  // ... other state fields (totalSupply, ownership, bridge, limits, etc.) ...
) implements IFungibleToken {
  pub fn getSymbol() -> ByteVec { return symbol }
  pub fn getName() -> ByteVec { return name }
  pub fn getDecimals() -> U256 { return decimals }
  pub fn getTotalSupply() -> U256 { return totalSupply }
  // ... bridge / mint / burn / etc methods ...
}
```

The four getters are the contract's only requirement for fungible-token compliance. Everything else (bridge logic, limits, ownership, mint/burn flows) is independent of the fungible-token interface check.

---

## What wRATR must do

wRATR uses the same Ralph template as wSMT (fungible wrapped token pattern). At a minimum:

1. **Declare `Contract WrappedRATR(...) implements IFungibleToken`**
2. **Implement all four getter methods** returning the respective state variables
3. **At deploy time**, pass the wRATR-specific constructor args:
   - `symbol`: "wRATR" encoded as hex bytes
   - `name`: "Wrapped Ratatoskr" encoded as hex bytes
   - `decimals`: `8` (matches native RATR + wSMT precedent)
   - `absMaxSupply`, initial `totalSupply`, etc. per the bridge specification

If the contract matches this pattern, it will pass the same fungible-token validation that wSMT passed in its merged token-list PR.

---

## What "the failed wSMT" actually was (Group 3 vs Group 0)

There were two wSMT PRs in `alephium/token-list` history. The first deployed wSMT in Alephium Group 3; the second redeployed in Group 0. Both contracts were valid fungible tokens — both passed the IFungibleToken validation. The Group 3 deployment "failed" in a different sense: Elexium DEX only operates in Group 0, so a Group 3 token cannot create LP and is effectively useless for DeFi. The team had to redeploy in Group 0 to enable LP.

**Implication for wRATR:** the test passage is about the CONTRACT, not the deployment group. The contract just needs to implement `IFungibleToken` correctly. But the DEPLOYMENT must be in Group 0 to be usable on Elexium DEX.

See [`token-list-pr-runbook.md`](token-list-pr-runbook.md) "Group 0 verification" prerequisite for the deployment-group gate.

---

## Cross-references

- [`token-list-pr-runbook.md`](token-list-pr-runbook.md) — submission flow for the wRATR token-list PR
- [`token-list-entry-wratr.json`](token-list-entry-wratr.json) — the exact JSON entry to add to `alephium/token-list`
- [Alephium official docs](https://docs.alephium.org/) — Ralph language + interface reference
- [Alephium brand guide](https://github.com/alephium/alephium-brand-guide) — for the Alephium-side branding context
- The active wSMT contract on Alephium mainnet — inspectable via any Alephium block explorer
