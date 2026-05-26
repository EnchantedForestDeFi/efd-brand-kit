# RATR Wallet Icon Family

The icon family **actively used by the Ratatoskr Qt wallet** (v1.0.0-rc4 and forward). Style: rope-cartoon — the candidate-1 medium-variant from the May 2026 brand selection.

**This is DIFFERENT from the marketing/listing mark** (the illuminated manuscript in `../`). The wallet icon family is more graphic / lower-detail because it needs to read at 16×16 pixels in OS chrome (taskbar, dock, alt-tab, etc.). The illuminated mark has too much detail for those sizes.

---

## Files

| File | Use | Source |
|---|---|---|
| `ratatoskr.ico` | Windows multi-resolution icon (16/32/48/64/128/256 embedded) | Built from PNG family |
| `ratatoskr.icns` | macOS multi-resolution icon | Built from PNG family |
| `ratatoskr16.png` | 16×16 — taskbar / tray | — |
| `ratatoskr32.png` | 32×32 — small UI contexts | — |
| `ratatoskr48.png` | 48×48 — Windows medium icon | — |
| `ratatoskr64.png` | 64×64 — Windows large icon | — |
| `ratatoskr128.png` | 128×128 — high-DPI taskbar | — |
| `ratatoskr256.png` | 256×256 — Windows extra-large icon | — |
| `ratatoskr_master_1024.png` | 1024×1024 master raster — source for re-rendering smaller sizes | — |

## Where these ship

- `share/pixmaps/ratatoskr.ico` in the Ratatoskr chain repo (used by Windows installer + .exe icon)
- `share/pixmaps/ratatoskr.icns` (used by macOS .app bundle)
- `share/pixmaps/ratatoskrXXX.png` (used by Linux .desktop file)

## Re-rendering at smaller sizes

If you need a non-standard size:

```python
from PIL import Image
src = "ratatoskr_master_1024.png"
Image.open(src).resize((SIZE, SIZE), Image.LANCZOS).save(f"ratatoskr-{SIZE}.png")
```

## Source provenance

Selected from 6 candidate styles during May 2026 brand-direction work. The full candidate set + working files remain in the `ratatoskr/doc/brand/source/` folder of the chain repo as design history (not redistributed here).

The "rope-cartoon medium" variant was chosen for the wallet icon because it scales cleanly to 16×16 (silhouette test passes) while remaining visually distinctive at 256×256.

## License

CC-BY 4.0 per repo `LICENSE`.
