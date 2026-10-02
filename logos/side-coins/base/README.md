# Base Brand Assets

**Source:** [github.com/base/brand-kit](https://github.com/base/brand-kit)
**Upstream license:** ⚠️ **none declared** — the repo ships **no LICENSE file**. Terms live in their brand guide, mirrored here as [`UPSTREAM-BRAND-GUIDE.pdf`](UPSTREAM-BRAND-GUIDE.pdf)
**Pulled:** 2026-10-02
**EFD use case:** referenced operationally because EFD operates the **wRATR bridge to Base**

---

## ⚠️ NOT under this repo's CC-BY 4.0 license

These files are **owned by Base** (Coinbase / the OP Stack Superchain). The CC-BY 4.0 declared at this repo's root does NOT extend to them.

Unlike Alephium — which ships an explicit LGPL-3.0 file — **Base declares no license at all in its brand-kit repo.** That is not permission by omission. Treat the brand guide PDF as the governing terms, and when in doubt pull from upstream rather than relying on this mirror.

---

## 🚨 The naming trap — "Basemark" is NOT the symbol

This cost an hour on 2026-10-02 and is the reason this section exists.

| File | Actual dimensions | What it really is |
|---|---|---|
| `Base_basemark_*` | **1281 × 419** | the **wordmark lockup** — glyph *plus* "Base" text |
| `Base_square_*` | **1281 × 1281** | the **symbol** — the solid square, their actual mark |

The name says "mark"; the asset is a lockup. **If you want the symbol, take `Base_square_*`.** Measured, not read off the filename.

---

## Files in this folder

### The symbol (use this for icons, pendants, token contexts)

| File | Description | When to use |
|---|---|---|
| `Base_square_blue.png` | Solid square, `#0000FF` | **Default.** Light backgrounds, and anywhere the brand colour should show |
| `Base_square_white.png` | Solid square, `#FFFFFF` | Dark backgrounds — their sanctioned dark-mode variant |

### The lockup (symbol + wordmark)

| File | Description |
|---|---|
| `Base_basemark_blue.png` / `.svg` | Lockup in brand blue |
| `Base_basemark_white.png` / `.svg` | Lockup in white, for dark backgrounds |

### Reference

| File | Purpose |
|---|---|
| `UPSTREAM-README.md` | Base's own brand-kit README |
| `UPSTREAM-BRAND-GUIDE.pdf` | **The governing terms** — there is no LICENSE file, so this is it |
| `UPSTREAM-EDITORIAL-STYLE-GUIDE.md` | Their editorial/voice guide |

---

## Base's official usage guidelines (per their brand guide)

> The Base logo is a **blue square**, and the colour is **always `#0000FF`**. In dark mode it changes to **pure white `#FFFFFF`**.

Their brand guide frames itself as "a starter kit with non-negotiables for recognizability and flex zones that invite the community to remix" — so the shape and the colour are the fixed part.

**Consequence for our artwork:** the Base mark stays a **square**. It does not get rounded into a disc to match Alephium's pendant, because Alephium's glyph already sits in a circle and Base's does not. See [`banners/README.md`](../../../banners/README.md).

---

## Brand colour

| Token | Hex | Use |
|---|---|---|
| Base Blue | `#0000FF` | The mark, always, on light surfaces |
| White | `#FFFFFF` | The mark in dark mode |

---

## Use in EFD contexts

1. **wRATR bridge to Base** — Base is a destination chain for wRATR
2. **Chain-variant banner** — `banners/chains/banner-parchment-base-2720x860.png`
3. **"Available on Base" identification** on pages covering the Base deployment

**wRATR on Base is a real deployment** — the token contract is verifiable on BaseScan. Identification use is accurate, not aspirational.

---

## Updating these mirrored files

```bash
DST="logos/side-coins/base"
for f in Basemark/Digital/Base_basemark_blue.png Basemark/Digital/Base_basemark_white.png \
         TheSquare/Digital/Base_square_blue.png TheSquare/Digital/Base_square_white.png; do
  curl -sL "https://raw.githubusercontent.com/base/brand-kit/main/logo/$f" -o "$DST/$(basename $f)"
done
curl -sL "https://raw.githubusercontent.com/base/brand-kit/main/README.md" -o "$DST/UPSTREAM-README.md"
curl -sL "https://raw.githubusercontent.com/base/brand-kit/main/guides/brand-guide.pdf" -o "$DST/UPSTREAM-BRAND-GUIDE.pdf"
```

Re-check quarterly, and **re-check the licence position specifically** — if Base ever adds a LICENSE file, that supersedes the PDF and this README should say so.
