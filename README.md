# AI Resume Analyzer

A Streamlit app that compares a resume (PDF) with a job description and uses an LLM to report the match, list missing skills, and draft application material.

**Live demo:** https://ai-resume-analyzer-bala.streamlit.app/

## Features

- **Match score**: a percentage match with the job description, the reasoning behind it, and suggestions to improve the resume.
- **Missing skills**: the skills the job description asks for that the resume doesn't show.
- **Cover letter**: a draft written from the resume and the job description.
- **"About Me"**: a first-person introduction to use in interviews.
- **Download**: any result can be saved as a text file.

## How it works

1. PyMuPDF extracts the text from the uploaded PDF.
2. Each feature sends a focused prompt to **Gemini 2.0 Flash** (`google-genai`).
3. If the Gemini call fails, the app falls back to **OpenRouter** (`openrouter/auto`).

## Tech stack

Python · Streamlit · PyMuPDF · Google Gemini API · OpenRouter API

## Run locally

```bash
git clone https://github.com/BalaMSD7781/AI-Resume-Analyzer.git
cd AI-Resume-Analyzer
pip install -r requirements.txt
cp .env.example .env   # then add your own API keys
streamlit run App.py
```

On Streamlit Cloud, add `API_KEY` and `OPENROUTER_API_KEY` under **Secrets** instead of using a `.env` file.

## Project structure

```
├── App.py              # Streamlit app: PDF parsing, prompts, LLM calls, UI
├── requirements.txt
├── .env.example        # The environment variables the app expects
└── .devcontainer/      # GitHub Codespaces setup
```
