**📘 Snowflake SnowPro Specialty: Gen AI Study Notes** | [Domain 1 >](./1_Snowflake_for_Gen_AI_Overview/README.md)
***

# Snowflake SnowPro Specialty: Generative AI Study Notes

Comprehensive study notes for the **Snowflake SnowPro Specialty: Generative AI** certification exam, **aligned to the C02 exam study guide (last updated April 30, 2026)**.

> ⚠️ **Updated for the C02 exam.** Snowflake refreshed this exam in 2026: domain weightings shifted, Domain 4 was renamed to **Snowflake Document Processing**, and the function surface moved to the **`AI_*` family** (AI SQL / AISQL). New topics include **AI Observability (TruLens)**, **Cortex Agents**, **Snowflake Intelligence**, **Cortex Code**, **Semantic Views**, **cross-region inference**, **MCP**, and **Cortex Knowledge Extensions**. These notes reflect that guide.

## 🎯 Exam Overview

| Item | Detail |
|------|--------|
| **Exam code** | SnowPro Specialty: Gen AI (**C02**) |
| **Format** | 65 questions, 115 minutes |
| **Question types** | Multiple choice, multiple select, scenario/interactive |
| **Passing score** | 750 / 1000 (scaled) |
| **Cost** | $225 USD |
| **Prerequisites** | None required; **SnowPro Core** knowledge assumed |
| **Validity** | 2 years (recertify via Continuing Education or a higher cert) |
| **Official study time** | 10–13 hours to work through Snowflake's guide (plan more for hands-on) |

**Target audience:** AI/ML Engineers, Data Scientists, Data Engineers, Data Application Developers, and Data Analysts with programming experience. Candidates typically have **1+ year of Gen AI experience on Snowflake** and can write Python and SQL.

## 📚 Domain Topics (C02 Exam Weighting)

| # | Domain | Weight | Notes |
|---|--------|:------:|-------|
| 1 | [Snowflake for Gen AI Overview](./1_Snowflake_for_Gen_AI_Overview/README.md) | **18%** | ↓ from 26% (C01) |
| 2 | [Snowflake Gen AI Functions](./2_Snowflake_Gen_AI_and_LLM_Functions/README.md) | **38%** | ↓ from 40% — still the biggest domain |
| 3 | [Snowflake Gen AI Governance](./3_Snowflake_Gen_AI_Governance/README.md) | **29%** | ↑ from 22% — biggest growth |
| 4 | [Snowflake Document Processing](./4_Snowflake_Document_AI/README.md) | **15%** | ↑ from 12%; renamed from "Document AI" |

## 🧭 What C02 Emphasizes (know this cold)

- **AI SQL functions (`AI_*`)** — `AI_COMPLETE`, `AI_CLASSIFY`, `AI_EXTRACT`, `AI_PARSE_DOCUMENT`, `AI_SENTIMENT`, `AI_SUMMARIZE_AGG`, `AI_TRANSLATE`, `AI_EMBED`, `AI_FILTER`, `AI_AGG`, `AI_SIMILARITY`, `AI_TRANSCRIBE`, `AI_REDACT`, plus helpers (`AI_COUNT_TOKENS`, `TRY_COMPLETE`, `SPLIT_TEXT_*`, `TO_FILE`, `PROMPT`).
- **`VECTOR_*` functions** — the full distance/aggregation catalog, not just cosine similarity.
- **Cortex Search / Cortex Analyst / Cortex Agents / Snowflake Intelligence** and how they compose.
- **Semantic Views** — Autopilot, YAML spec, Verified Query Repository, Custom Instructions.
- **Governance** — model allowlists, `CORTEX_*_USER` roles, usage-history views, object tagging, **Cortex Guard**, **AI_REDACT**, and **AI Observability with TruLens**.
- **Document Processing** — `AI_PARSE_DOCUMENT` (OCR vs LAYOUT, `page_split`, `page_limit`), `AI_EXTRACT`, Streams/Tasks pipelines, `GET_PRESIGNED_URL` / `BUILD_SCOPED_FILE_URL`, **arctic-extract fine-tuning**.

## 🚀 Quick Access

### Domain 1 — Overview & Architecture
- [1.1 Snowflake Cortex Overview](./1_Snowflake_for_Gen_AI_Overview/1.1_Snowflake_Cortex_Overview.md)
- [1.2 Cortex AI Features & Interfaces](./1_Snowflake_for_Gen_AI_Overview/1.2_Snowflake_Cortex_AI_Features.md)
- [1.3 Vector Data Types & Operations](./1_Snowflake_for_Gen_AI_Overview/1.3_Vector_Data_Types_Operations.md)
- [1.4 Cortex Search, Analyst & Semantic Views](./1_Snowflake_for_Gen_AI_Overview/1.4_Cortex_Search_Analyst_Semantic_Views.md)
- [1.5 Agents, Intelligence & Cortex Code](./1_Snowflake_for_Gen_AI_Overview/1.5_Agents_Intelligence_and_Code.md)
- [1.6 Bringing Your Own Models](./1_Snowflake_for_Gen_AI_Overview/1.6_Bringing_Your_Own_Models.md)

### Domain 2 — Gen AI Functions
- [2.1 AI SQL Function Catalog](./2_Snowflake_Gen_AI_and_LLM_Functions/2.1_Cortex_LLM_Functions.md)
- [2.2 AI_COMPLETE & Structured Outputs](./2_Snowflake_Gen_AI_and_LLM_Functions/2.2_Cortex_LLM_Complete_Functions.md)
- [2.3 Vector & Helper Functions](./2_Snowflake_Gen_AI_and_LLM_Functions/2.3_Vector_and_Helper_Functions.md)
- [2.4 Data Analysis by Use Case](./2_Snowflake_Gen_AI_and_LLM_Functions/2.4_Data_Analysis_By_Use_Case.md)
- [2.5 Chat Interfaces & Pipelines](./2_Snowflake_Gen_AI_and_LLM_Functions/2.5_Chat_Interfaces_and_Pipelines.md)

### Domain 3 — Governance
- [3.1 Model Access Controls](./3_Snowflake_Gen_AI_Governance/3.1_Model_Access_Controls.md)
- [3.2 RBAC Roles & Privileges](./3_Snowflake_Gen_AI_Governance/3.2_RBAC_Roles_and_Privileges.md)
- [3.3 Cost Management](./3_Snowflake_Gen_AI_Governance/3.3_Cost_Management.md)
- [3.4 AI Observability](./3_Snowflake_Gen_AI_Governance/3.4_AI_Observability.md)

### Domain 4 — Document Processing
- [4.1 Document Parsing Functions](./4_Snowflake_Document_AI/4.1_Document_AI_Overview.md)
- [4.2 Document Pipelines & Optimization](./4_Snowflake_Document_AI/4.2_Document_Pipelines_and_Optimization.md)

### Exam Preparation
- [📅 Study Plan](./exam_prep/Study_Plan.md)
- [Practice Questions by Domain](./exam_prep/Practice_Questions.md)
- [Exam Strategy Guide](./exam_prep/Exam_Strategy.md)
- [Scenario: Building RAG Applications](./scenarios/01_Building_RAG_Applications.md)

## 🗺️ How to Use This Guide

1. **Read the domain READMEs first** for scope and weighting.
2. **Follow the [Study Plan](./exam_prep/Study_Plan.md)** — it sequences the topics by weight and dependency.
3. **Do the SQL hands-on** — every function in Domain 2 and 4 should be run at least once in a trial account.
4. **Drill governance** — Domain 3 grew to 29%; know the roles, allowlist, usage views, and observability tools by name.
5. **Test yourself** with the [Practice Questions](./exam_prep/Practice_Questions.md), including the official C02 samples.

## 🔗 Additional Resources

- [SnowPro Specialty: Gen AI Certification page](https://learn.snowflake.com/en/certifications/snowpro-GenAI-C02/)
- [Snowflake Cortex AISQL Documentation](https://docs.snowflake.com/en/user-guide/snowflake-cortex/aisql)
- [Cortex Search](https://docs.snowflake.com/en/user-guide/snowflake-cortex/cortex-search/cortex-search-overview) · [Cortex Analyst](https://docs.snowflake.com/en/user-guide/snowflake-cortex/cortex-analyst) · [Cortex Agents](https://docs.snowflake.com/en/user-guide/snowflake-cortex/cortex-agents)
- [AI Observability (TruLens)](https://docs.snowflake.com/en/user-guide/snowflake-cortex/ai-observability/overview)
- [Snowflake Quickstarts](https://quickstarts.snowflake.com/)

---

**Note:** These are community study notes, not official Snowflake material. Snowflake evolves Cortex rapidly — always confirm exact syntax, model names, and regional availability against the current [Snowflake documentation](https://docs.snowflake.com/).

**Attribution:** This project began as a fork of [augustorosa/snowflake-snowpro-specialty-genai-study-notes](https://github.com/augustorosa/snowflake-snowpro-specialty-genai-study-notes) and has since been substantially rewritten and expanded to align with the **C02** exam revision. Distributed under the **Apache License 2.0** (see [`LICENSE`](./LICENSE)); the original author's copyright is retained.

***
**📘 Snowflake SnowPro Specialty: Gen AI Study Notes** | [Domain 1 >](./1_Snowflake_for_Gen_AI_Overview/README.md)
