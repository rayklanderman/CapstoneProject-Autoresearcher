# AutoResearcher

**Multi-Agent Crew for Instant, Citation-Rich Research Reports**  
_From prompt to LaTeX PDF in under 10 minutes_

[![Open in Kaggle](https://img.shields.io/badge/Kaggle-Notebook-20BEFF?logo=kaggle)](https://www.kaggle.com/rayklanderman/autoresearcher-capstone)
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/rayklanderman/CapstoneProject-Autoresearcher/blob/main/AutoResearcher_Capstone.ipynb)
[![Vertex AI ADK](https://img.shields.io/badge/Vertex_AI_ADK-Official_Python_Support-4285F4?logo=google-cloud)](https://google.github.io/adk-docs/get-started/python/)

---

## 📌 Problem

In 2025, researchers, analysts, and professionals spend 8–10 hours manually compiling comprehensive reports—searching sources, verifying facts, creating charts, writing sections, and formatting citations. Tools like ChatGPT or Perplexity provide summaries but cannot deliver **complete, reproducible, 15–20 page documents** with:

- ✅ Real, traceable sources
- ✅ Verified claims
- ✅ Original data visualizations
- ✅ Proper academic structure
- ✅ Downloadable PDF/LaTeX output

---

## 🤖 Solution: A Multi-Agent Research Crew

AutoResearcher automates the full research pipeline using a **7-agent hierarchical system** built with the **official Vertex AI Agent Development Kit (ADK) for Python**.

| Agent           | Model            | Tool           | Role                                                     |
| --------------- | ---------------- | -------------- | -------------------------------------------------------- |
| **Supervisor**  | Gemini 2.5 Pro   | —              | Orchestrates workflow via structured JSON delegation     |
| **Researcher**  | Gemini 2.5 Flash | Tavily         | Fetches live web sources (titles, URLs, snippets)        |
| **FactChecker** | Gemini 2.5 Pro   | Tavily         | Validates claims against collected sources               |
| **Visualizer**  | Gemini 2.5 Flash | Python REPL    | Generates Matplotlib charts (market growth, risk matrix) |
| **Writer**      | Gemini 2.5 Pro   | —              | Drafts structured academic sections                      |
| **Formatter**   | Gemini 2.5 Flash | —              | Assembles final Markdown with TOC, figures, references   |
| **Compiler**    | —                | Pandoc + LaTeX | Converts Markdown → print-ready PDF                      |

All agents share an in-memory dictionary (`MEMORY`) to pass state—enabling stateful collaboration in notebook environments.

---

## 🧪 Demo

Given the prompt:

> _“Create a 15–20 page report on AI agents in healthcare in 2025 for hospital CIOs.”_

The system produces:

- 📚 **50+ real sources** from Tavily
- ✅ **Verified market stats** (e.g., $28.3B market in 2025)
- 📊 **2 dynamic charts**: market forecast + risk matrix
- 📄 **Downloadable PDF** with title, TOC, citations, and figures

✅ **Full pipeline runs in <10 minutes**  
✅ **Zero hallucinated references**  
✅ **Zero manual formatting**

▶️ **Run it yourself**:

- [Kaggle Notebook](https://www.kaggle.com/rayklanderman/autoresearcher-capstone)
- [Open in Google Colab](https://colab.research.google.com/github/rayklanderman/CapstoneProject-Autoresearcher/blob/main/AutoResearcher_Capstone.ipynb)

---

## 🛠️ Tech Stack

- **Agent Framework**: **Official Vertex AI ADK for Python** (`google.adk.agents`)
- **Models**: Gemini 2.5 Pro & Flash (`google-generativeai` SDK)
- **Tools**:
  - Tavily (web search)
  - Custom Python REPL (safe chart generation)
  - Pandoc + LaTeX (`xelatex`) for PDF export
- **Memory**: In-notebook shared dictionary
- **Environment**: Kaggle / Colab (secrets managed via platform secrets)

> 🔒 **No API keys are hardcoded**—all loaded securely from secrets.

---

## ▶️ How to Run

### On Kaggle (Recommended)

1. Open the [Kaggle Notebook](https://www.kaggle.com/rayklanderman/autoresearcher-capstone)
2. Go to **Add-ons → Secrets** and add:
   - `PROJECT_ID`
   - `GEMINI_API_KEY`
   - `TAVILY_API_KEY`
   - `SERVICE_ACCOUNT_JSON`
3. Run all cells

### On Google Colab

1. Click **[Open in Colab](https://colab.research.google.com/github/rayklanderman/CapstoneProject-Autoresearcher/blob/main/AutoResearcher_Capstone.ipynb)**
2. Use **Secrets** (Colab → Runtime → "Secrets") or replace `kaggle_secrets` with manual input
3. Install dependencies and run

> 💡 **Tip**: Record **Cell 7** for your demo video—it shows the full agent pipeline.

---

## ℹ️ ADK Implementation Note

This project uses the **official ADK for Python**, installed via:

```bash
pip install "git+https://github.com/google/adk-python.git@main"
---


📄 License
----------

For educational and capstone submission purposes only.© 2025 Raymond Robert Klanderman

📁 Repository Structure
-----------------------

Plaintext

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   CapstoneProject-Autoresearcher/  ├── autoresearcher.ipynb          # Main Jupyter notebook with the multi-agent research system  ├── LICENSE                       # License file  ├── README.md                     # This README file  ├── SECURITY.md                   # Security policy  ├── CONTRIBUTING.md               # Contributing guidelines  ├── CODE_OF_CONDUCT.md            # Code of conduct  ├── NOTICE                        # Legal notices and attributions  └── SECRET_HANDLING.md            # Guidelines for handling secrets and API keys   `
