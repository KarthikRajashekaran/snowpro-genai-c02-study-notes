[< Study Plan](./Study_Plan.md) | **📘 SnowPro Gen AI (C02) Exam Strategy** | [Practice Questions >](./Practice_Questions.md)
***

# SnowPro Specialty: Gen AI (C02) — Exam Strategy Guide

## Exam Overview

| Item | Detail |
|------|--------|
| **Exam** | SnowPro Specialty: Gen AI (**C02**, guide updated Apr 30, 2026) |
| **Format** | 65 questions, 115 minutes |
| **Passing score** | 750 / 1000 (scaled) |
| **Question types** | Multiple choice, multiple select, scenario/interactive |
| **Delivery** | Online proctored or test center |
| **Prerequisites** | None required; SnowPro Core knowledge assumed |

## Domain Breakdown & Study Allocation (C02)

> Weightings changed in C02. **Governance jumped to 29%** — the single biggest shift from C01. Budget accordingly.

### Domain 1: Snowflake for Gen AI Overview — **18%** (~12 Q)
- Cortex surface: Search, Analyst, Agents, Snowflake Intelligence, Cortex Code.
- Interfaces: AI Studio, SQL, REST API, **MCP**.
- Semantic Views (Autopilot, YAML, Verified Query, Custom Instructions).
- Cross-region inference; **CKE**; bring-your-own models (Model Registry, SPCS).

### Domain 2: Snowflake Gen AI Functions — **38%** (~25 Q) — largest domain
- The full **`AI_*` function catalog** — purpose, parameters, and the right function per task.
- `AI_COMPLETE` + **structured outputs**; `TRY_COMPLETE`; multimodal.
- **`VECTOR_*`** distance/aggregation functions; helpers (`AI_COUNT_TOKENS`, `SPLIT_TEXT_*`, `TO_FILE`, `PROMPT`).
- Use-case analysis (unstructured vs structured, multimodal); chat interfaces (Streamlit, multi-turn memory); pipelines; third-party models.

### Domain 3: Snowflake Gen AI Governance — **29%** (~19 Q) — grew the most
- Model access controls: **allowlist**, application roles, RBAC.
- Roles: **`CORTEX_USER`, `CORTEX_ANALYST_USER`, `CORTEX_AGENT_USER`, `CORTEX_EMBED_USER`**.
- Cost: **usage-history views**, object tagging, per-service cost drivers, Provisioned Throughput.
- Safety: **Cortex Guard**, **AI_REDACT**, reducing hallucinations/bias, REST API auth.
- **AI Observability** with **TruLens** (metrics, comparisons, tracing, event tables).

### Domain 4: Snowflake Document Processing — **15%** (~10 Q) — renamed & grew
- **`AI_PARSE_DOCUMENT`** (OCR vs LAYOUT, `page_split`, `page_limit`).
- **`AI_EXTRACT`** (schema/response format, prompting).
- Pipelines with **Streams + Tasks**; `GET_PRESIGNED_URL` / `BUILD_SCOPED_FILE_URL`; **arctic-extract fine-tuning**.

See the [Study Plan](./Study_Plan.md) for a week-by-week schedule.

## Key Function Cheat Sheet (C02)

C02 is built around the **`AI_*` (AISQL)** functions. The `SNOWFLAKE.CORTEX.*` namespace still exists underneath and some legacy names remain valid, but study the `AI_*` names first.

```sql
-- Generation
AI_COMPLETE(model, prompt [, options])       -- text/JSON generation; structured outputs via response_format
TRY_COMPLETE(model, prompt [, options])      -- error-safe variant (NULL instead of error)
PROMPT('template {0} {1}', col_a, col_b)     -- build prompts / multimodal prompt objects

-- Task-specific
AI_CLASSIFY(input, categories)               -- single/multi-label, supports text & images
AI_FILTER(predicate)                         -- boolean NL filter, great in WHERE
AI_AGG(col, task)                            -- reduce many rows to one insight (no row limit)
AI_SUMMARIZE_AGG(col)                        -- aggregate summarization across rows
SUMMARIZE(text)                              -- single-text summary
AI_SENTIMENT(text)                           -- sentiment (with entity-level options)
AI_TRANSLATE(text, from, to)                 -- translation
AI_EXTRACT(text, response_format)            -- structured field extraction
AI_SIMILARITY(a, b)                          -- semantic similarity score
AI_TRANSCRIBE(audio_file)                    -- speech-to-text
AI_REDACT(text)                              -- remove/mask sensitive data (PII)

-- Embeddings & documents
AI_EMBED(model, text)                        -- generate embedding vectors
AI_PARSE_DOCUMENT(file, {'mode':'LAYOUT'})   -- parse PDF/doc; OCR or LAYOUT mode

-- Helpers
AI_COUNT_TOKENS(model, text)                 -- token estimate for cost/limits
SPLIT_TEXT_RECURSIVE_CHARACTER(text, ...)    -- chunking for RAG
SPLIT_TEXT_MARKDOWN_HEADER(text, ...)        -- markdown-aware chunking
TO_FILE(stage_path)                          -- build a FILE object for multimodal input
```

```sql
-- Vector functions (know when to use each metric)
VECTOR_COSINE_SIMILARITY(v1, v2)   -- higher = more similar; default for text
VECTOR_INNER_PRODUCT(v1, v2)       -- dot product
VECTOR_L2_DISTANCE(v1, v2)         -- Euclidean; lower = more similar
VECTOR_L1_DISTANCE(v1, v2)         -- Manhattan
VECTOR_NORMALIZE(v) / VECTOR_TRUNCATE(v, n)
VECTOR_SUM / VECTOR_MIN / VECTOR_MAX / VECTOR_AVG   -- aggregations
```

**Models:** Cortex hosts LLMs from OpenAI, Anthropic, Meta (Llama), Mistral AI, DeepSeek, and Snowflake (Arctic). Specific model names change frequently — study *how to choose* (latency/size, accuracy, capability, cost, Provisioned Throughput) rather than memorizing an exact roster.

## Exam Tips

### Time management
- ~1.75 min/question. Flag-and-return on anything that isn't obvious in 30 seconds.

### Scenario questions (most of the exam)
1. Identify the **business goal** and constraints (cost, latency, structure, privacy).
2. Map it to the **right Cortex service** (Search vs Analyst vs Agents vs Intelligence) or the **right `AI_*` function**.
3. Watch keywords: *structured fields* → `AI_EXTRACT`; *preserve tables/layout* → `AI_PARSE_DOCUMENT` LAYOUT; *chatbot over PDFs* → Cortex Search; *NL to SQL over a semantic model* → Cortex Analyst.

### Multiple-select
- Count the required selections. Treat each option independently.

## Common Pitfalls (C02-specific)

1. **Old vs new naming** — the exam favors `AI_*`. Don't pick a fabricated `DOCUMENT_AI.*` or `CORTEX.CHAT` distractor.
2. **OCR vs LAYOUT** — LAYOUT preserves structure/tables as markdown; OCR returns raw text.
3. **Wrong usage view** — daily AI-service credit usage is `SNOWFLAKE.ACCOUNT_USAGE.METERING_DAILY_HISTORY` filtered on `SERVICE_TYPE='AI_SERVICES'`, *not* `QUERY_HISTORY` or `INFORMATION_SCHEMA`.
4. **Role confusion** — `CORTEX_USER` (functions) ≠ `CORTEX_ANALYST_USER` ≠ `CORTEX_AGENT_USER` ≠ `CORTEX_EMBED_USER`.
5. **AI_AGG vs SUMMARIZE** — `AI_AGG`/`AI_SUMMARIZE_AGG` reduce across many rows (no row limit); `SUMMARIZE` is single-text.
6. **Memory in chat** — its role is to **maintain context across turns**, not to store credentials, speed responses, or cap tokens.
7. **Cortex Search chunking** — remember recursive/markdown split, chunk sizing, embedding model, and semantic reranking.

## Readiness Metrics
- Consistently 80%+ on practice sets; ≥75% in each domain.
- Can implement an end-to-end RAG app and every Domain 2/4 function hands-on.
- Can answer any governance question about roles, allowlists, usage views, and observability from memory.

## Maintaining Your Certification
Certifications expire **2 years** after the issue date. Recertify through the **Continuing Education (CE)** program (complete eligible Instructor-Led Training) or by earning an **equivalent or higher** SnowPro certification. A valid certification is required to participate in CE.

***
[< Study Plan](./Study_Plan.md) | **📘 SnowPro Gen AI (C02) Exam Strategy** | [Practice Questions >](./Practice_Questions.md)
