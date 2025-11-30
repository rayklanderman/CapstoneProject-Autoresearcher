# AutoResearcher

**Multi-Agent Research Crew for Instant, Citation-Rich Reports**  
_Transforms a single prompt into a print-ready LaTeX PDF in under 10 minutes._

[![Open in Kaggle](https://img.shields.io/badge/Kaggle-Notebook-20BEFF?logo=kaggle)](https://www.kaggle.com/rayklanderman/autoresearcher-capstone)
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/rayklanderman/CapstoneProject-Autoresearcher/blob/main/AutoResearcher_Capstone.ipynb)
[![Vertex AI ADK](https://img.shields.io/badge/Vertex_AI_ADK-Official_Python_Support-4285F4?logo=google-cloud)](https://google.github.io/adk-docs/get-started/python/)

---

## 🚀 What AutoResearcher Produces

Give the system a prompt like:

> _“Create a 15–20 page report on AI agents in healthcare in 2025 for hospital CIOs.”_

Within minutes you get:

- **50+ verified sources** from Tavily  
- **Fact-checked claims** by a dedicated agent  
- **Matplotlib charts** (market forecast, risk matrix, trends)  
- **Structured academic writing** (exec summary → conclusion)  
- **A complete PDF** with title page, TOC, figures, citations  
- **No hallucinated references**

⚡ **End-to-end pipeline runs in <10 minutes**  
⚡ **Zero manual formatting or citation work**

---

## ❓ Why AutoResearcher Exists

Professionals in 2025 still lose 8–10 hours building a single research report:

- Searching and extracting sources  
- Verifying claims  
- Creating charts  
- Writing structured academic sections  
- Formatting citations  
- Exporting to PDF or LaTeX  

Traditional AI tools summarize text but cannot generate **reproducible, citation-rich, multi-section research documents**.  
AutoResearcher solves this with a coordinated agent team.

---

## 🤖 How It Works: The Multi-Agent Crew

AutoResearcher uses a **7-agent hierarchical system** built on the **Vertex AI ADK for Python**.

| Agent           | Model            | Tool           | Role                                                     |
| ----------------| ---------------- | -------------- | -------------------------------------------------------- |
| **Supervisor**  | Gemini 2.5 Pro   | —              | Manages workflow + structured JSON task routing         |
| **Researcher**  | Gemini 2.5 Flash | Tavily         | Collects real, live web sources                         |
| **FactChecker** | Gemini 2.5 Pro   | Tavily         | Cross-checks claims and stats                           |
| **Visualizer**  | Gemini 2.5 Flash | Python REPL    | Generates charts via Matplotlib                         |
| **Writer**      | Gemini 2.5 Pro   | —              | Produces academic-grade sections                        |
| **Formatter**   | Gemini 2.5 Flash | —              | Builds final Markdown with TOC + references             |
| **Compiler**    | —                | Pandoc + LaTeX | Converts Markdown → PDF                                 |

All agents share an in-notebook dictionary called `MEMORY`, enabling coordinated, stateful work.

### **System Architecture**

![AutoResearcher Architecture](https://raw.githubusercontent.com/rayklanderman/CapstoneProject-Autoresearcher/main/AutoResearcher%20Architecture.png)

---

## ▶️ Quickstart

### **Option A — Kaggle (Recommended)**

1. Open the notebook  
   https://www.kaggle.com/rayklanderman/autoresearcher-capstone  
2. Add secrets:  
   - `PROJECT_ID`  
   - `GEMINI_API_KEY`  
   - `TAVILY_API_KEY`  
   - `SERVICE_ACCOUNT_JSON`  
3. Run all cells

### **Option B — Google Colab**

1. Open the Colab notebook  
2. Add secrets (Runtime → Secrets) or edit code to input them manually  
3. Install dependencies → run all cells

💡 Tip: **Cell 7** displays the entire agent pipeline—perfect for demos.

---

## 🛠 Tech Stack

- **Framework**: Vertex AI ADK for Python  
- **Models**: Gemini 2.5 Pro + Flash  
- **Tools**: Tavily API, Matplotlib, Pandoc + LaTeX  
- **Runtime**: Kaggle / Colab  
- **State Management**: Shared in-notebook memory dictionary  
- **Security**: All keys pulled from platform secrets

Install ADK:

```bash
pip install "git+https://github.com/google/adk-python.git@main"
```

---

## 📁 Repository Structure

```
CapstoneProject-Autoresearcher/
├── autoresearcher.ipynb          # Main Jupyter notebook
├── LICENSE                       # License file
├── README.md                     # This README
├── SECURITY.md                   # Security policy
├── CONTRIBUTING.md               # Contributing guidelines
├── CODE_OF_CONDUCT.md            # Community code of conduct
├── NOTICE                        # Legal notices and attributions
└── SECRET_HANDLING.md            # Secure handling of secrets & API keys
```

---

## 📄 License

For educational and capstone submission purposes only.  
© 2025 Raymond Robert Klanderman
