# UPVC Factory Planner

A browser-based planner for a UPVC windows & doors factory: factory shed (warehouse) plus a separate office building on your plot, with roofing options and a detailed bill of quantities.

Open `index.html` in any browser. No install or internet needed apart from web fonts.

## What it does

- **Site layout**: plot with setbacks, factory shed with column grid, office placed in front of / left of / right of the shed, ring road, truck and staff gates, parking, security cabin. Draws a cross-section of the shed and a front elevation of the office.
- **UPVC production zones**: profile store → cutting → machining → welding & corner cleaning → hardware & assembly → glass & glazing → QC → finished goods → dispatch, sized by area.
- **Roofing options**: compares six systems on your exact shed size: PEB with bare Galvalume, PEB with colour-coated sheet + glasswool, PEB with PUF panel, PEB with standing seam, conventional MS truss, and RCC slab. Shows steel tonnage, shell cost, cost per sq ft, comfort, rain noise and life.
- **Detailed estimate**: about 90 line items in 10 sections (site prep, foundations, industrial floor, steel frame, roofing, walls & openings, shed services, office, external works, fire & power) with quantity, unit, rate and amount, plus design fee, contingency and GST.
- **Rate library**: every rate is editable. Replace the defaults with your local quotes.
- Save / open project files, copy the estimate into Excel, download CSV, print to PDF.

All dimensions are in feet, areas in sq ft, volumes in cu ft, and rates in ₹ per sq ft, cu ft or running ft. Slab and wall thicknesses are in inches. Only sheet gauges (mm), steel weights (kg) and concrete grades keep their usual units.

Your inputs and rates are remembered in the browser.

## Notes

Rates are indicative 2026 Indian rates (₹, excluding GST). Quantities use standard engineering rules of thumb, which are good for budgeting and comparing options. Get the structure designed by a licensed structural engineer and confirm setbacks and ground coverage with your planning authority before construction.

---

# Page Reader

`page-reader/index.html` — open a PDF, Word (.docx) or text file, type a page number, and the app reads that page aloud in the language it is written in.

- Detects the language of the page by its script (Tamil, Hindi, Marathi, Bengali, Telugu, Kannada, Malayalam, Gujarati, Punjabi, Odia, Urdu, Arabic, Persian, Russian, Chinese, Japanese, Korean, Thai and more) and, for Latin-script text, by common words (English, French, Spanish, German, Italian, Portuguese and others). Sentences in a second language on the same page are read with that language's voice.
- Highlights each sentence as it is read; tap a sentence to start from there. Pause, stop, previous/next page, speed, voice, and "keep reading next pages".
- Uses the browser's built-in speech voices. If your device has no voice for a language, the app shows how to install one (Android, Windows, iPhone/Mac).
- **Text recognition (OCR):** for Indian-language PDFs and scanned pages, the app reads the picture of the page with Tesseract instead of trusting the text stored in the PDF, which is often in the wrong order and makes voices spell out letters. Language data for English, Tamil, Hindi, Marathi, Malayalam, Telugu, Kannada, Bengali, Gujarati and Punjabi is in `page-reader/tessdata/` (base64 text; serve the folder over http, e.g. `python3 -m http.server`, for it to be used); other languages download it on first use. You can switch between OCR and the file's own text under **Get text from**.
- **Poems:** short lines are read line by line with a pause after each line and a longer pause between stanzas. Change it under **Read as**.
- Word and text files have no fixed pages, so they are split into pages of about 300 words.
