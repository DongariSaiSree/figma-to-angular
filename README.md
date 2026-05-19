# 🎨 Figma-to-Angular — AI-Powered UI Code Generator

Convert UI design screenshots into production-ready **Angular code** using multimodal AI — no manual coding required.

![Python](https://img.shields.io/badge/Python-3.10+-blue?logo=python)
![FastAPI](https://img.shields.io/badge/FastAPI-latest-teal)
![LLM](https://img.shields.io/badge/LLM-Vision_Enabled-orange)
![Angular](https://img.shields.io/badge/Output-Angular-red?logo=angular)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

---

## 🧠 What It Does

Upload one or more screenshots of a UI design (from Figma, sketches, or any mockup tool), and this system will:

1. Encode your images to base64
2. Send them to a vision-enabled LLM with structured prompting
3. Generate Angular components with a complete file hierarchy
4. Extract code into individual files
5. Package everything into a **downloadable ZIP** — ready to drop into your Angular project

---

## ✨ Features

- **Multi-image support** — Upload multiple screenshots for complex, multi-view UIs
- **Structured file generation** — Outputs proper Angular component structure (`.ts`, `.html`, `.scss`)
- **Iterative refinement** — Upload, test, tweak, repeat until the output matches your design
- **REST API** — Clean FastAPI endpoints for easy integration into existing workflows
- **Vision LLM integration** — Leverages state-of-the-art multimodal models for high-fidelity code generation

---

## 🏗️ Architecture

```
User Uploads UI Image(s)
         │
         ▼
┌─────────────────────────┐
│   Image → Base64 Encode  │
└────────────┬────────────┘
             │
             ▼
┌─────────────────────────┐
│  Vision LLM API Call     │
│  (Structured Prompting)  │
└────────────┬────────────┘
             │
             ▼
┌─────────────────────────┐
│  Angular Code Generation │
│  with File Hierarchy     │
└────────────┬────────────┘
             │
             ▼
┌─────────────────────────┐
│  Extract → ZIP Package   │
└────────────┬────────────┘
             │
             ▼
      📦 Download ZIP
```

---

## 🛠️ Tech Stack

| Component | Technology |
|---|---|
| Backend API | FastAPI |
| Image Processing | Python (base64, PIL) |
| AI Model | Vision-enabled LLM (GPT-4V / Gemini Vision) |
| Prompt Engineering | Custom structured prompts |
| Output Packaging | Python zipfile |
| Language | Python 3.10+ |

---

## 📁 Project Structure

```
figma-to-angular/
├── app/
│   ├── main.py              # FastAPI entry point
│   ├── encoder.py           # Image to base64 encoding
│   ├── prompt_builder.py    # Structured prompt construction
│   ├── llm_client.py        # Vision LLM API integration
│   ├── code_extractor.py    # Parse LLM output into files
│   └── packager.py          # ZIP file generation
├── prompts/
│   └── angular_prompt.txt   # Base prompt template
├── outputs/                 # Generated ZIP files
├── tests/
│   └── test_generation.py
├── requirements.txt
├── .env.example
└── README.md
```

---

## 🚀 Getting Started

```bash
# Clone the repo
git clone https://github.com/yourusername/figma-to-angular.git
cd figma-to-angular

# Install dependencies
pip install -r requirements.txt

# Set up environment variables
cp .env.example .env
# Add your LLM API key to .env

# Run the API
uvicorn app.main:app --reload
```

### API Usage

```bash
# Upload a UI image and get Angular code back as a ZIP
curl -X POST "http://localhost:8000/generate" \
  -F "files=@screenshot1.png" \
  -F "files=@screenshot2.png" \
  --output generated_angular.zip
```

---

## 💡 Tips for Best Results

- Upload **multiple screenshots** for complex UIs (list view + detail view + mobile)
- Use **high-resolution, clean screenshots** for better OCR and layout understanding
- **Iterate** — download, test in Angular, then re-upload with feedback in the prompt
- Works best with **standard UI patterns** (forms, tables, dashboards, navigation)

---

## 📊 Key Results

- ✅ End-to-end Angular code generation from UI images
- ✅ Proper component file structure (`.ts`, `.html`, `.scss`)
- ✅ Multi-image support for complex multi-view interfaces
- ✅ Production-tested at Virtusa for enterprise client projects

---

## 🔮 Future Improvements

- [ ] Support for React and Vue output targets
- [ ] Figma API direct integration (no screenshot needed)
- [ ] Component-level granularity (generate individual components)
- [ ] Style token extraction for consistent theming

---

