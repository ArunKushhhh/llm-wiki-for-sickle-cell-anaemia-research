# raw/

This directory contains your **immutable source documents**.

Drop papers, articles, notes, and other references here. The LLM reads from this directory but **never modifies it**. This is your source of truth.

## Supported file types
- `.md` — Markdown (articles clipped with Obsidian Web Clipper, personal notes)
- `.pdf` — Research papers, reports
- `.txt` — Plain text

## Subdirectories
- `assets/` — Images downloaded from clipped articles (auto-managed by Obsidian Web Clipper)

## How to add sources
1. Drop the file here
2. In a new session, tell the LLM: `ingest <filename>`

The LLM will process the source and update the wiki accordingly.
