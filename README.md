# Yova's Unit Converter

A fast, self-contained unit converter in a single HTML file — no build step, no dependencies, no server. Open it in any browser and convert across **17 categories and 200+ units**, in both directions.

Inspired by the classic [Convert for Windows](https://joshmadison.com/convert-for-windows/) by Josh Madison.

<img width="782" height="781" alt="Screenshot 2026-07-08 125758" src="https://github.com/user-attachments/assets/d79cf97e-63f7-4249-8805-fe176d5fc087" />

## Features

- **17 categories** — Acceleration, Angle, Area, Density, Distance, Flow, Force, Light, Mass, Power, Pressure, Speed, Temperature, Time, Volume, Volume (Dry), and Custom
- **Bidirectional conversion** — type in either the Input *or* Output field and the other updates instantly; no need to swap first
- **One-click reverse** — the swap button exchanges the input/output units *and* their values
- **Custom units** — define your own relationship (`1 A = X B`) and convert both ways; swapping inverts the factor automatically
- **Proper temperature handling** — Celsius, Fahrenheit, Kelvin, Rankine, Réaumur, Delisle, Newton, and Rømer via exact non-linear formulas, not lookup factors
- **Adjustable precision** — 4 to 12 significant digits
- **Live factor readout** — the status bar always shows the current relationship, e.g. `1 Mile = 1.609344 Kilometers`
- **Robust input** — accepts commas and scientific notation; very large/small results switch to exponential form
- **Accessible** — keyboard navigation in the unit lists (arrows / Home / End), visible focus states, ARIA roles, and `prefers-reduced-motion` support
- **Responsive** — works down to small phone screens
- **Animated logo** — a lightweight 3D particle-orb rendered on `<canvas>`, adapted to the site palette

## Getting started

No installation required.

1. Download `yova-unit-converter.html`
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge)

That's it. The file works offline; the only optional network request is the fallback web font.

To host it (e.g. GitHub Pages), just serve the file:

```
your-repo/
├── yova-unit-converter.html   # the entire app
├── BoisterousSignatureScript.woff2   # optional — see Fonts below
└── README.md
```

## Usage

1. Pick a category tab (e.g. **Distance**)
2. Select the input unit in the left list and the output unit in the right list
3. Type a value in **Input** — the result appears in **Output**
4. Or type in **Output** to convert in reverse
5. Hit the round **Swap** button to flip the units and values entirely

### Custom conversions

Open the **Custom** tab, name your two units, and set the factor (`1 Widget = 2.5 Gadgets`). Both fields then convert bidirectionally, and Swap inverts the factor for you.

## Fonts

The branding uses **Boisterous Signature Script** by [Dhan Studio](https://www.myfonts.com/collections/boisterous-script-font-dhanstudio), which is a **commercial font and is not bundled** with this project. The stylesheet loads it in this order:

1. Your locally installed copy of the font, if present
2. A font file placed next to the HTML (`BoisterousSignatureScript.woff2`, `.woff`, `.ttf`, or `Boisterous.otf`)
3. Fallback: [Allison](https://fonts.google.com/specimen/Allison) (Google Fonts, free) — a similar signature-style script

If you own a webfont license for Boisterous, drop the font file into the same folder as the HTML and it will be used automatically. Do not commit the commercial font file to a public repository unless your license permits redistribution.

## Color palette

| Role | Hex |
|---|---|
| Charcoal — header, footer, anchors | `#1F2328` |
| Forest — primary interactive | `#3C4A3F` |
| Sage — borders, muted text | `#A9B7A6` |
| Cream — page background | `#E7E2D9` |
| Terracotta — accent, swap button | `#C97C5D` |

## Accuracy notes

- Linear categories convert through an exact base unit (e.g. meters, kilograms, pascals) using published definition-based factors (`1 in = 0.0254 m`, `1 lbf = 4.4482216152605 N`, etc.)
- Temperature uses exact conversion formulas between scales
- Mach is based on the standard atmosphere (340.2933 m/s); month/year use calendar averages (Gregorian mean year = 31,556,952 s)
- Results are rounded for display only — internal math is full double precision

## Credits

- Concept and category layout inspired by **[Convert for Windows](https://joshmadison.com/convert-for-windows/)** by **Josh Madison** — a beloved freeware classic since 1996
- Boisterous Signature Script font by **Dhan Studio**
- Allison fallback font via **Google Fonts**

## License

The code in this repository is released under the [MIT License](LICENSE). Third-party fonts remain under their own licenses (see Fonts above).
