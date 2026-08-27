# Bundled Fonts for Kaalam

This directory contains fonts bundled with Kaalam for Tamil rendering, PDF export, and deterministic chart typography.

## What's Included

Tamil fonts:
- `TiroTamil-Regular.ttf` for flagship Tamil cover and section display typography
- `NotoSerifTamil-Regular.ttf` for flagship Tamil narrative/body typography
- `NotoSerifTamil-SemiBold.ttf` for flagship Tamil narrative emphasis and section headings
- `NotoSansTamil-Regular.ttf`
- `NotoSansTamil-Bold.ttf`
- additional Noto Sans Tamil width and weight variants, including:
  - `NotoSansTamil-Medium.ttf`
  - `NotoSansTamil_SemiCondensed-Regular.ttf`
  - `NotoSansTamil_SemiCondensed-SemiBold.ttf`

Multilingual UI fonts:
- `NotoSansDevanagari-Regular.ttf`, `Medium`, `SemiBold`, `Bold` for Hindi
- `NotoSansTelugu-Regular.ttf`, `Medium`, `SemiBold`, `Bold` for Telugu
- `NotoSansKannada-Regular.ttf`, `Medium`, `SemiBold`, `Bold` for Kannada
- `NotoSansMalayalam-Regular.ttf`, `Medium`, `SemiBold`, `Bold` for Malayalam

Chart label fonts:
- `Cinzel[wght].ttf`
- `CormorantGaramond[wght].ttf`
- `PlayfairDisplay[wght].ttf`
- `Outfit[wght].ttf`

Data and degree fonts:
- `JetBrainsMono-Regular.ttf`
- `JetBrainsMono-Bold.ttf`

## Purpose

These bundled fonts ensure:

1. Zero setup for users on Windows, macOS, and Linux.
2. Consistent Tamil, Hindi, Telugu, Kannada, and Malayalam rendering across the app and exported reports.
3. Deterministic display, narrative, and compact Indic typography across flagship PDFs.
4. Predictable fallback behavior when a machine does not have the preferred fonts installed system-wide.

## How It Works

Kaalam registers bundled `.ttf` files from this directory at startup.

The bundled families are then used in two places:

1. PDF and export pipelines, especially for Tamil text.
2. Qt chart rendering, including premium large-orb labels and compact readability-first orb labels.

## Developer Notes

If you add another bundled font:

1. Place the `.ttf` file in this directory.
2. Confirm the font family appears after startup through the shared bundled-font registration path.
3. Update any relevant font stacks and tests.

When packaging the application, include:

```python
datas = [
    ("kaalam/resources/fonts/*.ttf", "kaalam/resources/fonts"),
]
```

## License

The bundled fonts are sourced from Google Fonts and JetBrains Mono. They are distributed under the SIL Open Font License 1.1.
