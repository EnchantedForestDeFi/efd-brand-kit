# EFD Typography

**Status:** Locked 2026-05-05.
**Source:** Internal `efd_brand_asset_spec.md` Section 2.

---

## Type system overview

EFD uses a **three-font system**:

| Role | Primary | Fallback stack |
|---|---|---|
| **Display (headings, hero)** | Cinzel | `Cinzel, "Cormorant Garamond", "Times New Roman", serif` |
| **Body (reading surfaces)** | Inter | `Inter, "IBM Plex Sans", "Helvetica Neue", Arial, sans-serif` |
| **Code (mono)** | JetBrains Mono | `"JetBrains Mono", "IBM Plex Mono", "SF Mono", Consolas, monospace` |

All three are SIL Open Font License — free for commercial use including embedding.

---

## Cinzel (display)

**Use for:** Whitepaper cover headline, press kit tagline, hero website title, character name labels.

- **Weight:** Regular (400) for body headings; SemiBold (600) for impact
- **Size guidance:** H1 = 36-48pt display · H2 = 24-32pt · H3 = 18-22pt
- **License:** [SIL Open Font License 1.1](https://scripts.sil.org/OFL)
- **Source:** [Google Fonts — Cinzel](https://fonts.google.com/specimen/Cinzel)

---

## Inter (body)

**Use for:** Whitepaper body, press kit body, web copy, all reading surfaces.

- **Weights:** Regular (400) body · Medium (500) emphasis · SemiBold (600) strong
- **Size guidance:** Body 11-13pt print / 14-16px web · small text 9-10pt / 12-13px
- **License:** [SIL Open Font License 1.1](https://scripts.sil.org/OFL)
- **Source:** [Google Fonts — Inter](https://fonts.google.com/specimen/Inter) · [rsms.me/inter](https://rsms.me/inter/)

---

## JetBrains Mono (code)

**Use for:** Code blocks in whitepaper, address strings on website, terminal output in setup guides.

- **Weight:** Regular (400)
- **Features:** Ligatures, programming-friendly character distinction (e.g., `0` vs `O`, `1` vs `l`)
- **License:** [SIL Open Font License 1.1](https://scripts.sil.org/OFL)
- **Source:** [JetBrains Mono](https://www.jetbrains.com/lp/mono/) · [GitHub](https://github.com/JetBrains/JetBrainsMono)

---

## PDF / embedding requirements

- **All PDFs MUST embed fonts** — don't rely on the reader's system fonts
- **Web pages MAY use system fallbacks** for performance — the Cinzel/Inter pairing has acceptable system-font fallbacks in any modern browser
- For best results, serve from a CDN (Google Fonts) or self-host the OFL files

---

## Bundled font files (future)

Future addition: `fonts/` subfolder containing the OFL fonts for offline / self-hosting use. Not yet shipped in this repo — pull from upstream OFL sources for now.
