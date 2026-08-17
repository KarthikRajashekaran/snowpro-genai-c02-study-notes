[< Home](../README.md) | **📅 SnowPro Gen AI (C02) Study Plan** | [Practice Questions >](./Practice_Questions.md)
***

# SnowPro Specialty: Gen AI (C02) — Study Plan

A topic-by-topic plan mapped directly to the **C02 exam guide (April 30, 2026)**. Snowflake estimates **10–13 hours** to work through its official guide; budget more if you also do hands-on labs (recommended). This plan assumes ~3–4 weeks of part-time study on top of existing Snowflake experience.

## 📊 Where to spend your time

Study time should track exam weight. Governance nearly doubled in importance from C01 — do not under-invest in it.

| Domain | Weight | ~Questions* | Suggested time | Priority |
|--------|:------:|:-----------:|:--------------:|----------|
| 2. Gen AI Functions | 38% | ~25 | 12–14 h | 🔴 Highest |
| 3. Gen AI Governance | 29% | ~19 | 9–11 h | 🔴 High (grew a lot) |
| 1. Gen AI Overview | 18% | ~12 | 5–7 h | 🟡 Medium |
| 4. Document Processing | 15% | ~10 | 5–6 h | 🟡 Medium |

\*65 total questions, apportioned by weight. Approximate — Snowflake does not publish exact per-domain counts.

## 🗓️ 4-Week Plan

### Week 1 — Foundations (Domain 1, 18%)
**Goal:** Understand the Cortex surface and how the pieces compose.
- [ ] 1.1 Cortex overview — model families (OpenAI, Anthropic, Meta, Mistral, DeepSeek, Arctic), fully-managed model hosting.
- [ ] 1.2 Interfaces — **AI Studio, SQL, REST API**, and **MCP**.
- [ ] 1.3 Vector data type basics (details in Domain 2).
- [ ] 1.4 **Cortex Search** (RAG, multi-index, access control) + **Cortex Analyst** (text-to-SQL, **Semantic Views**, Autopilot, YAML, **Verified Query**, Custom Instructions).
- [ ] 1.5 **Cortex Agents**, **Snowflake Intelligence**, **Cortex Code / CLI**, **Copilot Inline**, **cross-region inference** (`CORTEX_ENABLED_CROSS_REGION`), **CKE**.
- [ ] 1.6 Bring-your-own models — **Model Registry**, **Snowpark Container Services**, Cortex Fine-tuning.
- **Hands-on:** run `AI_COMPLETE`; build a tiny Cortex Search service; open Cortex Analyst on a semantic view.

### Week 2 — Functions (Domain 2, 38%) — the big one
**Goal:** Be able to pick and write the right `AI_*` function for any task.
- [ ] 2.1 AISQL catalog — memorize *what each function does*: `AI_COMPLETE`, `AI_CLASSIFY`, `AI_EXTRACT`, `AI_PARSE_DOCUMENT`, `AI_SENTIMENT`, `SUMMARIZE`, `AI_SUMMARIZE_AGG`, `AI_TRANSLATE`, `AI_EMBED`, `AI_FILTER`, `AI_AGG`, `AI_SIMILARITY`, `AI_TRANSCRIBE`, `AI_REDACT`.
- [ ] 2.2 `AI_COMPLETE` deep dive — **structured outputs (JSON schema)**, options, `TRY_COMPLETE`, multimodal/single-file complete.
- [ ] 2.3 `VECTOR_*` (inner product, L1/L2 distance, cosine similarity, truncate, normalize, sum/min/max/avg) + helpers (`AI_COUNT_TOKENS`, `SPLIT_TEXT_RECURSIVE_CHARACTER`, `SPLIT_TEXT_MARKDOWN_HEADER`, `TO_FILE`, `PROMPT`).
- [ ] 2.4 Use-case analysis — unstructured vs structured; **multimodal audio/image**; Cortex Search chunking/reranking; Cortex Analyst VQR; **performance & Provisioned Throughput**.
- [ ] 2.5 Chat interfaces (**Streamlit in Snowflake**, multi-turn memory, messages array), pipelines (extraction/enrichment/augmentation/transformation), third-party models (SPCS + Model Registry).
- **Hands-on:** run every function once; build a structured-output extraction; a Streamlit multi-turn chat.

### Week 3 — Governance (Domain 3, 29%) + Document Processing (Domain 4, 15%)
**Governance:**
- [ ] 3.1 Model access controls — **allowlist** (`CORTEX_MODELS_ALLOWLIST`), **application roles**, RBAC; **Cortex Guard**; **AI_REDACT**; reducing hallucinations/bias; **REST API auth** (key-pair JWT / OAuth / PAT).
- [ ] 3.2 RBAC roles — **`CORTEX_USER`, `CORTEX_ANALYST_USER`, `CORTEX_AGENT_USER`, `CORTEX_EMBED_USER`**; grant/revoke; per-service privileges (Analyst, Search, Agents, Intelligence).
- [ ] 3.3 Cost — per-service cost types; **usage-history views** (`METERING_DAILY_HISTORY`, `CORTEX_ANALYST_USAGE_HISTORY`, `CORTEX_AISQL_USAGE_HISTORY`, `CORTEX_SEARCH_DAILY_USAGE_HISTORY`, `CORTEX_REST_API_USAGE_HISTORY`, `CORTEX_PROVISIONED_THROUGHPUT_USAGE_HISTORY`); **object tagging**; usage quotas.
- [ ] 3.4 **AI Observability** — evaluation metrics, comparisons, tracing, logging, **event tables**, **TruLens SDK**, RAG Triad.

**Document Processing:**
- [ ] 4.1 `AI_PARSE_DOCUMENT` (**OCR vs LAYOUT**, `page_split`, `page_limit`) + `AI_EXTRACT` (schema, prompting).
- [ ] 4.2 Prep/upload docs & requirements; **Streams + Tasks** pipelines; troubleshooting (`GET_PRESIGNED_URL`, `BUILD_SCOPED_FILE_URL`); privileges; cost; **arctic-extract fine-tuning**.
- **Hands-on:** parse a PDF both modes; extract invoice fields; wire a Stream+Task pipeline.

### Week 4 — Integration & Review
- [ ] Rebuild an **end-to-end RAG app** (parse → chunk → embed → Cortex Search → `AI_COMPLETE`) — ties all four domains together.
- [ ] Work all [Practice Questions](./Practice_Questions.md) incl. official C02 samples; review every miss.
- [ ] Re-drill weakest domain (usually Governance).
- [ ] Read [Exam Strategy](./Exam_Strategy.md); take a timed pass.

## ✅ Readiness checklist

You are ready when you can, without looking anything up:
- [ ] Name the right `AI_*` function for a described task (classify vs extract vs filter vs agg vs redact…).
- [ ] Explain when to use **Cortex Search vs Cortex Analyst vs Cortex Agents vs Snowflake Intelligence**.
- [ ] Choose **OCR vs LAYOUT** mode for `AI_PARSE_DOCUMENT` given a document goal.
- [ ] List the four `CORTEX_*_USER` database roles and what each unlocks.
- [ ] Point to the correct **usage-history view** for a given cost question (e.g., daily AI-service credits → `METERING_DAILY_HISTORY` with `SERVICE_TYPE='AI_SERVICES'`).
- [ ] Describe how **TruLens** evaluates a RAG app (context relevance, groundedness, answer relevance).
- [ ] Restrict which models an account/role can use via allowlist + application roles.
- [ ] Explain **structured outputs**, **Provisioned Throughput**, and **cross-region inference**.

## 🔁 Maintaining certification
Certs expire **2 years** after issue. Recertify via the Snowflake **Continuing Education (CE)** program (eligible Instructor-Led courses) or by earning an equivalent/higher SnowPro certification. You must hold a valid certification to participate in CE.

***
[< Home](../README.md) | **📅 SnowPro Gen AI (C02) Study Plan** | [Practice Questions >](./Practice_Questions.md)
