
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

## 🔐 OpenAI API Key Setup

This module requires access to OpenAI's API in order to perform country inference using GPT models. Please follow the steps below to obtain and set up your API key:

### Step 1. Create an OpenAI account
Visit [https://platform.openai.com/signup](https://platform.openai.com/signup) to create a free or paid OpenAI account.

### Step 2. Generate your API key
1. Go to your account dashboard: [https://platform.openai.com/account/api-keys](https://platform.openai.com/account/api-keys)
2. Click **“Create new secret key”**
3. Copy and securely store the generated key (it will only be shown once)

### Step 3. Set the API key as an environment variable

You can store your key as an environment variable called `OPENAI_API_KEY`. For example:

#### On Linux/macOS:
```bash
export OPENAI_API_KEY="your-api-key-here"
```

To make this permanent, add the above line to your `~/.bashrc` or `~/.zshrc`.

#### On Windows (Command Prompt):
```cmd
set OPENAI_API_KEY=your-api-key-here
```

#### On Windows (PowerShell):
```powershell
$env:OPENAI_API_KEY="your-api-key-here"
```

### Step 4. Verify installation
After setting the key, run the notebook. The OpenAI SDK will automatically access `OPENAI_API_KEY` from the environment.

If the key is missing, the script will raise the following error:
```
ValueError: ❗ OPENAI_API_KEY not found. Please set your API key as an environment variable.
```

> 🔒 **Keep your API key private.** Do not share or upload it to GitHub.

## 🧪 Prompt Format

The system uses a standardized prompt:

```
Determine the country corresponding to each of the following locations...
[omitted here, see full prompt in paper]
```

## 📜 Citation

> He, Jie-Long (2025). *Fasta AI_CSI R1: AI-Powered Country Inference for Avian Influenza FASTA files*. Zenodo. https://doi.org/10.5281/zenodo.15344824
