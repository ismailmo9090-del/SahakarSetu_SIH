---
license: cc-by-4.0
language:
  - hi
  - en
task_categories:
  - question-answering
  - text-retrieval
tags:
  - hindi
  - hinglish
  - cooperative
  - legal
  - rag
  - agriculture
pretty_name: Sahakar Setu Corpus
size_categories:
  - n<1K
---

# Sahakar Setu Corpus — Cooperative Governance & Legal Assistance Knowledge Base

Curated Hindi/Hinglish knowledge corpus powering **Sahakar Setu** (सहकार सेतु), the multilingual cooperative governance & legal assistance assistant built for **Smart India Hackathon 2026, Problem Statement 26088** (Ministry of Cooperation / NCCT) by Team **LexNova** (Team ID 131559).

## What's inside

| File | Description | Size |
|---|---|---|
| `corpus_passages.json` | 333 authored knowledge passages with source document, section reference and category | 333 rows |
| `eval_queries.json` | 13 Hinglish evaluation queries with expected source document | 13 rows |

**Domains covered (6):**
1. **laws core** — cooperative acts, by-laws, membership, voting, surplus distribution
2. **PMFBY ops** — crop insurance operations, premium, claims
3. **PACS services** — Primary Agricultural Credit Society services, KCC, loans
4. **schemes ministry** — PM-Kisan and other ministry schemes
5. **grievance redressal** — complaint filing, escalation to Registrar/Ombudsman
6. **financial literacy** — byaj, EMI, bachat, borrowing decisions

## Passage format

```json
{
  "id": 1,
  "source_doc": "laws core",
  "section_ref": "MSCS Act 2002 §…",
  "category": "laws",
  "passage_text": "…"
}
```

## How the corpus is used (RAG pipeline)

The live assistant retrieves from this corpus with a deterministic BM25 search:

- **Hinglish keyword expansion** — `member → sadasya/sadasyata`, `premium → kiraya/bhugtan` (60+ mappings)
- **Okapi BM25** — k1 = 1.2, b = 0.75, IDF = log(1 + (N − df + 0.5)/(df + 0.5))
- **Phrase boosts** — exact bigram +3.0, full-phrase +2.5
- **Top-5** passages above score 0.2, deterministic tie-break by id
- **Citation enforcement** — every answer must cite `[Source: doc, section]`; otherwise the assistant declines with a verified "no answer" phrase

**Evaluation result:** 13/13 eval queries return the correct source document in the top-3 retrieved passages.

## Live system

- **IVR voice assistant:** +1 346 998 6840 (Hindi, feature-phone, no internet needed)
- **Server:** https://sahakar-setu-server.onrender.com (health: `/health`)
- **Docs:** GitHub Pages — Sahakar Setu SIH 2026 documentation site

## Citation

```bibtex
@misc{sahakarsetu2026,
  title     = {Sahakar Setu Corpus: Cooperative Governance \& Legal Assistance Knowledge Base},
  author    = {LexNova},
  year      = {2026},
  note      = {SIH 2026, PS 26088, Ministry of Cooperation / NCCT}
}
```
