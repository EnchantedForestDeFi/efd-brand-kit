# alephium/token-list PR — wRATR submission runbook

**Status:** Ready except for the `id` field (waits for wRATR contract mainnet deploy)
**Target:** PR to [alephium/token-list](https://github.com/alephium/token-list) appending the wRATR entry to `tokens/mainnet.json`
**Precedent:** wSMT's currently-active token-list PR (merged overnight, ~12-24 hr typical merge time when well-formed)

---

## Pre-submission prerequisites (must be true before opening the PR)

- [x] **wRATR mark designed + committed** to this repo at `logos/wratr/wratr-mark-256.png`
- [ ] **EFD Brand Kit repo flipped public** so the `logoURI` resolves on raw.githubusercontent.com. Command:
  ```powershell
  gh repo edit EnchantedForestDeFi/efd-brand-kit --visibility public --accept-visibility-change-consequences
  ```
- [ ] **wRATR mainnet contract deployed on Alephium**. Output: 64-char hex contract id (e.g. `4126be6f21e1971acd63b304155b26a6d606ab80d85f67cc15a8fe83be966900`).
- [ ] **Group 0 verification** — wRATR contract MUST be in Group 0 of Alephium. Group 1/2/3 deployments cannot be used with Elexium DEX LP creation. wSMT learned this the hard way (the original deployment was in Group 3 and had to be redone in Group 0 to enable LP).

---

## The PR submission — 5 minutes once prerequisites are met

### Step 1 — Fork + clone

```powershell
gh repo fork alephium/token-list --clone --remote
cd token-list
```

### Step 2 — Branch

```powershell
git checkout -b add-wratr
```

### Step 3 — Edit `tokens/mainnet.json`

Append this entry to the end of the `tokens` array (after the last existing token). **Replace the `<WRATR_MAINNET_CONTRACT_ID>` placeholder with the actual hex id from deploy:**

```json
{
  "id": "<WRATR_MAINNET_CONTRACT_ID_FROM_DEPLOY>",
  "name": "Wrapped Ratatoskr",
  "symbol": "wRATR",
  "decimals": 8,
  "description": "Wrapped Ratatoskr (wRATR) is the bridged representation of native RATR on Alephium, backed 1:1 via the Ratatoskr Bridge.",
  "logoURI": "https://raw.githubusercontent.com/EnchantedForestDeFi/efd-brand-kit/main/logos/wratr/wratr-mark-256.png"
}
```

(This file is also at [`token-list-entry-wratr.json`](token-list-entry-wratr.json) in this repo for easy copy/paste.)

### Step 4 — Commit + push + open PR

```powershell
git add tokens/mainnet.json
git commit -m "Add wRATR (Wrapped Ratatoskr)"
git push -u origin add-wratr
gh pr create --title "Add wRATR (Wrapped Ratatoskr)" --body-file PR-BODY.md
```

### Step 5 — Verify

After PR is opened, wait for an Alephium core maintainer to review + merge. Typical merge time: overnight, ~12-24 hr if the entry is well-formed.

After merge, wRATR auto-propagates to:
- Onixscan (alphexplorer.io)
- AlphScan
- AlphFlow
- Elexium token factory (token shows up in pair-creation dropdown)

---

## PR description template (PR-BODY.md content)

```markdown
## Add wRATR — Wrapped Ratatoskr on Alephium

**Project:** Enchanted Forest DeFi (EFD)
**Token:** wRATR (Wrapped Ratatoskr)
**Native chain:** Ratatoskr (RATR) — mainnet launched 2026-06-01
**Bridge:** EFD's Ratatoskr Bridge — similar architecture to the existing EFD-operated wSMT bridge

wRATR is the Alephium-side wrapped representation of native RATR, backed 1:1 by RATR held in the bridge custody contract. Bridging in mints wRATR; bridging out burns it.

**Contract:**
- ID: `<WRATR_MAINNET_CONTRACT_ID>`
- Group: 0 (verified Group 0 for Elexium LP compatibility)
- Decimals: 8 (matches native RATR + wSMT precedent)
- Implements `IFungibleToken` — passes the standard fungible-token validation

**Logo:** Hosted in EFD's official brand kit repo, version-controlled, CC-BY 4.0 licensed.
- 256px PNG: https://raw.githubusercontent.com/EnchantedForestDeFi/efd-brand-kit/main/logos/wratr/wratr-mark-256.png
- Repo: https://github.com/EnchantedForestDeFi/efd-brand-kit

**Links:**
- EFD website: https://enchantedforestdefi.com
- RATR explorer: https://ratrexplorer.efd.com
- Bridge: [link added once UI is live]

Thanks for your time reviewing!
```

---

## Post-merge follow-up sequence

Once the PR is merged + wRATR appears in the registry:

1. **Verify visibility** on Onixscan, AlphScan, AlphFlow (~24 hr post-merge typically)
2. **Create Elexium LP pair** — wRATR/NUTTY pool, deposit initial liquidity
3. **Submit Elexium gauge proposal** for vote eligibility
4. **First gauge vote** + first bribe deposit cycle

---

## Future wrapped-token submissions

This runbook + the JSON template are designed to be reusable. For future wrapped tokens issued by EFD (wKRGN, wOTHER), copy the JSON template, swap `name`/`symbol`/`description`/`logoURI`, and follow the same flow. The fungible-token-test reference at [`wratr-fungible-token-test.md`](wratr-fungible-token-test.md) applies to all of them.
