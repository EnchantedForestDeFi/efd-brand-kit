# wRATR Logos (Wrapped RATR on Alephium)

Logo family for **wRATR** — the Alephium-side wrapped representation of native RATR. Used in DeFi contexts (Elexium DEX, alephium/token-list, wRATR pair displays).

---

## Design: the double-sealed scroll

The wRATR mark is built on the canonical illuminated-manuscript RATR mark (red squirrel + scroll + Celtic frame on aged parchment). The distinguishing element is the **scroll's seals**:

- **Original horseshoe seal** — RATR's own mark of authenticity, present on the native scroll
- **Alephium round-logo seal** — composited beneath the original, hanging from the same cord, indicating the scroll has been countersigned by Alephium (i.e., wrapped onto the Alephium chain)

The narrative read: *Ratatoskr the messenger carries a scroll that has been sealed twice — once by Ratatoskr itself (the original assertion of value), and once by Alephium (the wrapping authority). Together, the double seal is the wRATR.*

This pattern is intended to extend to future wrapped tokens (wKRGN, wOTHER) where the "second seal" identifies the destination chain.

---

## Files

| File | Use case |
|---|---|
| `wratr-mark-1024.png` | Master raster, transparent BG. Source for all downscales. |
| `wratr-mark-512.png` | High-res web / press |
| `wratr-mark-256.png` | **Standard listing / web / social. Used in alephium/token-list PR submissions.** |
| `wratr-mark-128.png` | Discord, smaller web contexts |
| `wratr-mark-64.png` | Favicon, tiny contexts (Alephium seal merges into silhouette at this size; OK — the squirrel-on-branch shape carries recognition) |
| `dark-variants/` | (future) — same family on dark background |

---

## Token-list logoURI

For Alephium ecosystem registries, the canonical URL is:

```
https://raw.githubusercontent.com/EnchantedForestDeFi/efd-brand-kit/main/logos/wratr/wratr-mark-256.png
```

Stable, version-controlled, unaffected by future RATR-chain or EFD-website changes.

---

## License + attribution

### The base mark (squirrel, scroll, Celtic frame, parchment)

CC-BY 4.0 — per repo `LICENSE`. Credit:

```
wRATR logo from EFD Brand Kit (CC-BY 4.0)
https://github.com/EnchantedForestDeFi/efd-brand-kit
```

### The embedded Alephium round-logo seal

The Alephium round logo composited onto the scroll is **owned by the Alephium project** and licensed under **LGPL-3.0**. Source: [`alephium/alephium-brand-guide`](https://github.com/alephium/alephium-brand-guide). Mirror copy at [`../side-coins/alephium/`](../side-coins/alephium/) with full LGPL-3.0 attribution.

If you derive further work from these wRATR PNGs, you must:
- Comply with CC-BY 4.0 for the base illustration
- Comply with LGPL-3.0 for the embedded Alephium-logo portion
- Attribute both projects appropriately

In practice, since these are static PNGs ready for downstream use (token-list submissions, UI display), the LGPL obligation is satisfied by linking back to Alephium's brand-guide repo.

---

## Source provenance

The base illuminated-manuscript illustration was produced via AI image generation, refined and selected on 2026-05-26. The Alephium round logo was composited programmatically (Python + Pillow) and iteratively positioned through multiple refinement passes to land at the final position.

**Final composition parameters (v3.14, locked 2026-05-26):**
- Position: center (691, 437) in 1024×1024 canvas
- Size: 45×45 pixels
- Compositing approach: Python + Pillow `paste()` with alpha mask, source from `Alephium-Logo-round.png` (see [`../side-coins/alephium/`](../side-coins/alephium/))
- Reads as: Alephium glyph hanging inline below the existing horseshoe seal on the scroll's tied cord — twin seals on one cord, like a notarized document with both signers' stamps

Higher-resolution variants (2048, 4096) can be produced by re-running the composition pipeline on a higher-resolution base image when one exists. The script is deterministic — same coords/size produce identical output.
