# HTML Biblical Terms List to CSV Converter

A client-side web tool that converts Biblical Terms lists exported from Paratext into CSV format for use as additional training data in Scripture Forge.

## Purpose

This tool bridges the gap between Paratext's Biblical Terms export format and Scripture Forge's training data requirements. It extracts source and target language terms from HTML tables and generates properly formatted CSV files that can be imported into Scripture Forge for enhanced translation assistance.

## Features

- **100% Client-Side Processing**: All data processing happens in your browser - no uploads, no server, complete privacy
- **Smart Parentheses Detection**: Automatically identifies and extracts language data from parenthetical expressions
- **Flexible Source Selection**: When multiple language options exist in parentheses, choose which to use as your source
- **Custom Filename Output**: Edit the output filename before downloading
- **UTF-8 Encoding**: Ensures proper handling of all Unicode characters and diacritics
- **Clean, Responsive Interface**: Works on desktop and mobile devices

## How to Use

### Step 1: Export from Paratext
1. Export your Biblical Terms list from Paratext as an HTML file (.html or .htm)
2. Ensure the export includes both source and target language terms in the 5th column

### Step 2: Upload and Process
1. Open `Convert-Terms-List.html` in your web browser
2. Drag and drop your HTML file or click to browse
3. The tool will validate that the file contains a proper table structure

### Step 3: Configure Export
- If multiple sets of parentheses are detected, select which one contains your source language
- Edit the output filename if desired (defaults to `[original_filename].csv`)
- Click "Confirm & Process"

### Step 4: Download
- Click "Download CSV" to save your converted file
- Import the CSV into Scripture Forge as training data

## CSV Output Format

The generated CSV contains two columns:
- **Source**: The text extracted from inside the selected parentheses
- **Target**: The text appearing before the first set of parentheses

Example:
```csv
Source,Target
Greek term,English translation
Hebrew word,Target language equivalent
```

## Technical Details

- **Technology**: HTML5, Tailwind CSS, Vanilla JavaScript
- **File Processing**: Uses the browser's File API and DOM Parser
- **Privacy**: No data leaves your computer - everything runs locally
- **Encoding**: UTF-8 with BOM for Excel compatibility

## Requirements

- Any modern web browser (Chrome, Firefox, Safari, Edge)
- No internet connection required (after initial page load for Tailwind CSS)
- No installation needed

## For Developers: Building the CSS

**End users don't need to install anything** - they just visit the GitHub Pages URL and use the tool directly in their browser.

If you're modifying the HTML/CSS and need to rebuild the stylesheet:

1. Install Node.js (if you don't already have it) and run:

```bash
npm install
```

2. Build the Tailwind stylesheet:

```bash
npm run build:css
```

3. Commit the updated `dist/styles.css` file before deploying to GitHub Pages

The built `dist/styles.css` file is already included in this repository, so the tool works immediately when deployed to GitHub Pages.

## Use Case

This tool is specifically designed for Bible translation teams using both Paratext and Scripture Forge. It streamlines the workflow of preparing Biblical Terms data for machine translation training, eliminating manual CSV formatting and reducing potential errors.

## Privacy & Security

All file processing occurs entirely within your browser. No files are uploaded to any server, and no data is transmitted over the network (except for loading the Tailwind CSS library). Your Biblical Terms data remains completely private and secure on your local machine.

## License

MIT License

Copyright (c) 2026

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
