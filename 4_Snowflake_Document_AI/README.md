[< Domain 3](../3_Snowflake_Gen_AI_Governance/README.md) | **📘 Domain 4: Snowflake Document Processing** | [Scenarios >](../scenarios/01_Building_RAG_Applications.md)
***

# Domain 4: Snowflake Document Processing

This domain focuses on Snowflake's document processing capabilities for parsing, extracting, and operationalizing content from unstructured documents using Cortex AI. It accounts for **15%** of the exam questions (SnowPro Specialty: Gen AI **C02**, last updated April 30, 2026) and covers the `AI_PARSE_DOCUMENT` and `AI_EXTRACT` functions, document preparation, automated pipelines, and troubleshooting/optimization.

> **C02 rename note:** In the C02 revision this domain was renamed from *"Snowflake Document AI"* to **"Snowflake Document Processing"**, and its weighting increased from 12% to **15%**. The modern surface is built on the Cortex AISQL functions **`AI_PARSE_DOCUMENT`** and **`AI_EXTRACT`** — not the legacy per-task functions.

## 🎯 Domain Overview

Snowflake Document Processing lets you turn PDFs, images, and Office documents staged in Snowflake into text, structured markdown, and typed fields — entirely in SQL. Cortex reads files directly from internal or external stages, so parsing and extraction run next to your data with no external service. You then wire these functions into automated **Streams + Tasks** pipelines, monitor and troubleshoot them, and optionally **fine-tune arctic-extract** models for higher-accuracy extraction.

## 📚 Table of Contents

### **Core Topics**
- [4.1 Document Parsing & Extraction Functions](./4.1_Document_AI_Overview.md) — `AI_PARSE_DOCUMENT` (OCR vs LAYOUT mode, `page_split`, `page_limit`) and `AI_EXTRACT` (response format, prompt engineering)
- [4.2 Document Pipelines & Optimization](./4.2_Document_Pipelines_and_Optimization.md) — preparing documents, automated Streams + Tasks pipelines, troubleshooting, cost, and fine-tuning arctic-extract

## 🚀 Key Learning Objectives (C02 Objectives 4.1–4.4)

### **4.1 — Use document parsing functions**
- Use **`AI_PARSE_DOCUMENT`** to convert documents to text or structured markdown
  - **OCR mode** — raw text extraction, best for simple/scanned text where structure does not matter
  - **LAYOUT mode** — preserves tables, headings, and reading order as **markdown**
  - **`page_split`** — return per-page output as an array of page objects
  - **`page_limit`** — cap the number of pages processed
- Use **`AI_EXTRACT`** to pull structured fields out of documents
  - Define a **response format / schema** (fields or questions to answer)
  - Apply **prompt engineering** to phrase questions clearly and constrain outputs

### **4.2 — Prepare and manage documents; implement extracting workflows**
- Upload documents to an **internal or external stage** (with `SERVER_SIDE_ENCRYPTION` for internal stages)
- Know the **requirements**: supported formats (PDF, DOCX, PPTX, images: JPEG/PNG/TIFF, etc.) and **size / page limits**

### **4.3 — Build automated document processing pipelines with Cortex AI**
- Orchestrate Snowflake-native tooling: a **Stream** on a directory table to detect newly staged files, and a **Task** to run `AI_PARSE_DOCUMENT` / `AI_EXTRACT` on the new rows

### **4.4 — Troubleshoot and optimize document processing**
- Diagnose extracting query errors; generate access URLs with **`GET_PRESIGNED_URL`** and **`BUILD_SCOPED_FILE_URL`**
- Understand **requirements and privileges** (stage access, `SNOWFLAKE.CORTEX_USER` role, directory tables)
- Manage **cost and best practices** (page limits, warehouse sizing, batching, incremental processing)
- **Fine-tune arctic-extract** models to improve extraction accuracy on domain-specific documents

## 📋 Exam Focus Areas

### **High Priority**
1. **`AI_PARSE_DOCUMENT` OCR vs LAYOUT** — when to use each; LAYOUT returns markdown that preserves tables/structure
2. **`AI_EXTRACT` with a schema** — extracting typed fields (vendor, total, line items) from invoices/forms
3. **`page_split` / `page_limit`** — controlling per-page output and processed page counts
4. **Streams + Tasks pipelines** — automated, incremental document processing

### **Medium Priority**
1. **Stage preparation & requirements** — formats, size/page limits, directory tables, encryption
2. **Troubleshooting file access** — `GET_PRESIGNED_URL` vs `BUILD_SCOPED_FILE_URL`
3. **Prompt engineering for `AI_EXTRACT`** — clear questions, constrained response format
4. **Cost optimization** — page limits, batching, right-sizing warehouses

### **Lower Priority**
1. **Fine-tuning arctic-extract models** for specialized document types
2. **Privileges & governance** for Cortex document functions

## ✅ Sample-Question Patterns (memorize these mappings)

- **"Extract structured fields (vendor, total, line items) from invoices"** → use **`AI_EXTRACT`** with a **schema / response format**.
- **"Preserve the structure of contracts as searchable markdown"** → use **`AI_PARSE_DOCUMENT`** in **LAYOUT mode**.
- **"Raw text from a scanned document, structure doesn't matter"** → use **`AI_PARSE_DOCUMENT`** in **OCR mode**.
- **"Process only the first N pages / return page-by-page output"** → use **`page_limit`** / **`page_split`**.
- **"Automatically process files as they land in a stage"** → **Stream** on the directory table + **Task**.
- **"File-not-found / access errors when reading a staged file"** → check stage privileges and use **`GET_PRESIGNED_URL`** or **`BUILD_SCOPED_FILE_URL`**.
- **"Improve extraction accuracy on our specific document type"** → **fine-tune an arctic-extract model**.

## 🔍 Common Exam Pitfalls

1. **Legacy function names** — there is **no** `DOCUMENT_AI.CLASSIFY()`, `.OCR()`, or `.EXTRACT_TABLES()`; the C02 surface is `AI_PARSE_DOCUMENT` and `AI_EXTRACT`.
2. **OCR vs LAYOUT confusion** — LAYOUT (not OCR) is the mode that returns markdown preserving tables and structure.
3. **Parsing vs extracting** — `AI_PARSE_DOCUMENT` produces text/markdown; `AI_EXTRACT` produces typed fields from a schema.
4. **Presigned vs scoped URLs** — `GET_PRESIGNED_URL` yields a temporary public URL; `BUILD_SCOPED_FILE_URL` yields a scoped, permission-checked URL.
5. **Missing directory table** — Streams-based pipelines require `DIRECTORY = (ENABLE = TRUE)` on the stage.
6. **Ignoring page/size limits** — oversized or too-many-page files fail or inflate cost; use `page_limit`.

## 📈 Success Metrics

To master this domain, you should be able to:
- ✅ Choose OCR vs LAYOUT mode for `AI_PARSE_DOCUMENT` and control `page_split` / `page_limit`
- ✅ Write an `AI_EXTRACT` call with a schema and well-engineered prompts to pull structured fields
- ✅ Stage documents correctly and know the format/size requirements
- ✅ Build an automated Streams + Tasks document pipeline
- ✅ Troubleshoot file-access errors with `GET_PRESIGNED_URL` / `BUILD_SCOPED_FILE_URL`
- ✅ Apply cost best practices and fine-tune arctic-extract models

## 📊 Study Resources

- [Practice Questions](../exam_prep/Practice_Questions.md) — Domain-specific practice questions
- [Exam Strategy Guide](../exam_prep/Exam_Strategy.md) — Test-taking strategies and tips

---

**Next Steps:** This is the final domain. Continue to the applied [Practice Scenarios](../scenarios/01_Building_RAG_Applications.md) and the [Practice Questions](../exam_prep/Practice_Questions.md) to prepare for the exam.

***
[< Domain 3](../3_Snowflake_Gen_AI_Governance/README.md) | **📘 Domain 4: Snowflake Document Processing** | [Scenarios >](../scenarios/01_Building_RAG_Applications.md)
