# RATR Network-Color Variants

Same wallet icon (256×256 rope-cartoon medium), retinted per Ratatoskr network so the user can tell at a glance whether they're on mainnet vs testnet vs devnet vs regtest.

These render in the Qt wallet title bar / system tray when the daemon is running on the corresponding network.

---

## Files

| File | Network | Color | Tint applied |
|---|---|---|---|
| `ratatoskr256-mainnet.png` | mainnet | Brown / amber / canonical brand colors | Default brand palette (no tint shift) |
| `ratatoskr256-testnet.png` | testnet | Blue | Hue-shifted to blue family |
| `ratatoskr256-devnet.png` | devnet | Different blue / purple | Different hue from testnet to distinguish |
| `ratatoskr256-regtest.png` | regtest | Yet another color | Distinct from above 3 |

## Where these ship

These get embedded in the Qt wallet at build time per `network-style-check` validation — see `ratatoskr/src/qt/networkstyle.cpp`.

## Source

Generated from the canonical rope-cartoon mainnet PNG by hue-shifting (see `ratatoskr/doc/brand/source/icon-preview/network-style-check/build-previews.py`).

To re-render after a base icon update:

```bash
cd ratatoskr/doc/brand/source/icon-preview
python build-previews.py
```

## License

CC-BY 4.0 per repo `LICENSE`.
