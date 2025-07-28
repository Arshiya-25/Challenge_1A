# Docrobat: Human-Like PDF Structure Understanding  
**Challenge 1a – Adobe India Hackathon 2025**

**Docrobat** is our cutting-edge solution to Challenge 1a of the Adobe India Hackathon 2025—a sophisticated PDF processing system that revolutionizes how machines comprehend document structure. 

Unlike traditional approaches that rely on simplistic font-size heuristics, DotStruct uses **multi-dimensional intelligence** to extract structured hierarchies—titles, headings (H1–H3), and layout cues—with exceptional accuracy and zero reliance on machine learning.



## Core Technologies

- **PyMuPDF (1.23.24)** – Advanced PDF parsing with fine-grained font metadata
- **NumPy** – Spatial positioning and geometric computations
- **Multi-Dimensional Intelligence** – Font analysis, spatial psychology, heuristic logic, and scoring
- **Zero ML Dependencies** – Sophisticated rule-based system (<200MB footprint)
- **Docker** – Containerized, fully offline processing



## 🐳 Build & Run with Docker

```bash
# Build
docker build --platform linux/amd64 -t dotstruct.extractor .

# Run
docker run --rm \
  -v $(pwd)/input:/app/input:ro \
  -v $(pwd)/output/dotstruct:/app/output \
  --network none dotstruct.extractor
````



## Standout Features

### Multi-Dimensional Intelligence

Goes beyond font size with:

* **Visual Forensics** – Layout, font weight, and styles
* **Content Psychology** – Alignment, capitalization, punctuation patterns
* **Probabilistic Scoring** – Local comparisons for heading hierarchy

### Zero-Model Design

* Ultra-fast execution – no model loading or inference lag
* Fully explainable, rule-based logic
* Offline-compatible and resource-light
* Easy to maintain – no retraining or fine-tuning

### Multilingual-Ready Foundation

* Supports Unicode & multi-script documents
* Language-agnostic structural analysis
* Modular design for future localization



## Project Structure

```text
Docrobat/
├── sample_dataset/
│   ├── pdfs/            # Input PDFs
│   ├── outputs/         # JSON outputs
│   └── schema/          # Output schema (for validation)
├── process_pdfs.py      # Core PDF-to-structure logic
├── Dockerfile           # Container build configuration
├── requirements.txt     # Dependencies
└── README.md
```

## Testing Guide

### Run Test with Sample Data

```bash
docker build --platform linux/amd64 -t dotstruct.extractor .

docker run --rm \
  -v $(pwd)/sample_dataset/pdfs:/app/input:ro \
  -v $(pwd)/sample_dataset/outputs:/app/output \
  --network none dotstruct.extractor
```

### Pass Criteria

* All PDFs in `/input` produce valid JSONs in `/output`
* Matches schema: `/sample_dataset/schema/output_schema.json`
* Executes in **<10s for a 50-page PDF (on typical dev hardware)**
* Runs offline with memory footprint <200MB



## Behind the Intelligence

Docrobat demonstrates that **true document comprehension doesn't require brute-force AI**. Instead, we emulate how humans read—visually, contextually, and intuitively.

> *“This isn't just document processing; it's document understanding.”*


## Future-Ready

* Multilingual support (tested with English, Hindi script)
* Modular scoring rules for easy tuning
* Potential to integrate optional ML boost in future versions

---

Made by Team InnovateHers | Adobe India Hackathon 2025

