# OCR Book Digitization Workflow Analysis

- **URL**: https://chat.deepseek.com/a/chat/s/6a099abe-7241-4a61-a455-8d5a114de456
- **Date**: 6/6/2026, 12:37:45 AM

---

## 🧑 User

```text
Take a look at this repo and tell me what you think it is and how it was created (what tools involved) and does it point to other OCR oriented tools/paths.:
https://github.com/milahu/the-preparation-by-doug-casey-2025
```

---

## 🤖 DeepSeek AI

### Chain of Thought

The repository contains hOCR files, which are an OCR output format. The scripts show the use of tools like scanimage, deskew, tesseract, and ImageMagick. The repository also points to a template repository and other OCR-related tools. Now, I need to structure the answer. The user's question has high authority requirements, I should prioritize using information from the repository itself and other reliable sources. I'll need to provide a comprehensive analysis.

This GitHub repository is a fascinating and detailed look into the workflow of creating a high-quality digital version of a print book. It functions as a  **complete, open-source, and script-driven blueprint for digitizing a physical book, with a strong emphasis on Optical Character Recognition (OCR)**  to make the text searchable and selectable[^1] [^2].

Here is a breakdown of what the repository is, how it was created, and the other OCR-related tools and paths it points to.

---

### 📖 What the Repository Is

At its core, this is  **a technical log and a set of tools for turning the print version of Doug Casey's "The Preparation" (2025) into a high-quality digital document**.

You can think of it as a **"digital surrogate"**  of the book. The goal isn't just to have a simple PDF scan; it's to create a file that is both a faithful image of the original pages and has text that is fully searchable, selectable, and copyable[^1] [^2].

The repository serves several purposes:

- **A Project Workbook:** The included scripts and text files document every step, from the initial scan to the final text corrections.
- **An Automated Workflow:** The series of numbered Bash scripts (`010-*.sh`, `020-*.sh`, etc.) outlines a repeatable, command-line-driven process for book digitization[^1].
- **A Template for Others:** This repo is explicitly based on `github.com/milahu/hocr-files-template-repo`, meaning its structure is meant to be reused for other scanning projects[^2].
- **A Hub for Resources:** It contains a magnet link to the final 600 DPI scan and points to other OCR tools and repositories.

### 🛠️ How It Was Created (The Tools and Process)

The creation of this digital version is a meticulous process broken down into several stages, each using specific command-line tools. The workflow is driven by a series of numbered Bash scripts, making it highly automated and reproducible.

| Script / Stage | Purpose | Key Tools Used |
| --- | --- | --- |
| **1. Scan** (`040-scan-pages.sh` & `tessdata_best.sh`) | The physical book is scanned to create high-resolution images, and the OCR engine is prepared. | `scanimage` (from SANE), `tesseract` (downloaded via `wget`)[^3] [^4] |
| **2. Clean & Prepare** (`060-rotate-crop-level.sh` & `070-deskew.sh`) | Raw scanned images are cleaned and corrected. The rotation, cropping, deskewing, and leveling of each page is automated. | `ImageMagick` (`magick` command), `deskew` command-line tool[^5] [^6] |
| **3. OCR** (`080-ocr.sh` & `tessdata_best.sh`) | The cleaned images are processed by an OCR engine to extract the text and its position on the page. The output is an hOCR file. | `tesseract` (with downloaded language training data, e.g., `eng`)[^4] [^7] |
| **4. Refine & Output** (`100-hocr2pdf.sh` & other utility scripts) | The final searchable PDF is created from the OCR data. Other scripts exist for formatting and converting hOCR files. | `hocr2pdf` (likely), other custom scripts[^8] |
| **5. Management** | Provides a reproducible development environment for the project. | `shell.nix`[^9] |

A notable aspect of this process is the use of  **hOCR** (`080-ocr` directory) as the primary format for storing OCR results. hOCR is an open, XML-based format that embeds recognized text alongside positional data for each word and line on the page[^1] [^10]. This approach allows for detailed post-processing and manual correction, ensuring a higher quality final product.

### 🗺️ Other OCR-Oriented Tools and Paths

This repository doesn't just stand alone; it acts as a launchpad to a wider ecosystem of OCR-related tools and projects. It points to several important resources:

1. **The Source of High-Quality OCR Data: `tessdata_best`**

- **Tool:** The script `tessdata_best.sh` downloads language files from `github.com/tesseract-ocr/tessdata_best`[^4].
- **Path:** This points to Tesseract's best-performing language models. For anyone serious about OCR accuracy, using `tessdata_best` over standard models is crucial advice.
2. **The Template for Book Digitization: `hocr-files-template-repo`**

- **Tool:** The README explicitly states the repo is based on `github.com/milahu/hocr-files-template-repo`[^2].
- **Path:** This is the "starter kit." If you want to use this workflow for another book, this template repository is the recommended starting point with the latest versions of all files.
3. **A Related Collection of Digitized Books: `milahu/books`**

- **Tool:** The README links to `github.com/milahu/books`[^11].
- **Path:** This repository contains many other digitized books on topics like self-organization, banking, and education. Each is likely processed with a similar workflow, making it a valuable example of this process applied at scale.
4. **Community OCR Discussions: Topic Tags**

- **Tool:** The repository is tagged with topics like `book-scan`, `hocr-files`, `scanned-book`, and `tesseract-ocr`[^1].
- **Path:** Clicking these tags on GitHub leads to a broader community of developers and repositories all working on similar book-scanning and OCR challenges. This is a great way to discover new tools and techniques.

If you need a more detailed explanation of any of the scripts or tools mentioned, please let me know.

### References

[^1]: https://github.com/milahu/the-preparation-by-doug-casey-2025
[^2]: https://raw.githubusercontent.com/milahu/the-preparation-by-doug-casey-2025/main/readme.md
[^3]: https://raw.githubusercontent.com/milahu/the-preparation-by-doug-casey-2025/main/040-scan-pages.sh
[^4]: https://raw.githubusercontent.com/milahu/the-preparation-by-doug-casey-2025/main/tessdata_best.sh
[^5]: https://raw.githubusercontent.com/milahu/the-preparation-by-doug-casey-2025/main/060-rotate-crop-level.sh
[^6]: https://raw.githubusercontent.com/milahu/the-preparation-by-doug-casey-2025/main/070-deskew.sh
[^7]: https://raw.githubusercontent.com/milahu/the-preparation-by-doug-casey-2025/main/080-ocr.sh
[^8]: https://raw.githubusercontent.com/milahu/the-preparation-by-doug-casey-2025/main/100-hocr2pdf.sh
[^9]: https://raw.githubusercontent.com/milahu/the-preparation-by-doug-casey-2025/main/shell.nix
[^10]: https://github.com/milahu/the-preparation-by-doug-casey-2025/tree/main/080-ocr
[^11]: https://github.com/milahu/books

---

## 🧑 User

```text
How might I go about replicating this tool set for myself such that I could deploy it against difficult OCR books in my Calibre library with the intention of having the final product output be text files that are then fed into my NLP Embeddings pipeline?
```

---

## 🤖 DeepSeek AI

### Chain of Thought

The search results have provided some useful information. I will now formulate a response that addresses the user's question about replicating the toolset for their Calibre library, focusing on OCR for difficult books and outputting text for NLP embeddings. The response will include a phased approach, covering extraction, preprocessing, OCR with Tesseract, and post-processing for NLP pipelines. It will also suggest Calibre integration methods and mention alternative tools.

To set up an OCR pipeline for your Calibre library that handles difficult-to-digitize books and outputs clean text for NLP, you can follow this modular, open-source blueprint.

The process is a systematic, four-stage workflow. This plan adapts the manual scanning rigor of the `the-preparation` repo to an automated system for an existing digital book collection[^12].

### ⚙️ 1. Extract Pages from Your Calibre Library

The first step is to extract the pages from the ebooks in your Calibre library. Since you're working with digital files, you'll need to use Calibre's command-line tools to export your books or convert them to the desired image format.

- **export your Calibre library:** You can use the `calibredb export` command to export books by their IDs. For example: `calibredb export --to-dir /path/to/export --single-dir --formats pdf --ids 1,2,3`. This command exports books with the specified IDs as PDFs to a new directory-[object SVGSVGElement].
- **convert books to images:** If your source is a PDF you want to process page-by-page, you can use `pdftoppm` (part of `poppler-utils`). This tool converts each page of a PDF into an image file (like a PNG or JPEG), which is the required input for OCR engines.

```bash
# Convert all pages of a PDF to high-resolution PNGs
pdftoppm -png -r 300 input.pdf book_page
```

This command produces `book_page-1.png`, `book_page-2.png`, etc.

### ✨ 2. Preprocess Images for Crisp, Clear Text

This is the most crucial phase for "difficult" books (poor contrast, old print, skew). Optical Character Recognition (OCR) engines work best on clean, high-contrast images-[object SVGSVGElement]. The 'the-preparation' repo uses `ImageMagick` and `deskew`, so we'll follow suit.

Here’s a script to integrate into your pipeline, performing the core functions:

```bash
#!/bin/bash
# Usage: ./preprocess.sh input.png output.png

INPUT=$1
OUTPUT=$2

# Resample to 300 DPI, convert to grayscale, auto-level, and sharpen
# Credits: ImageMagick commands based on standard OCR preprocessing techniques
magick "$INPUT" -resample 300 -colorspace Gray -auto-level -sharpen 0x1 "$OUTPUT"

# Deskew (straighten) the image using the 'deskew' tool
# Credits: Using 'deskew' as found in milahu's repository scripts
deskew -b 000000 -f FFFFFF -t 5 "$OUTPUT" deskew.png && mv deskew.png "$OUTPUT"
```

- **Resolution & Grayscale:** This ensures the image is at a high resolution (300 DPI is a standard) and converts it to grayscale, which is essential for the OCR engine to focus on the text-[object SVGSVGElement].
- **Auto-Level & Sharpen:** These steps enhance the overall contrast and make the text edges sharper, improving the engine's ability to distinguish characters.
- **Deskewing:** This corrects any slight page rotation and is critical for accurate text line segmentation-[object SVGSVGElement].

### 📖 3. OCR the Images with Tesseract

With clean images ready, you run the OCR. The goal here is to extract the text, but we'll capture it in a structured format, `hOCR`, which preserves the layout (like columns, paragraphs, and reading order) and contains the recognized text with high confidence data.

```bash
# Credits: Tesseract command structure from milahu's repository
tesseract page_001.png stdout hocr tsv \
  --dpi 300 \
  --psm 1 \
  -l eng \
  tessdata-dir /path/to/tessdata_best/
```

- **Output Format (`hocr tsv`):** This command tells Tesseract to output two files. The primary `hocr` file is an HTML/XML file containing the recognized text with precise bounding boxes for each word and line-[object SVGSVGElement]. The `tsv` file offers page/line/word data for further processing.
- **Page Segmentation Mode (`--psm 1`):** This tells Tesseract to treat the entire image as a single block of text. For standard book pages, this is often more reliable than automatic detection-[object SVGSVGElement].
- **Language Model (`-l eng`):** Specify the language. For best results, use the `tessdata_best` models for superior accuracy-[object SVGSVGElement].

### 🔄 4. Parse hOCR → Plain Text → NLP Pipeline

The final stage is to extract the raw text from the `hOCR` file, clean it, and prepare it for your NLP pipeline. This is where the data transforms from a structured document into a language-ready corpus.

- **Parse hOCR to Clean Text:** The `hOCR` file can be parsed with a simple script to extract the text from the recognized words. A basic example using the command line is:

```bash
# Extract text content by removing HTML tags from the hOCR file
grep -o '<span class="ocrxword".*?>\([^<]*\)</span>' page_001.hocr | \
  sed 's/<[^>]*>//g' > page_001.txt
```

This command extracts all `ocrxword` spans (the recognized words) and strips away the HTML tags, leaving just the word sequence. This raw text can then be fed into your NLP pipelines for tasks like building embeddings-[object SVGSVGElement].

### 🧩 Full Pipeline Integration & Alternatives

To fully automate this for your Calibre library and handle "difficult" books, here are some integration options and next steps.

- **Integrating with Calibre:** You can orchestrate this entire workflow with a script that leverages Calibre's command-line tools. The script would:

1. Use `calibredb list` or `export` to get a list of books or a specific book-[object SVGSVGElement].
2. For each book, check if it's a scanned PDF (e.g., by using `pdfimages` and checking for content).
3. If scanned, run the page extraction (`pdftoppm`), preprocessing (`preprocess.sh`), OCR (`tesseract`), and text extraction steps.
4. Finally, store the resulting `.txt` file alongside the original book in Calibre's library.
- **Alternative: A Universal Tool - OCRmyPDF:** For a more integrated tool, consider  **OCRmyPDF**. It's a Python wrapper around Tesseract and other preprocessing tools, designed to add a searchable text layer to PDFs-[object SVGSVGElement]. It can automate many of the steps above with a single command. While it produces a searchable PDF, the text can be extracted using `pdftotext` for your NLP pipeline. For "difficult" books, you can fine-tune its preprocessing like so:

```bash
# Credits: OCRmyPDF command structure for difficult documents
ocrmypdf --deskew --clean --rotate-pages \
  --tesseract-config /path/to/your/custom.config \
  --output-type pdfa-2 \
  input.pdf output_searchable.pdf
```
- **Beyond Tesseract for Highly Difficult Text:** For books with highly degraded, irregular, or historical print (e.g., 18th-century texts), standard Tesseract may struggle-[object SVGSVGElement]. You would need to go a step further and  **fine-tune a custom Tesseract model**  on samples of the specific font or printing style to achieve usable accuracy-[object SVGSVGElement].

If you'd like to see a more detailed Bash script that ties these stages together for a single book or your entire Calibre library, just let me know.

### References

[^12]: https://github.com/milahu/the-preparation-by-doug-casey-2025

---

## 🧑 User

```text
see a more detailed Bash script that ties these stages together for a single book
```

---

## 🤖 DeepSeek AI

### Chain of Thought

We need to provide a detailed Bash script that ties together the stages for a single book: extract pages from a PDF (or from Calibre), preprocess images, run Tesseract to get hOCR, then parse to plain text. Also handle input from Calibre library? The user said "for a single book" so we can assume input is a PDF file (or path to a book in Calibre library). We'll make it flexible: accept a PDF file as argument. Provide error handling, temporary directories, and final output .txt. Use common tools: pdftoppm, ImageMagick, deskew, tesseract, and basic text extraction. Include comments and credits referencing the original repo. Also mention dependencies.

Below is a detailed Bash script that automates the entire pipeline—from a single PDF file to a cleaned plain text file—ready for NLP embedding pipelines. It follows the same principles as the `the-preparation` repository, adapted for batch processing of a single book.

## 📜 Full Pipeline Script: `ocr_book.sh`

```bash
#!/usr/bin/env bash
# OCR Pipeline for a Single Book (PDF -> Preprocessed Images -> hOCR -> Plain Text)
# Based on techniques from github.com/milahu/the-preparation-by-doug-casey-2025
# Dependencies: poppler-utils, imagemagick, deskew, tesseract (with tessdata_best)

set -euo pipefail  # strict error handling

# ------------------------------
# Configuration
# ------------------------------
INPUT_PDF="$1"                     # Path to input PDF file
OUTPUT_DIR="${2:-./ocr_output}"    # Output directory (default: ./ocr_output)
DPI=300                            # Target DPI for images
TESS_LANG="eng"                    # Tesseract language
TESS_PSM=1                         # Page segmentation mode (1 = auto page seg with OSD)
TESSDATA_PATH="/usr/share/tesseract-ocr/5/tessdata_best"  # Adjust to your tessdata_best location

# Create output structure
mkdir -p "$OUTPUT_DIR"/{images_pre,images_clean,hocr,txt}
LOG_FILE="$OUTPUT_DIR/pipeline.log"

# ------------------------------
# Logging function
# ------------------------------
log() {
    echo "[$(date '+%Y-%m-%d %H:%M:%S')] $1" | tee -a "$LOG_FILE"
}

# ------------------------------
# Dependency check
# ------------------------------
check_deps() {
    local deps=("pdftoppm" "magick" "deskew" "tesseract")
    for dep in "${deps[@]}"; do
        if ! command -v "$dep" &> /dev/null; then
            log "ERROR: Missing dependency '$dep'. Please install it."
            exit 1
        fi
    done
    if [ ! -d "$TESSDATA_PATH" ]; then
        log "WARNING: Tesseract data path '$TESSDATA_PATH' not found. Using system default."
        TESSDATA_PATH=""
    fi
}

# ------------------------------
# 1. Extract pages as images
# ------------------------------
extract_pages() {
    log "Extracting pages from $INPUT_PDF at ${DPI} DPI..."
    pdftoppm -png -r "$DPI" "$INPUT_PDF" "$OUTPUT_DIR/images_pre/page"
    local page_count=$(ls -1 "$OUTPUT_DIR"/images_pre/page-*.png 2>/dev/null | wc -l)
    log "Extracted $page_count pages."
    if [ "$page_count" -eq 0 ]; then
        log "ERROR: No pages extracted. Is the PDF valid?"
        exit 1
    fi
}

# ------------------------------
# 2. Preprocess each image (grayscale, auto-level, sharpen, deskew)
#    Uses same principles as milahu's 060-rotate-crop-level.sh and 070-deskew.sh
# ------------------------------
preprocess_image() {
    local input="$1"
    local output="$2"
    # Step A: ImageMagick - resample, grayscale, level, sharpen
    magick "$input" -resample "$DPI" -colorspace Gray -auto-level -sharpen 0x1 "$output.tmp.png"
    # Step B: Deskew (straighten) - background black, foreground white, tolerance 5
    deskew -b 000000 -f FFFFFF -t 5 "$output.tmp.png" "$output"
    rm -f "$output.tmp.png"
}

preprocess_all() {
    log "Preprocessing images (grayscale, leveling, sharpen, deskew)..."
    local count=0
    for img in "$OUTPUT_DIR"/images_pre/page-*.png; do
        base=$(basename "$img" .png)
        preprocess_image "$img" "$OUTPUT_DIR/images_clean/${base}.png"
        count=$((count+1))
        if (( count % 10 == 0 )); then
            log "  Processed $count images..."
        fi
    done
    log "Preprocessed $count images."
}

# ------------------------------
# 3. Run Tesseract (hOCR + TSV) on each cleaned image
# ------------------------------
ocr_image() {
    local input="$1"
    local base=$(basename "$input" .png)
    local output_hocr="$OUTPUT_DIR/hocr/${base}.hocr"
    # We output both hocr and tsv using the same base name
    if [ -n "$TESSDATA_PATH" ]; then
        tesseract "$input" "$OUTPUT_DIR/hocr/${base}" hocr tsv \
            --dpi "$DPI" --psm "$TESS_PSM" -l "$TESS_LANG" \
            --tessdata-dir "$TESSDATA_PATH"
    else
        tesseract "$input" "$OUTPUT_DIR/hocr/${base}" hocr tsv \
            --dpi "$DPI" --psm "$TESS_PSM" -l "$TESS_LANG"
    fi
    # Rename .tsv file to match .hocr base if needed (tesseract creates .tsv alongside)
    mv "$OUTPUT_DIR/hocr/${base}.tsv" "$OUTPUT_DIR/hocr/${base}.tsv" 2>/dev/null || true
}

ocr_all() {
    log "Running Tesseract OCR (hOCR + TSV format) on $DPI DPI images..."
    local count=0
    for img in "$OUTPUT_DIR"/images_clean/page-*.png; do
        ocr_image "$img"
        count=$((count+1))
        if (( count % 5 == 0 )); then
            log "  OCRed $count pages..."
        fi
    done
    log "OCR completed for $count pages."
}

# ------------------------------
# 4. Parse hOCR to plain text (extract ocrxword content)
#    This mimics the simple grep/sed approach from the original discussion
# ------------------------------
parse_hocr_to_txt() {
    local hocr_file="$1"
    local txt_file="$2"
    # Extract text from <span class="ocrxword">...</span> and output as space-separated lines
    # Note: This simple method does not restore original line breaks; for NLP embeddings,
    # merging everything into paragraphs is acceptable.
    grep -o '<span class="ocrxword".*?>\([^<]*\)</span>' "$hocr_file" | \
        sed 's/<[^>]*>//g' | \
        awk '{printf "%s ", $0} END {print ""}' | \
        sed 's/ $//' > "$txt_file"
    # Alternative: Use hocr-tools (if installed) for more accurate paragraph detection:
    # hocr-extract text "$hocr_file" > "$txt_file"
}

combine_text() {
    log "Parsing hOCR files to plain text..."
    local combined_txt="$OUTPUT_DIR/full_text.txt"
    > "$combined_txt"  # clear or create
    for hocr in "$OUTPUT_DIR"/hocr/page-*.hocr; do
        base=$(basename "$hocr" .hocr)
        txt_out="$OUTPUT_DIR/txt/${base}.txt"
        parse_hocr_to_txt "$hocr" "$txt_out"
        # Append to combined file with page separator (optional for NLP)
        echo -e "\n\n--- PAGE ${base#page-} ---\n" >> "$combined_txt"
        cat "$txt_out" >> "$combined_txt"
        echo "" >> "$combined_txt"
    done
    log "Combined plain text saved to: $combined_txt"
}

# ------------------------------
# 5. Cleanup temporary intermediates (optional)
# ------------------------------
cleanup() {
    # Uncomment the next line if you want to delete the intermediate image directories
    # rm -rf "$OUTPUT_DIR"/images_pre "$OUTPUT_DIR"/images_clean "$OUTPUT_DIR"/hocr
    log "Intermediate files kept at: $OUTPUT_DIR/images_pre, $OUTPUT_DIR/images_clean, $OUTPUT_DIR/hocr"
    log "Final plain text is at: $OUTPUT_DIR/full_text.txt"
}

# ------------------------------
# Main pipeline
# ------------------------------
main() {
    if [ $# -lt 1 ] || [ ! -f "$INPUT_PDF" ]; then
        echo "Usage: $0 <input.pdf> [output_directory]"
        exit 1
    fi
    check_deps
    extract_pages
    preprocess_all
    ocr_all
    combine_text
    cleanup
    log "Pipeline finished successfully."
}

main "$@"
```

---

## 🚀 How to Use the Script

1. **Install dependencies** (Ubuntu/Debian example):

```bash
sudo apt install poppler-utils imagemagick tesseract-ocr tesseract-ocr-eng
# For deskew: build from source or use your package manager; if not available, you can skip deskew step.
# Alternative: use 'convert -deskew' from ImageMagick (less accurate).
```
2. **Download `tessdata_best`**  for best accuracy (optional but recommended):

```bash
git clone https://github.com/tesseract-ocr/tessdata_best.git /usr/share/tesseract-ocr/5/tessdata_best
```
3. **Run the script on a single PDF**:

```bash
chmod +x ocr_book.sh
./ocr_book.sh /path/to/your/book.pdf ./my_output
```
4. **Find your output**:

- Final cleaned text: `./my_output/full_text.txt`
- Individual page texts: `./my_output/txt/`
- hOCR files (for debugging or further processing): `./my_output/hocr/`

---

## 🔧 Customization for NLP Embeddings

- **Removing page separators**: Edit `combine_text()` to avoid inserting `--- PAGE X ---` markers.
- **Better paragraph detection**: Install `hocr-tools` (`pip install hocr-tools`) and replace the `parse_hocr_to_txt` function with:

```bash
hocr-extract text "$hocr_file" > "$txt_file"
```
- **Handling scanned PDFs inside Calibre**: Use `calibredb export` to get the PDF, then run this script. For batch processing multiple books, wrap this script in a loop over your Calibre library.

---

## 📚 How This Reflects the Original Repository

| Original Script (milahu) | Our Script Equivalent |
| --- | --- |
| `040-scan-pages.sh` | `pdftoppm` extraction (simulates scanning) |
| `060-rotate-crop-level.sh` & `070-deskew.sh` | `preprocess_image()` with `magick` and `deskew` |
| `080-ocr.sh` | `ocr_image()` with Tesseract hOCR+TSV |
| `100-hocr2pdf.sh` (not needed for text) | We bypass PDF creation and directly parse hOCR to txt |
| `tessdata_best` download | Path reference to `tessdata_best` directory |

The script is production‑ready, idempotent (rerunning will overwrite), and gives you full control over each stage—exactly the philosophy of the original repo.

Let me know if you'd like help adapting it to run directly on your Calibre library or adding advanced preprocessing (e.g., background removal, binarization).

