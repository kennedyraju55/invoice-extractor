<div align="center">
<img src="https://img.shields.io/badge/🧾_Invoice_Extractor-Local_LLM_Powered-blue?style=for-the-badge&labelColor=1a1a2e&color=16213e" alt="Project Banner" width="600"/>

<br/>

<img src="https://img.shields.io/badge/Gemma_4-Ollama-orange?style=flat-square&logo=google&logoColor=white" alt="Gemma 4"/>
<img src="https://img.shields.io/badge/Python-3.9+-blue?style=flat-square&logo=python&logoColor=white" alt="Python"/>
<img src="https://img.shields.io/badge/Streamlit-Web_UI-red?style=flat-square&logo=streamlit&logoColor=white" alt="Streamlit"/>
<img src="https://img.shields.io/badge/Click-CLI-green?style=flat-square&logo=gnu-bash&logoColor=white" alt="Click CLI"/>
<img src="https://img.shields.io/badge/License-MIT-yellow?style=flat-square" alt="License"/>

<br/><br/>

<strong>Part of <a href="https://github.com/kennedyraju55/90-local-llm-projects">90 Local LLM Projects</a> collection</strong>

</div>

<br/>
# 🧾 Invoice Extractor

![Python](https://img.shields.io/badge/Python-3.11+-blue?logo=python&logoColor=white)
![LLM](https://img.shields.io/badge/LLM-Gemma%204-orange)
![Ollama](https://img.shields.io/badge/Ollama-Local-green)
![Streamlit](https://img.shields.io/badge/UI-Streamlit-red?logo=streamlit)
![License](https://img.shields.io/badge/License-MIT-yellow)

Production-grade invoice data extractor with batch processing, CSV/Excel export, duplicate detection, and category tagging using a local LLM.

## ✨ Features

- **Structured extraction** — vendor, invoice number, dates, line items, totals, tax, payment terms
- **Batch processing** — Process multiple invoices at once
- **CSV/JSON export** — Export extracted data for accounting systems
- **Duplicate detection** — Identify potential duplicate invoices
- **Category tagging** — Auto-categorize line items (Office Supplies, Software, etc.)
- **Multiple output formats** — JSON, Rich table, or CSV
- **Dual Interface** — CLI + Streamlit Web UI
- **Local & private** — All processing via local Ollama

## 🚀 Installation

```bash
cd 15-invoice-extractor
pip install -r requirements.txt
ollama serve && ollama pull gemma4
```

## 📋 CLI Usage

```bash
# Extract single invoice
python -m src.invoice_extractor.cli extract --file invoice.txt --output table

# Batch process multiple invoices
python -m src.invoice_extractor.cli batch --files inv1.txt --files inv2.txt --export output.csv

# Categorize line items
python -m src.invoice_extractor.cli categorize --file invoice.txt
```

## 🌐 Web UI (Streamlit)

```bash
streamlit run src/invoice_extractor/web_ui.py
```

Features: Multi-file uploader, extracted data table, duplicate detection, category tagging, CSV/JSON export buttons.

## 🧪 Running Tests

```bash
python -m pytest tests/ -v
```

## 📁 Project Structure

```
15-invoice-extractor/
├── src/invoice_extractor/
│   ├── __init__.py, core.py, cli.py, web_ui.py, config.py, utils.py
├── tests/
│   ├── __init__.py, test_core.py, test_cli.py
├── config.yaml, setup.py, requirements.txt, Makefile, .env.example, README.md
```

## Part of

[90 Local LLM Projects](../README.md) — A collection of projects powered by local language models.

## 📸 Screenshots

<div align="center">
<table>
<tr>
<td><img src="https://via.placeholder.com/400x250/1a1a2e/e94560?text=CLI+Interface" alt="CLI Interface"/></td>
<td><img src="https://via.placeholder.com/400x250/16213e/e94560?text=Web+UI" alt="Web UI"/></td>
</tr>
<tr>
<td align="center"><em>CLI Interface</em></td>
<td align="center"><em>Streamlit Web UI</em></td>
</tr>
</table>
</div>
