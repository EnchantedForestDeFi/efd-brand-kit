# BNB Chain Brand Assets

**Source:** [bnbchain.org/en/brand-guidelines](https://www.bnbchain.org/en/brand-guidelines)
**Upstream license:** ⚠️ **none — proprietary, approval-based.** The mark is a **registered trademark**. There is no license file to mirror; the terms are the published guidelines, quoted below.
**Pulled:** 2026-10-02
**EFD use case:** referenced operationally because EFD operates the **wRATR bridge to BNB Smart Chain**

---

## 🚨 READ THIS BEFORE USING ANYTHING IN THIS FOLDER

**This folder is the most restricted in the kit.** Alephium ships LGPL-3.0; Base ships a brand guide. BNB Chain ships neither — it requires **permission**.

> "Projects should seek approval from BNB Chain before using the logo."

> "Projects must not use the BNB Chain logo in a way that implies endorsement or sponsorship by BNB Chain. In rare circumstances, this must be approved and authorized by management."

The mark cannot be used commercially without explicit written permission. **Having the file does not mean we may use it.**

---

## ✅ The carve-out — what we MAY do without asking

There is a standing permitted use, and most of what we need falls inside it. Projects may place the BNB Chain logo on their own website and social posts **when identifying that the project is on BNB Chain**, provided:

1. The wording is **"Powered by"**, **"Available on"**, or **"Building on"** BNB Chain
2. The BNB Chain handle is tagged on socials
3. It is used **solely to identify** that the project is on BNB Chain — nothing more

**wRATR is deployed on BNB Smart Chain, so this identification is factual.** Verified on chain 2026-10-02:

| | |
|---|---|
| Contract | `0xDeb6265cEE49CC277A938452DEDAb2B8774210d1` |
| Name / symbol | Wrapped Ratatoskr / wRATR |
| Decimals | 8 |
| Chain id | 56 (BNB Smart Chain) |

---

## ❌ Prohibited, per their guidelines

- Altering shape, form or colour
- Adding outlines, shadows or gradients
- Stretching beyond original proportions
- **Placing against busy or low-contrast backgrounds**
- Anything implying endorsement, sponsorship or partnership

**That fourth one is why the BNB banner differs from the others.** The Alephium and Base variants hang their mark as a pendant on the illustrated panel. The BNB variant does **not** — an illustrated scene with a squirrel, a seal and a cord is a busy background by any reading. Its mark sits instead on plain parchment with the required wording. See [`banners/README.md`](../../../banners/README.md).

---

## Files in this folder

| File | Description | When to use |
|---|---|---|
| `BNB_Chain_Symbol_Black.png` / `.svg` | Black symbol | **On light backgrounds** — what the parchment banner uses |
| `BNB_Chain_Symbol_White.png` / `.svg` | White symbol | On dark backgrounds |
| `BNB_Chain_Symbol_Yellow.png` / `.svg` | Brand yellow `#f0b90b` | Where the brand colour should show and contrast allows |

All three are the **symbol**, not the wordmark lockup. SVG is 96 × 96 viewBox.

Permitted symbol contexts per their guidelines: *buttons, profile picture, an expression for the BNB Token, or as an icon.*

---

## Brand colour

| Token | Hex | Notes |
|---|---|---|
| BNB Yellow | `#f0b90b` | CMYK 0/100/26/0 · RGB 240/185/11 · Pantone 116C |

⚠️ **Yellow on cream parchment is low contrast**, which their guidelines prohibit. Use the **black** symbol on parchment.

---

## Approval status

| Date | Status |
|---|---|
| 2026-10-02 | Request **drafted, not yet sent.** Covers the pendant-style use that falls outside the carve-out. The compliant "Available on BNB Chain" banner needs no approval and is in use. |

There is **no published approval process** — no dedicated email, no form, no stated timeline. The route is their general contact form or comms/legal. What they ask for is the proposed use plus how it will be distributed.

**When approval is obtained, save the written response in this folder** — that correspondence is this mark's license, and it is the only artifact that makes the restricted uses legitimate.

---

## Updating these mirrored files

```bash
DST="logos/side-coins/bnb"
for C in Yellow Black White; do
  for EXT in svg png; do
    curl -sL "https://www.bnbchain.org/images/brand-guidelines/$EXT/BNB%20Chain_Symbol_$C.$EXT" \
         -o "$DST/BNB_Chain_Symbol_$C.$EXT"
  done
done
```

**Re-read the guidelines page when refreshing** — these terms are permission-based, so they can change in a way a license file cannot.
