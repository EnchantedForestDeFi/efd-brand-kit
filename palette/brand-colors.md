# EFD Brand Color Palette

**Status:** Locked 2026-05-05 (canonical brand palette — Palette A).
**Source:** Internal `efd_brand_asset_spec.md` Section 1.

This palette is used for **brand identity** surfaces — logos, hero art, whitepaper, press kit, social graphics, character artwork.

For **UI surfaces** (Qt wallet, web app, explorer, bridge UI), the **UI palette (Palette B)** is used instead. Both palettes share an orange accent family as visual through-line.

---

## Brand Mark Palette (Palette A — locked)

| Role | Hex | RGB | Use |
|---|---|---|---|
| **Brand primary** | `#5B3A29` | 91, 58, 41 | Logo body. Body text on parchment backgrounds. The "tree-trunk umber" — squirrel body in the Ratatoskr mark. |
| **Brand accent** | `#D7882F` | 215, 136, 47 | Pull-quotes, taglines, accent strokes. The "ember orange" — messenger pop. |
| **Brand accent 2** | `#C9A227` | 201, 162, 39 | Alternative accent (use sparingly). "Rune gold." |
| **Brand secondary** | `#2E5339` | 46, 83, 57 | Section dividers. The "forest green" — Enchanted Forest DeFi tie-in. |
| **Brand bg (light)** | `#EDE2C5` | 237, 226, 197 | Parchment background. Light-mode default. |
| **Brand bg (dark)** | `#1A1812` | 26, 24, 18 | Dark-mode background. Used for dark logo variants + dark social media + dark Discord embeds. |
| **Brand danger** | `#7A2A1F` | 122, 42, 31 | Warnings only — never primary. The "smoky red" — root-level alerts. |
| **Brand text on light** | `#5B3A29` | 91, 58, 41 | Same as primary. |
| **Brand text on dark** | `#EDE2C5` | 237, 226, 197 | Parchment-cream text on dark backgrounds. |

---

## Character-specific palette extensions

Individual characters have their own canonical color signatures (used for character artwork only, not for the brand mark). Per design constraint: **no two characters share a dominant color palette**.

| Character | Primary | Secondary | Notes |
|---|---|---|---|
| **Heimdall** | warm browns / golds | helm-bronze | Watcher of Bifröst |
| **Tomte** | grey-brown homespun | oxblood cap | Domestic tinkerer |
| **Forseti** | moss-green cloak | — | Judge (Glitnir) |
| **Vár** | charcoal-grey | bone-white linen | Oath-Keeper |
| **Idunn** | russet, ochre, deep-amber | red-gold | Orchard steward (autumn palette) |
| **Freyja** | gold (warm — amber, honey, antique) | deep red (garnet, ember, blood-orange) | Vanaheim co-lead, fierce wealth |
| **The Norns (triptych)** | mossy greens (Urðr) / silver-grey (Verðandi) / pale ice-blue (Skuld) | luminous gold thread | Past / present / future |
| **Hel** | cold neutrals (grey, black, bone-white) | muted red OR purple accent | Half-beauty, half-cold-dead. NEVER gold. |
| **Skadi** | snow-white, pale ice-blue, cold steel-grey | deep evergreen, dark wool, weathered leather | Mountains + winter. Iron, blued steel — never gold. |
| **Draupnir** (object, not character) | rich gold (ring) | red-gold (drops) | Treasury drip mechanism |

---

## Usage guidelines

- **For listing / social media / press / whitepaper:** use Palette A (brand mark) — colors above
- **For Qt wallet UI / web UI / explorer UI:** use Palette B (UI palette) — see internal `efd_brand_asset_spec.md` Section 1.2
- **Through-line:** orange accent family (`#D7882F` brand / `#FF9328` UI) connects both palettes visually
- **Dark mode:** `Brand bg (dark)` (`#1A1812`) replaces parchment in dark-mode contexts

---

## Programmatic access (future)

Future addition: `brand-colors.json` for design-tool consumption and CSS-variable export. Not yet shipped.
