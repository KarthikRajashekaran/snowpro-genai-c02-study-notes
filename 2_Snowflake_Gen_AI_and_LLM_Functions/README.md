[< Domain 1](../1_Snowflake_for_Gen_AI_Overview/README.md) | **📘 Domain 2: Snowflake Gen AI Functions** | [Domain 3 >](../3_Snowflake_Gen_AI_Governance/README.md)
***

# Domain 2: Snowflake Gen AI Functions

This domain focuses on the practical implementation of Snowflake's generative AI functions — the **AI_\*** (AISQL) family, vector and helper functions, and the use-case patterns that combine them. It is the most heavily weighted domain of the **SnowPro Specialty: Gen AI (C02)** exam at **38%** (down from 40% on the prior version), and is almost entirely hands-on.

> **Naming note:** The C02 exam is built around the **AI_\*** function family (`AI_COMPLETE`, `AI_CLASSIFY`, `AI_EMBED`, …). These are the current, preferred names. They are implemented in the `SNOWFLAKE.CORTEX` schema, and many have older aliases (`COMPLETE`, `CLASSIFY_TEXT`, `EMBED_TEXT_768`, …) that still work. Learn the `AI_*` name first, then recognize the legacy alias.

## 🎯 Domain Overview

This domain covers the full AISQL catalog (general + task-specific functions), structured outputs, the VECTOR distance/aggregate functions, text-splitting and file helpers, and how to assemble these into real solutions: RAG and Cortex Search, text-to-SQL with Cortex Analyst, multimodal (audio/image) analytics, chat interfaces (Streamlit in Snowflake, Snowflake Intelligence), Cortex-in-pipelines, and running third-party models via Snowpark Container Services and the Model Registry.

## 📚 Table of Contents

### **2.1 Apply AI functions — the AISQL catalog**
- [2.1 AISQL Function Catalog (general + task-specific)](./2.1_Cortex_LLM_Functions.md)
- [2.2 AI_COMPLETE / COMPLETE Deep Dive (structured outputs, options, multimodal)](./2.2_Cortex_LLM_Complete_Functions.md)
- [2.3 Vector & Helper Functions](./2.3_Vector_and_Helper_Functions.md)

### **2.2 Perform data analysis given a use case**
- [2.4 Data Analysis by Use Case (unstructured, structured, multimodal, performance)](./2.4_Data_Analysis_By_Use_Case.md)

### **2.3 / 2.4 / 2.5 Chat interfaces, pipelines, third-party models**
- [2.5 Chat Interfaces, Pipelines & Third-Party Models](./2.5_Chat_Interfaces_and_Pipelines.md)

## 🗺️ C02 Domain 2 Sub-Objectives

| # | Sub-objective | Covered in |
|---|---------------|-----------|
| **2.1** | Apply AI functions (general, task-specific, vector, helper) | 2.1, 2.2, 2.3 |
| **2.2** | Perform data analysis given a use case (unstructured/structured/multimodal, Cortex Search, Cortex Analyst, performance) | 2.4 |
| **2.3** | Build or interact with interfaces to chat with data | 2.5 |
| **2.4** | Apply Snowflake Cortex functions in data pipelines | 2.5 |
| **2.5** | Run third-party models (SPCS, Model Registry) | 2.5 |

## 🔗 AISQL Function Catalog (memorize this map)

### **General**
- `AI_COMPLETE()` — text/multimodal completion; supports **structured outputs** (JSON schema via `response_format`). Alias: `COMPLETE`.

### **Task-specific**
- `AI_CLASSIFY()` — single/multi-label text & image classification (alias `CLASSIFY_TEXT`)
- `AI_FILTER()` — natural-language boolean predicate for `WHERE`/joins/aggregations
- `AI_AGG()` — reduce many rows to one insight, no context-window limit
- `AI_SUMMARIZE_AGG()` — aggregate summary across many rows
- `AI_SIMILARITY()` — semantic similarity between two inputs (embeds internally)
- `AI_SENTIMENT()` — sentiment, incl. entity/category-level (alias `SENTIMENT`)
- `AI_EXTRACT()` — extract fields/answers from text or documents
- `AI_PARSE_DOCUMENT()` — OCR/layout parsing of PDFs & images (alias `PARSE_DOCUMENT`)
- `AI_TRANSLATE()` — language translation (alias `TRANSLATE`)
- `AI_EMBED()` — generate vector embeddings (aliases `EMBED_TEXT_768` / `EMBED_TEXT_1024`)
- `AI_TRANSCRIBE()` — speech-to-text from audio files
- `AI_REDACT()` — redact PII / sensitive spans
- `SUMMARIZE()` / `AI_SUMMARIZE_AGG()` — summarization

### **Vector functions**
- Distance/similarity: `VECTOR_INNER_PRODUCT`, `VECTOR_L1_DISTANCE`, `VECTOR_L2_DISTANCE`, `VECTOR_COSINE_SIMILARITY`
- Vector math: `VECTOR_TRUNCATE`, `VECTOR_NORMALIZE`
- Vector aggregates: `VECTOR_SUM`, `VECTOR_MIN`, `VECTOR_MAX`, `VECTOR_AVG`

### **Helper functions**
- `AI_COUNT_TOKENS`, `TRY_COMPLETE`, `SPLIT_TEXT_RECURSIVE_CHARACTER`, `SPLIT_TEXT_MARKDOWN_HEADER`, `TO_FILE`, `PROMPT`

## 🚀 Key Learning Objectives

- **Apply AI functions** — know each function's purpose, signature, key parameters, and when to reach for it; prefer `AI_*` naming and recognize legacy aliases.
- **Structured outputs** — force `AI_COMPLETE` to return schema-valid JSON with `response_format`.
- **Vectors** — pick the right distance metric (cosine vs L2 vs inner product vs L1) and use vector aggregates.
- **Use-case analysis** — choose managed LLM vs RAG vs text-to-SQL by data type; chunk, embed and rerank for Cortex Search; use Cortex Analyst VQR and custom instructions for structured data.
- **Multimodal** — process audio (`AI_TRANSCRIBE`) and images (`TO_FILE` + multimodal `AI_COMPLETE`).
- **Chat & pipelines** — build chat apps (Streamlit in Snowflake, Snowflake Intelligence), maintain multi-turn memory via the messages array, and embed Cortex functions in SQL pipelines.
- **Third-party models** — deploy with Snowpark Container Services and log/call via the Model Registry.
- **Performance & cost** — choose a model for latency/accuracy/capability; use fine-tuning to reduce hallucinations; reserve **Provisioned Throughput** for steady, high-volume workloads.

## 🔍 Common Exam Pitfalls

1. **Old vs new names** — expecting `CORTEX.CHAT`/`CORTEX.GENERATE` (chat is now handled via the `messages`/`response_format` args of `AI_COMPLETE` and the Cortex Agent/REST APIs; there is no `GENERATE`).
2. **Distance metric choice** — using L2 when embeddings are normalized (cosine or inner product is usually correct).
3. **Structured output** — forgetting that `response_format` (JSON schema) is what guarantees parseable output, not prompt wording alone.
4. **Chunking** — chunks too large for the embedding model's context or too small to be meaningful.
5. **Memory** — assuming the model remembers turns; you must resend the `messages` array yourself.
6. **Provisioned Throughput** — confusing it (reserved capacity for latency/scale) with cost savings on small workloads.

## 📊 Study Resources

- [2.1 AISQL Function Catalog](./2.1_Cortex_LLM_Functions.md)
- [2.2 AI_COMPLETE Deep Dive](./2.2_Cortex_LLM_Complete_Functions.md)
- [2.3 Vector & Helper Functions](./2.3_Vector_and_Helper_Functions.md)
- [2.4 Data Analysis by Use Case](./2.4_Data_Analysis_By_Use_Case.md)
- [2.5 Chat Interfaces, Pipelines & Third-Party Models](./2.5_Chat_Interfaces_and_Pipelines.md)
- [Practice Questions](../exam_prep/Practice_Questions.md)
- [Exam Strategy Guide](../exam_prep/Exam_Strategy.md)

---

**Next Steps:** After completing this domain, proceed to [Domain 3: Snowflake Gen AI Governance](../3_Snowflake_Gen_AI_Governance/README.md).

***
[< Domain 1](../1_Snowflake_for_Gen_AI_Overview/README.md) | **📘 Domain 2: Snowflake Gen AI Functions** | [Domain 3 >](../3_Snowflake_Gen_AI_Governance/README.md)
