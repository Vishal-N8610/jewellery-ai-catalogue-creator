# Jewellery AI Catalogue Creator

> AI-powered background removal and catalogue image generation pipeline for jewellery products. Built with Streamlit + rembg (U2Net) + PIL.

## Overview

A production-ready Streamlit app that takes raw jewellery product photos and generates clean, catalogue-ready images with white/gold backgrounds, proper branding, and structured product annotations — all in one click.

Built for **WONDR Diamonds Private Limited** to automate and standardise jewellery product photography post-processing.

## Features

- **AI Background Removal** — Uses rembg (U2Net deep learning model) to cleanly remove backgrounds from jewellery images
- **Smart Post-Processing** — Multiple algorithms to suppress props, paper rolls, fabric backgrounds, text artifacts, and residual noise
- **Object Eraser Tool** — Manual colour-based eraser to remove specific props or background elements interactively
- **Brand-Specific Backgrounds** — Applies correct background colour based on gold type (22K Yellow Gold, 22K Rose Gold, 18K White Gold, etc.)
- **Product Annotation Panel** — Right-side panel for capturing Design Code/SKU, Gold Weight, Diamond CT, Gem Stone details, and Notes
- **Batch Export** — Download all processed images as a ZIP file

## Tech Stack

- **UI Framework:** Streamlit
- **Background Removal:** rembg (U2Net model)
- **Image Processing:** PIL / Pillow, NumPy
- **Post-Processing Algorithms:**
  - `suppress_support_objects()` — removes props/stands
  - `suppress_fabric_dark_bg()` — cleans fabric backgrounds
  - `suppress_text_dark_bg()` — removes text/label artifacts
  - `erase_residual_background()` — cleans remaining BG pixels
  - `restore_bright_pixels()` — recovers overexposed gem highlights
  - `defringe_dark_edges()` — smooths dark edge fringing
  - `clear_enclosed_dark_gaps()` — fills dark gaps in alpha
  - `sharpen_alpha_edges()` — sharpens final edge mask
  - `restore_enclosed_dark_stones()` — recovers dark stones (black diamonds, etc.)

## Workflow

1. Upload raw jewellery image(s) via the Streamlit UI
2. AI model removes background using U2Net
3. Post-processing pipeline cleans artifacts and refines alpha mask
4. Select Gold Type → background colour is applied automatically
5. Fill in product metadata (SKU, weights, stones)
6. Download individual images or full batch as ZIP

## Gold Type Backgrounds

| Gold Type           | Background Colour |
|---------------------|-------------------|
| 22K Yellow Gold     | Warm cream/gold   |
| 22K Rose Gold       | Soft rose         |
| 18K White Gold      | Clean white       |
| 22K Two-Tone        | Neutral grey      |

## Setup & Run

```bash
# Install dependencies
pip install streamlit rembg pillow numpy

# Run the app
streamlit run "Bg removal.py"
```

Then open `http://localhost:8501` in your browser.

## Author

**Vishal N** — AI/ML & Data Analytics  
[LinkedIn](https://www.linkedin.com/in/vishal-n-5a5059246/) | [GitHub](https://github.com/Vishal-N8610)
