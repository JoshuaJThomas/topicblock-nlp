# TopicBlock

A privacy-first browser extension that filters web content by topic and sentiment — all on-device, no data sent to any server.

Built for the FAI module (MSc AI, NCI Dublin 2025) as a group project. The full source code lives at [amit27592/TopicBlock](https://github.com/amit27592/TopicBlock) — I'm a contributor there.

## What it does

TopicBlock runs a two-part ML pipeline locally. The browser extension (TypeScript, Manifest V3) handles DOM segmentation and user interaction. A native Python component does the actual inference — topic classification and sentiment analysis — over Chrome Native Messaging.

The key design choice was keeping everything local. Zero-shot topic classification means users can block arbitrary topics without retraining, and the SQLite-backed embedding cache keeps it fast on repeated content.

Supported sites: Reddit, Hacker News, YouTube.

## Architecture

```
Browser extension (TypeScript)
  ├── DOM segmentation + site adapters (Reddit, HN, YouTube)
  ├── Filter actions: Hide / Blur / Remove
  └── Native messaging client

Native component (Python)
  ├── Text preprocessing + language detection (FastText)
  ├── Topic model — zero-shot via MiniLM-L6-v2 or BGE-small
  ├── Sentiment — VADER (fast) or DistilBERT (accurate)
  └── SQLite LRU cache for repeated content
```

## Stack

TypeScript, Manifest V3, Python 3.10+, HuggingFace, VADER, FastText, SQLite

## Report

`FAI_TopicBlock_Report.pdf` — the academic write-up covering the design, architecture decisions, and evaluation.

## Full source

[github.com/amit27592/TopicBlock](https://github.com/amit27592/TopicBlock)

---

MSc Artificial Intelligence, NCI Dublin 2025  
Joshua Thomas & Amit Gupta
