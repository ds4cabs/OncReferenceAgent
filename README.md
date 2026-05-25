# OncReferenceAgent

[![CABS: ds4cabs](https://img.shields.io/badge/CABS-ds4cabs-1f4b99?logo=github)](https://github.com/ds4cabs)
[![GitHub Pages: live](https://img.shields.io/badge/GitHub_Pages-live-brightgreen?logo=github)](https://ds4cabs.github.io/OncReferenceAgent/)
![CABS: 2026](https://img.shields.io/badge/CABS-2026-6f42c1)
![status: MVP in progress](https://img.shields.io/badge/status-MVP_in_progress-f1c40f)
![type: Scientific Intelligence Platform](https://img.shields.io/badge/type-Scientific_Intelligence_Platform-1f6feb)
![domain: Oncology Conference Intelligence](https://img.shields.io/badge/domain-Oncology_Conference_Intelligence-d63384)

**Intern:** TBD
**Project Type:** Scientific Intelligence Platform — AI-powered oncology conference intelligence agent

## Overview
OncReferenceAgent is an **AI-Powered Oncology Conference Intelligence Agent** that continuously monitors AACR, ASCO, ESMO, and ASH — ingesting thousands of abstracts, mapping them onto oncology ontologies (tumor type / target / MOA / modality), scoring novelty and impact, extracting competitor landscapes, and auto-generating chapterized scientific intelligence reports.

Unlike a generic conference summarizer, OncReferenceAgent is purpose-built for oncology: it understands tumor histology, response endpoints (ORR / DCR / PFS / OS / HR), modality stratification (ADC, bispecific, T-cell engager, radioligand, cell therapy, ctDNA / MRD), and competitive pipeline positioning.

## Deliverable
- Continuous abstract ingestion across AACR / ASCO / ESMO / ASH
- Oncology ontology mapping pipeline (tumor type, target, MOA, modality)
- Novelty + impact scoring
- Competitor landscape extraction with company → asset → indication mapping
- LLM-based structured summarization (per tumor type, per modality, per company)
- Auto-generated chapterized Markdown / DOCX reports
- Searchable dashboard / knowledge base over the corpus
- (Stretch) KOL ↔ company relationship graph, clinical-trial linkage, most-disruptive ranking

## Core Tools
- AACR / ASCO / ESMO / ASH abstract exports (HTML / PDF / JSON)
- PubMed E-utilities
- ClinicalTrials.gov API (trial linkage)
- Open Targets (oncology target / disease ontology)
- ChEMBL (modality / mechanism enrichment)
- OncoTree / NCIt (tumor ontology)
- Company press releases and 8-K filings
- KOL / social-signal feeds (X, LinkedIn) — optional

## Tech Stack
Python · pandas · spaCy / scispaCy · OpenAI / Gemini API · ClinicalTrials.gov · PubMed · OncoTree · Open Targets · Streamlit / Dash · NetworkX (graphs) · markdown-pdf / `python-docx` · optional LangChain / LlamaIndex.

## Notes
Two non-negotiables: (1) every quantitative claim in the final report must trace back to a source abstract / row — no LLM-invented numbers; (2) oncology-specific ontology mapping must be the first-class extraction step, not an afterthought, because all downstream analytics (novelty scoring, competitor maps, disruption ranking) depend on it.
