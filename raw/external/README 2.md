# 🧠 PRISMA-KB — Vault guide

> **LLM-Powered Academic Knowledge Base Builder for Systematic Reviews**
>
> *Inspired by [Andrej Karpathy's LLM knowledge base workflow](https://x.com/karpathy/status/2039805659525644595) (X post) — rebuilt as a proper Python open-source tool.*

This file lives **inside your vault** (`vault/README.md`). The vault holds research data; the **code repo** (clone of [PRISMA-KB](https://github.com/dschloe/PRISMA-KB)) contains scripts and `prisma_kb/`. Paths below are relative to the vault root.

---

## Vault layout

```
vault/
├── 01_raw/
│   ├── pdf/                    # PDFs (citation_key.pdf)
│   └── abstracts/              # e.g. missing_abstracts.md
├── 02_screening/
│   ├── included.csv            # screened-in corpus for compile
│   ├── compile_auto_progress.json   # optional: compile_auto.py progress
│   └── …
├── 03_notes/
│   ├── papers/                 # per-paper notes ({citation_key}.md)
│   └── summaries/              # RQ answers, sr_draft_*, index.md
├── 04_concepts/
│   ├── competency_taxonomy.json
│   └── *.md                    # concept wiki pages
├── 05_indexes/
│   └── paper_index.json
├── 06_outputs/
│   └── review_drafts/          # export outputs, rq_coverage, sections/
└── README.md                   # this file
```

**Note metadata (compile):** each paper note can record **Model**, **Compiled** (date), **Source** (`pdf` / `abstract` / `missing_abstracts`) under `## Bibliographic Info`.

**Logs (repo root, optional):** `compile_auto.log`, `cron_path_test.log` — if you schedule `scripts/compile_auto.py` or cron smoke tests from the project directory.

**Data APIs vs PDFs:** OpenAlex / Scopus keys feed **record metadata and exports**; many papers still need **manual or library PDF** into `01_raw/pdf/`. Single reference in the code repo: [`docs/DATA_SOURCES_AND_PDF_WORKFLOW.md`](../docs/DATA_SOURCES_AND_PDF_WORKFLOW.md).

---

## Pipeline (conceptual)

```
raw PDFs + included.csv
      ↓  scripts/compile.py | scripts/compile_auto.py
vault/03_notes/papers/*.md + vault/04_concepts/
      ↓  index rebuild (paper_index.json)
      ↓  scripts/query.py (RQ / ad-hoc)
vault/03_notes/summaries/rq*_answer.md
      ↓  scripts/export.py
vault/06_outputs/review_drafts/sr_draft_*.md
      ↓  --file-back
summaries/ + paper_index export row
```

---

## Features (current stack)

- **Ingest / compile** — PDF → structured notes; **Gemini** via **`google-genai`** (`prisma_kb/llm/gemini_client.py`); also Claude, OpenAI, Ollama.
- **`scripts/compile_auto.py`** — PDF-only batch, **429** wait/resume, **`compile_auto_progress.json`**, optional **caffeinate** on macOS.
- **Concept extraction** — JSON from LLM responses with fenced **`json`** blocks + fallback parsing (`concept_extractor.py`).
- **Query** — `scripts/query.py` — RQ synthesis, provider-specific outputs.
- **Export** — `scripts/export.py` — `sr_draft_{provider}.md`, sections, `--type final`, `--review-mode`, **`format_citation()`**, `--file-back`.
- **Lint** — `scripts/lint.py` (taxonomy, rq_coverage, consistency).
- **Scheduling** — e.g. **crontab** daily **08:10 UTC = 17:10 KST** for `compile_auto`; see `scripts/crontab_compile_auto.example` and `scripts/crontab_path_test.example` in the repo.

Core dependencies include **`google-genai`** and **`anthropic`**; optional extras remain in `pyproject.toml` (e.g. OpenAI, DeepL).

---

## Repo layout (reference)

```
prisma-kb/
├── prisma_kb/
│   ├── compile/     # summarizer, concept_extractor, wiki_writer
│   ├── llm/         # base, gemini_client, claude_client, openai_client, ollama_client
│   ├── query/       # qa_engine, search
│   └── …
├── scripts/
│   ├── compile.py
│   ├── compile_auto.py
│   ├── query.py
│   ├── export.py
│   ├── lint.py
│   ├── cron_path_test.py
│   ├── crontab_path_test.example
│   └── crontab_compile_auto.example
├── cli.py
├── config.yaml
├── pyproject.toml
└── README.md
```

---

## Quickstart (from cloned repo)

```bash
cd prisma-kb
uv sync
# API keys: .env or export — GEMINI_API_KEY, ANTHROPIC_API_KEY, OPENAI_API_KEY as needed
```

```bash
# Compile included corpus (example)
uv run python scripts/compile.py --provider gemini --model gemini-2.5-flash

# Long batch with quota handling (PDFs only, progress file)
uv run python scripts/compile_auto.py

# RQ answers + export
uv run python scripts/query.py --rq all --provider gemini
uv run python scripts/export.py --type review --provider gemini
```

Point **`config.yaml`** `vault` path at this vault if using `cli.py` / shared config.

---

## Motivation

| Paper | Type | Status |
|------|------|--------|
| *Human Competencies in Human–AI Collaboration: A Systematic Review* | SSCI Journal Article | In progress |
| *AI Transition and Talent Development in Korea: …* | PhD dissertation | Planned |

> As society transitions from an era valuing human expertise to one augmented by AI — **what competencies does this new era demand, and how well are Korean institutions responding?**

---

## Research context (Paper 1)

**Working title:** *Human Competencies Required for Effective Human–AI Collaboration: A Systematic Review*

| RQ | Question |
|----|----------|
| RQ1 | How is Human–AI Collaboration defined across the literature? |
| RQ2 | What human competencies are identified as necessary for effective HAC? |
| RQ3 | What factors influence HAC effectiveness? |
| RQ4 | In what industry and task contexts has HAC research been conducted? |
| RQ5 | What are the current research gaps and future directions? |

**PRISMA 2020** · Databases: Scopus, WoS, Scholar, OpenAlex (as applicable).

---

## Roadmap (high level)

**Done (representative):** ingest/compile pipeline, `paper_index`, RQ query + export, multi-provider LLM, taxonomy lint, filing back, Gemini SDK migration, compile automation, cron examples.

**Next:** multi-model batch/compare tooling (`multi_model_query_strategy.md`), methodology tables / `methodology_review.md` depth, Marp/slides polish, SR manuscript revision.

---

## Design principles

1. **LLM assists the wiki** — you curate sources; the pipeline compiles and indexes.
2. **CLI-first** — scripts + `uv run`; vault stays data-only.
3. **Vault ≠ code** — this tree is research data; reproducibility via your own backups or selective export.
4. **LLM-agnostic** — switch provider/model via CLI or config.
5. **Iterative** — exports and summaries file back into the vault where configured.

---

## Acknowledgements

Workflow inspired by [Andrej Karpathy](https://karpathy.ai/) and [this note on LLM knowledge-base practice](https://x.com/karpathy/status/2039805659525644595). PRISMA-KB formalizes that idea for systematic-review-sized corpora.

---

## License

MIT — see the repository `LICENSE` / `pyproject.toml`.

---

*Built for researchers who take knowledge management as seriously as the research itself.*
