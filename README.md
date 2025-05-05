# Fasta AI_CSI R1: AI-Powered Country Inference for Avian Influenza FASTA files

## 🔍 Project Overview

**Fasta AI_CSI R1** is a semantic inference module designed to resolve ambiguous or inconsistent location strings embedded in avian influenza virus FASTA metadata. When rule-based ISO 3166-1 assignment fails, this tool leverages OpenAI’s GPT models (gpt-3.5 / gpt-4o) to infer the most likely country of origin.

It is designed for scalable metadata normalization in large-scale surveillance of avian influenza viruses, ensuring high-resolution geographic mapping for downstream analysis.

## ⚙️ Features

- Language-model-driven inference via OpenAI GPT (model selectable)
- Batch processing with progress tracking (`tqdm`)
- Fault tolerance with autosave/resume and retry mechanism
- Live dictionary updates (`location_to_country_AI.json`)
- Export of unresolved entries for manual review (`other_locations.csv`)

## 📂 Files

- `Fasta AI_CSI R1.ipynb`: The main executable notebook
- `location_to_country_AI.json`: Output mapping of AI-inferred countries
- `other_locations.csv`: Unresolved entries labeled as "Other"
- `country_stat.csv`: Final country-level summary table

## 📥 Installation

```bash
pip install -r requirements.txt
```

## 🧪 Prompt Format

The system uses a standardized prompt:

```
Determine the country corresponding to each of the following locations...
[omitted here, see full prompt in paper]
```

## 📜 Citation

> He, Jie-Long (2025). *Fasta AI_CSI R1: AI-Powered Country Inference for Avian Influenza FASTA files*. Zenodo. https://doi.org/10.5281/zenodo.xxxxxxx
