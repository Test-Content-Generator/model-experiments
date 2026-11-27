# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Experimental repo for testing LLM and ML techniques, primarily focused on embedding models and semantic similarity. Work is done in Jupyter notebooks organized by topic.

## Setup

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

- Python 3.14, managed via local `.venv`
- API key for Google Gemini is expected in `.env` (loaded automatically by `google-genai` client)

## Project Structure

- `embeddings/` — Jupyter notebooks experimenting with Google Gemini embedding models
  - `gemini-embedding-1.ipynb` — Semantic similarity using `gemini-embedding-001` (task type `SEMANTIC_SIMILARITY`, cosine similarity via scikit-learn, Pydantic models for structured results)
  - `gemini-embedding-2.ipynb` — Early exploration of `gemini-embedding-2` model
- `requirements.txt` — Pinned dependencies (no pyproject.toml or setup.py)

## Key Libraries

- `google-genai` — Google Gemini API client (`from google import genai`)
- `sklearn.metrics.pairwise.cosine_similarity` — For comparing embedding vectors
- `pydantic` — Structured data models (e.g., `TextWithEmbeddings`)
- `pandas` — Similarity matrix display

## Conventions

- Notebooks use `genai.Client()` which picks up the API key from environment
- Embedding results use `types.EmbedContentResponse` and `types.EmbedContentConfig` from `google.genai`
- New experiments should go in topic-specific subdirectories as notebooks
