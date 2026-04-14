# 🧾 Invoice Extractor

![Python 3.11+](https://img.shields.io/badge/Python-3.11+-blue?style=flat-square&logo=python&logoColor=white)
![MIT License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square)
![Gemma 4](https://img.shields.io/badge/Gemma_4-LLM-orange?style=flat-square&logo=google&logoColor=white)
![Privacy-First](https://img.shields.io/badge/Privacy-100%25_Local-brightgreen?style=flat-square)
![Ollama](https://img.shields.io/badge/Ollama-Inference-blueviolet?style=flat-square)

> Extract structured data from invoices and receipts using a local LLM — no cloud, no API keys, 100% private.

## Architecture

```
┌──────────────────────────────────────────────┐
│         Invoice Input (text / file)          │
│                    │                          │
│            ┌──────▼───────┐                  │
│            │   Invoice    │                  │
│            │   Parser     │                  │
│            └──────┬───────┘                  │
│                   │                          │
│            ┌──────▼───────┐                  │
│            │   Ollama     │                  │
│            │  (Gemma 4)   │                  │
│            └──────┬───────┘                  │
│     ┌─────────────┼─────────────┐            │
│ ┌───▽────┐  ┌─────▽────┐  ┌────▽─────┐     │
│ │Vendor  │  │  Line    │  │Category  │     │
│ │Details │  │  Items   │  │Classifier│     │
│ └────────┘  └──────────┘  └──────────┘     │
│                   │                          │
│     ┌─────────────┼─────────────┐            │
│ ┌───▽────┐  ┌─────▽────┐  ┌────▽─────┐     │
│ │  JSON  │  │   CSV    │  │ Batch    │     │
│ │ Export │  │  Export  │  │ Report   │     │
│ └────────┘  └──────────┘  └──────────┘     │
└──────────────────────────────────────────────┘
```

## Features

1. **Structured Data Extraction** — Parses vendor details, line items, totals, tax, and payment terms from raw invoice text
2. **Automatic Categorization** — Classifies line items into categories like Software, Hardware, Travel, and Consulting
3. **Batch Processing** — Process multiple invoices in one run with configurable batch sizes
4. **Duplicate Detection** — Identifies near-duplicate invoices using configurable similarity thresholds
5. **Multi-Format Export** — Output extracted data as JSON or CSV for downstream accounting systems
6. **Rich CLI Interface** — Beautiful terminal output with color-coded tables and progress indicators
7. **Streamlit Web UI** — Browser-based dashboard for uploading invoices and reviewing extracted data
8. **FastAPI REST Endpoint** — Programmatic API access for integrating into automated AP workflows
9. **Docker Ready** — Full Docker and Docker Compose support for containerized deployment
10. **100% Local & Private** — All inference runs through Ollama locally; sensitive financial data never leaves your machine

## Quick Start

### Prerequisites

- Python 3.11 or higher
- [Ollama](https://ollama.com/) installed and running
- Gemma 4 model pulled: `ollama pull gemma4`

### Installation

```bash
git clone https://github.com/kennedyraju55/invoice-extractor.git
cd invoice-extractor
pip install -r requirements.txt
```

### Running the Application

**CLI:**
```bash
python -m src.invoice_extractor.cli extract --file invoice.txt
```

**Web UI:**
```bash
streamlit run src/invoice_extractor/web_ui.py
```

**Docker:**
```bash
docker-compose up
```

## Tech Stack

| Technology | Purpose |
|-----------|---------|
| Gemma 4 + Ollama | Local LLM inference for invoice parsing and categorization |
| Click + Rich | CLI framework with formatted tables and progress bars |
| Streamlit | Interactive web dashboard for invoice uploads |

## Project Structure

- `src/invoice_extractor/` — Core application: parsing engine, categorizer, CLI, web UI, API
- `common/` — Shared LLM client utilities for Ollama integration
- `tests/` — Unit and integration test suite
- `docs/` — Documentation and architecture diagrams
- `examples/` — Sample invoices and expected extraction outputs

## Author

**Nrk Raju Guthikonda** — [GitHub: kennedyraju55](https://github.com/kennedyraju55) · [Dev.to](https://dev.to/kennedyraju55) · [LinkedIn](https://www.linkedin.com/in/nrk-raju-guthikonda-504066a8/)
