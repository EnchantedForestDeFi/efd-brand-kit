# Banners

Wide promotional art, for ecosystem directories, listings and social headers.

Added 2026-10-02. Before that the kit had **no banners at all**, while five finished ones sat outside it on a workstation — which is the drift this tree exists to stop. If a banner ships, it lives here.

---

## The rule: ONE chain per banner. Never stacked.

**Operator ruling, 2026-10-01.** wRATR is on three chains, so there are three banners — not one banner carrying three marks.

Why, in the order the reasons actually matter:

1. **The surface picks the audience.** An Alephium directory listing wants the Alephium mark. Base and BNB marks there are noise to that reader, and on a BNB surface the Alephium mark is equally off.
2. **"A nod, not a billboard."** One small mark reads as a nod to the chain. Three stacked becomes a chain-support badge — the thing the eye lands on first, which is the opposite of the intent.
3. **The art's own logic.** Ratatoskr is the messenger, carrying a message *to* somewhere. One pendant reads as a destination. Three reads as a keyring.
4. **`logos/side-coins/` is already one folder per chain.** This mirrors a structure that was already here.

---

## Files

| File | Chain | Mark treatment |
|---|---|---|
| `chains/banner-parchment-alephium-2720x860.png` | Alephium | Round pendant hanging from the scroll's seal |
| `chains/banner-parchment-base-2720x860.png` | Base | **Square** tag in the same pendant position |
| `chains/banner-parchment-bnb-2720x860.png` | BNB Smart Chain | **Not a pendant** — mark on plain parchment with required wording |

All three are 2720 × 860 (ratio 3.163). For a 3.00 target such as 1200 × 400, **pad vertically rather than crop** — the parchment is full-bleed, so a crop takes real pixels while 47px of edge-matched padding takes none.

---

## Why the three differ — each difference is somebody's rule, not a style choice

**Alephium — a round pendant.** Their glyph already sits inside a circle (`Alephium-Logo-round.svg` is their token-context asset), so a disc hanging from the seal is their mark in its own shape. Geometry is measured from `logos/wratr/wratr-mark-1024.png`, which carries this pendant natively: seal radius ratio gives scale 0.62, disc 29px, 8.1px gap between seal and disc edge.

**Base — a square.** Their brand guide fixes the mark as a blue square at `#0000FF`. Rounding it into a disc to match Alephium would alter the mark, so it stays square. Same bail, same position, different shape.

**BNB — no pendant at all.** Their guidelines prohibit placing the symbol "against busy or low-contrast backgrounds," and the illustrated panel is busy. So the BNB banner leaves the panel alone and puts the black symbol on the plain parchment band below the runic rule, beside the wording **"Available on BNB Chain"** — which is what their standing carve-out permits without case-by-case approval.

**Read that last one as the pattern, not the exception:** the mark goes where the owning project's rules allow it, and the composition bends, not their mark.

---

## Source art

Built on `banner-CGK-PARCHMENT-2720x860.png`, originally produced for a CoinGecko listing application. The CoinGecko name appears nowhere in the art and the versionless variants carry no version stamp, so it is general-purpose.

⚠️ **There is an older variant of the same filename in a `banners-OLD-20260808` folder outside this repo. It is a different image, not a copy.** Measured 2026-10-02: the two differ only in text on the right-hand side — 82 small clusters, all in three text bands, nothing in the illustrated panel. Both carry the same wax-seal rosette on the scroll; **neither ever had a chain mark.** The chain pendants here are new work, not a restoration.

---

## Regenerating

The compositing is parameterised — scale, offset and mark are inputs, so a new chain variant is one run once that chain's mark is in `logos/side-coins/`. Keep the geometry constants together with the seal measurement they derive from; they are not magic numbers, they are a ratio between two drawings.
