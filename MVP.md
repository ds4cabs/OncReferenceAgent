# OncReferenceAgent — Project Plan (10-Week Internship)

**Intern:** TBD
**Project Type:** Scientific Intelligence Platform — AI-Powered Oncology Conference Intelligence Agent
**Timeline:** 10 weeks
**One-Sentence Description:** OncReferenceAgent is an automated oncology scientific intelligence workflow that continuously ingests AACR / ASCO / ESMO / ASH abstracts, maps them onto oncology ontologies, scores novelty and impact, and auto-generates chapterized competitor-landscape reports.

---

## Why This Project

A typical "summarize ASCO" exercise is a literature-review assignment. **OncReferenceAgent is different**: it builds a real biotech/pharma scientific intelligence platform that combines biomedical data, AI workflows, and a clear pharma business use case. From a career-development perspective this positions the intern closer to **AI-enabled strategy, translational intelligence, and decision-support systems** — a much higher-value trajectory than a generic chatbot or simple RAG demo.

## Core Problem

The big four oncology meetings (AACR / ASCO / ESMO / ASH) collectively publish **tens of thousands of abstracts per year**. Inside any single meeting there are too many abstracts, too many sub-indications, and too many competing modalities for any one person to track. Strategy, BD, translational, and R&D teams need to answer the same questions every cycle:

- Which assets are novel vs incremental?
- Which sponsors are gaining momentum in which tumor type?
- Which trials could change standard of care?
- Which modalities (ADC, bispecific, TCE, radioligand, cell therapy, ctDNA / MRD, PROTAC) are accelerating?
- Which KOLs are presenting on which company's data?
- Which abstracts are the *most disruptive* and which are noise?

OncReferenceAgent automates this first-pass intelligence at oncology-grade specificity.

---

## Seven Core Modules

### 1. Conference Abstract Ingestion
- Pull from AACR / ASCO / ESMO / ASH (HTML / PDF / API as available)
- PubMed E-utilities for related publications
- Company press-release ingestion for context
- Output: standardized abstract corpus with provenance

### 2. Oncology Ontology Mapping
- **Tumor type:** OncoTree / NCIt mapping (NSCLC subtype, HR+/HER2- breast, MSI-H CRC, etc.)
- **Target:** Open Targets and ChEMBL alignment
- **MOA / Modality:** ADC, bispecific, T-cell engager, radioligand, cell therapy, ctDNA / MRD, PROTAC / degrader, small molecule, immunotherapy combo
- **Endpoint extraction:** ORR, DCR, PFS, OS, HR, p-value, median follow-up
- **Trial phase + sponsor + line of therapy**

### 3. Novelty and Impact Scoring
- **Novelty:** target / MOA / combination first-in-class signals, novel biomarker stratification, novel modality-indication pairs
- **Impact:** magnitude vs SoC benchmark, sample size, blinded / RCT design, LBA / oral / poster type, regulatory potential
- Composite score per abstract → ranked watchlist

### 4. Competitor Landscape Extraction
- Company → asset → tumor-type → phase mapping
- Side-by-side modality maps within indication (e.g., HER2 ADCs across tumor types)
- Momentum signals: count of abstracts, oral / LBA share, year-over-year delta

### 5. LLM-Based Structured Summarization
- Per tumor type, per modality, per company chapters
- Synthesized from the **structured tables only** — no narrative invention
- Each generated paragraph carries inline references to source abstracts

### 6. Auto-Generated Chapterized Reports
- Markdown + DOCX export
- Standard chapters: executive summary · conference statistics · top tumor types · top modalities · LBA watchlist · company ranking · novelty leaderboard · disruption candidates · post-meeting tracking checklist
- Source table appendix with hyperlinks

### 7. Dashboard / Searchable Knowledge Base
- Streamlit or Dash app
- Faceted search: tumor type × modality × company × phase × endpoint
- Drill-down into a single abstract with extracted fields + source link

---

## Advanced Extensions (Stretch Goals)

- **KOL / company relationship graph** — NetworkX graph of authors ↔ institutions ↔ sponsors built from abstract author lists
- **Clinical trial linkage** — join abstracts to ClinicalTrials.gov NCT-IDs, surface unreported updates
- **"Most disruptive abstracts" ranking** — composite of novelty, effect size relative to SoC, modality momentum
- **Automatic relevance mapping to internal pipeline** — given a list of internal targets / indications, surface the abstracts most relevant to that program

---

## 10-Week Plan

| Week | Milestone |
|------|-----------|
| 1 | Define use case, oncology ontology scope, report template, data schema |
| 2 | Build abstract ingestion pipeline (AACR + ASCO first) |
| 3 | Tumor-type and target dictionaries (OncoTree + Open Targets) |
| 4 | Modality / MOA classification (ADC, bispecific, TCE, radioligand, ctDNA, cell therapy) |
| 5 | Endpoint extraction (ORR / PFS / OS / HR / p-value) + trial-phase tagging |
| 6 | Novelty + impact scoring, competitor landscape extraction |
| 7 | LLM-based structured summarization with source tracing |
| 8 | Chapterized report generator (Markdown + DOCX), dashboard skeleton |
| 9 | Stretch: KOL graph + clinical-trial linkage + disruption ranking |
| 10 | Final demo: end-to-end report on one full conference, prototype walkthrough |

---

## Final Deliverables

- Working Python pipeline (ingestion → ontology → scoring → report)
- Oncology dictionaries (tumor type, target, modality, endpoint)
- Example chapterized conference report (AACR or ASCO)
- Markdown + DOCX export functions
- Streamlit / Dash dashboard prototype
- QC checklist enforcing source-grounded numbers
- GitHub repository
- Final presentation

## Success Criteria

OncReferenceAgent is successful if it can:

- Ingest 5,000–10,000 oncology abstracts across at least one major meeting
- Map ≥ 90% of abstracts to a valid tumor type and target
- Classify modality with ≥ 85% accuracy on a held-out sample
- Produce a chapterized report that a senior oncology strategist would find usable
- Reduce manual pre-conference preparation time by **≥ 70%**
- Maintain **zero LLM-invented numerical claims** — every number traces back to a source row

---

## Realistic CV Entry

*Built OncReferenceAgent, an AI-powered oncology conference intelligence platform that ingested thousands of AACR / ASCO / ESMO / ASH abstracts, mapped each to oncology ontologies (tumor type, target, MOA, modality), scored novelty and impact, extracted competitor landscapes, and auto-generated chapterized scientific intelligence reports with full source provenance.*

- Engineered an oncology-specific ingestion + entity-extraction pipeline using OncoTree, Open Targets, ChEMBL, biomedical NER, and LLM-assisted extraction.
- Built a novelty + impact scoring framework and a competitor-landscape extractor that produces side-by-side modality maps per tumor type.
- Delivered chapterized Markdown / DOCX reports and a searchable dashboard; QC module ensured zero invented numerical claims.

## Tech Stack

Python · pandas · spaCy / scispaCy · OpenAI / Gemini API · OncoTree · NCIt · Open Targets · ChEMBL · ClinicalTrials.gov · PubMed E-utilities · NetworkX · Streamlit / Dash · markdown-pdf / `python-docx` · optional LangChain / LlamaIndex.
