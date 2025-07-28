# Semantic Document Explorer - PDF Heading Extractor

## Overview
This application extracts structured outlines from PDF documents, identifying titles and hierarchical headings (H1, H2, H3) with their page numbers.

## Approach
- **Font Size Analysis**: Primary method for identifying heading levels
- **Text Pattern Recognition**: Detects common heading patterns (numbered sections, chapters, etc.)
- **Formatting Cues**: Uses bold text and other formatting indicators
- **Hierarchical Classification**: Automatically assigns H1, H2, H3 levels based on font size tiers
- **Multilingual Support**: Works with various character encodings including Japanese

## Libraries Used
- **PyMuPDF (fitz)**: PDF processing and text extraction with formatting information
- **Python Standard Library**: JSON handling, regex, pathlib, logging

## Features
- Processes PDFs up to 50 pages
- Extracts title and hierarchical headings
- Outputs structured JSON format
- Handles multilingual content
- Optimized for performance (< 10 seconds for 50-page PDF)
- No internet connectivity required
- Lightweight model size (< 200MB)

## Build and Run

### Building the Docker Image
```bash
docker build --platform linux/amd64 -t pdf-heading-extractor:latest .