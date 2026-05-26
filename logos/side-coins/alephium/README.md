# Alephium Brand Assets

**Source:** [github.com/alephium/alephium-brand-guide](https://github.com/alephium/alephium-brand-guide)
**Upstream license:** **GNU Lesser General Public License v3.0 (LGPL-3.0)** — see [`UPSTREAM-LICENSE-LGPL-3.0`](UPSTREAM-LICENSE-LGPL-3.0)
**Pulled:** 2026-05-26 (this date)
**EFD use case:** referenced operationally because EFD operates the **wRATR bridge to Alephium**

---

## ⚠️ NOT under this repo's CC-BY 4.0 license

The files in this folder are **owned by the Alephium project** and licensed under **LGPL-3.0**, NOT under the EFD Brand Kit's CC-BY 4.0 license. The CC-BY 4.0 declared at this repo's root does NOT extend to these assets.

If you use these files, you must:
1. **Attribute Alephium** as the source (link to upstream repo or alephium.org)
2. **Comply with LGPL-3.0** for any modifications you make to these specific files
3. **Not use these for derivative branding** that could be mistaken for official Alephium communications

For original Alephium assets, always pull from upstream first — these are mirrored for EFD's convenience but the canonical source is `alephium/alephium-brand-guide`.

---

## Files in this folder

### SVG (vector, preferred when supported)

| File | Description | When to use |
|---|---|---|
| `Alephium-Logo-round.svg` | Round token logo (white glyph in black circle) | **Token contexts** (CoinMarketCap, CoinGecko, token-list displays) |
| `Alephium-Logo-W.svg` | White glyph (square layout, no frame) | **On dark backgrounds** (Alephium's recommended default) |
| `Alephium-Logo-B.svg` | Black glyph (square layout, no frame) | On light backgrounds |
| `Alephium-Logo-W-text.svg` | White glyph + wordmark | ⚠️ Alephium discourages "wordmark alone" use — only use this complete logo+text composite |
| `Alephium-Logo-B-text.svg` | Black glyph + wordmark | ⚠️ Same caveat as W-text |

### PNG (raster)

Same five logo variants in `.png` form for contexts where SVG isn't supported.

### Reference

| File | Purpose |
|---|---|
| `UPSTREAM-README.md` | Alephium's official brand-guide README (their usage guidelines) |
| `UPSTREAM-LICENSE-LGPL-3.0` | The LGPL-3.0 license text |
| `alephium-brand-colors.png` | Alephium's official background/foreground variant guide image |

---

## Alephium's official usage guidelines (per their README)

Direct quotes / paraphrase from upstream:

> **"To simplify and consolidate our branding ahead of future evolutions, we recommend using the white logo on a black background as the default."**

> **"When used as a token logo (e.g., on platforms like CoinMarketCap or CoinGecko), please use the round logo."**

> **"The logo alone is the preferred option. Please do not use the wordmark alone."**

> Font: **Inter** typeface family — open-source, available at https://rsms.me/inter/

---

## Alephium brand color palette (what it actually is)

**The Alephium brand is intentionally MONOCHROME — pure black and pure white only.**

| Token | Hex | Use |
|---|---|---|
| Alephium Black | `#000000` | Default background, glyph fill on light surfaces |
| Alephium White | `#FFFFFF` | Background on inverse, glyph fill on dark surfaces |

There is **no "Alephium blue"** — despite frequent assumptions to the contrary. The brand is minimalist by deliberate design.

---

## Use in EFD contexts

EFD references Alephium operationally in:

1. **wRATR bridge** — Alephium is the destination chain; bridge UI shows ALPH alongside wRATR
2. **wRATR token-list submission** (alephium/token-list PR) — submission goes to Alephium ecosystem
3. **Elexium DEX integration** (LP, gauge votes, bribes) — Elexium runs on Alephium
4. **Bridge documentation** — explaining the cross-chain flow
5. **Press / partnership materials** — when discussing the EFD ↔ Alephium relationship

**Recommended logo per context:**

| Context | Use |
|---|---|
| Token-list registry submissions | (own native logo only — Alephium logo NOT included in submission) |
| Bridge UI showing ALPH | `Alephium-Logo-round.svg` (token logo) |
| "Powered by Alephium" footer/badge | `Alephium-Logo-W.svg` on dark or `Alephium-Logo-B.svg` on light |
| Side-by-side product comparison | Whatever matches the page palette |
| Marketing about the bridge | Use Alephium's recommended default (white-on-black) |

---

## Updating these mirrored files

When Alephium updates their brand kit, this folder may drift out of date.

To refresh:

```bash
DST="C:/src/efd-brand-kit/logos/side-coins/alephium"
for f in Alephium-Logo-round.svg Alephium-Logo-W.svg Alephium-Logo-B.svg \
         Alephium-Logo-W-text.svg Alephium-Logo-B-text.svg; do
  curl -sL "https://raw.githubusercontent.com/alephium/alephium-brand-guide/master/logos/svgs/$f" -o "$DST/$f"
done
# Repeat for /logos/pngs/ if PNGs need refresh
curl -sL "https://raw.githubusercontent.com/alephium/alephium-brand-guide/master/README.md" -o "$DST/UPSTREAM-README.md"
```

Periodic check (quarterly?) against the upstream repo is reasonable.
