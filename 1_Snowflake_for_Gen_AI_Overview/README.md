[< Home](../README.md) | **📘 Domain 1: Snowflake for Gen AI Overview** | [Domain 2 >](../2_Snowflake_Gen_AI_and_LLM_Functions/README.md)
***

# Domain 1: Snowflake for Gen AI Overview

This domain provides the foundational understanding of Snowflake's Gen AI principles, features, and capabilities. On the **SnowPro Specialty: Gen AI (C02)** exam it accounts for **18%** of the questions.

## 🎯 Domain Overview

Domain 1 introduces the breadth of Snowflake's Gen AI stack: Snowflake Cortex (models, functions, Search, Analyst, Agents, Fine-tuning), Cortex Code, Snowflake Copilot, Snowflake Intelligence, the interfaces used to reach these features (AI Studio, SQL, REST API, MCP), cross-region inference, and the paths for bringing your own models into Snowflake (Model Registry and Snowpark Container Services).

## 📋 Official C02 Objectives Covered

### 1.1 Define Snowflake's Gen AI principles and features
- **Snowflake Cortex** — Cortex Models & Functions, Cortex Fine-tuning [PuPr], Cortex Search (RAG and unstructured-data use cases), Cortex Analyst (text-to-SQL), Cortex Agents
- **Snowflake Cortex Code** — Cortex Code in the Snowsight UI, Cortex Code CLI
- **Snowflake Copilot Inline** [PuPr]
- **Snowflake Intelligence**
- **Different interfaces** — AI Studio, SQL, REST API
- **Bringing your own models** — Snowflake Model Registry (custom model), Snowpark Container Services

### 1.2 Outline Gen AI capabilities in Snowflake
- **Prompting** and **Cortex AI functions** (vector embeddings, context windows)
- **Cortex Search** — multi-index queries, access-control requirements, different ways to use Cortex Search
- **Cortex Analyst** — Semantic Views, Semantic Views Autopilot, YAML specification, Verified Query, Custom Instructions
- **Cortex Agents** and **Snowflake Intelligence**
- **Cross-region inference** — `CORTEX_ENABLED_CROSS_REGION` parameter and considerations (latency, availability)
- **REST APIs**, **Model Context Protocol (MCP)**
- **Snowflake Cortex Code** (Cortex Code CLI commands)
- **Cortex Knowledge Extensions (CKE)**

## 📚 Table of Contents

- [1.1 Snowflake Cortex Overview](./1.1_Snowflake_Cortex_Overview.md) — what Cortex is, model families, AI_* functions and the `SNOWFLAKE.CORTEX.*` namespace
- [1.2 Snowflake Cortex AI Features](./1.2_Snowflake_Cortex_AI_Features.md) — feature catalog and the interfaces (AI Studio, SQL, REST API, MCP)
- [1.3 Vector Data Types & Operations](./1.3_Vector_Data_Types_Operations.md) — the VECTOR type and embeddings (function catalog lives in Domain 2)
- [1.4 Cortex Search, Analyst & Semantic Views](./1.4_Cortex_Search_Analyst_Semantic_Views.md) — RAG search and text-to-SQL
- [1.5 Agents, Intelligence & Code](./1.5_Agents_Intelligence_and_Code.md) — Cortex Agents, Snowflake Intelligence, Cortex Code, Copilot, cross-region inference, CKE
- [1.6 Bringing Your Own Models](./1.6_Bringing_Your_Own_Models.md) — Model Registry, Snowpark Container Services, Cortex Fine-tuning

## 🚀 Key Learning Objectives

- Explain Snowflake's Gen AI principles: run AI next to governed data, no data movement, serverless access to hosted model families
- Distinguish the Cortex building blocks — Models & Functions, Search, Analyst, Agents — and when each applies
- Identify the interfaces for reaching Cortex: AI Studio, SQL, REST API, and MCP
- Describe how Cortex Analyst uses Semantic Views (YAML spec, Autopilot, Verified Queries, Custom Instructions) for text-to-SQL
- Explain Cortex Agents and Snowflake Intelligence as orchestration layers over Search + Analyst + tools
- Understand cross-region inference and the `CORTEX_ENABLED_CROSS_REGION` account parameter
- Describe how to bring your own / open-source models via the Model Registry and Snowpark Container Services, and fine-tune with Cortex Fine-tuning

## 🔍 Common Exam Pitfalls

1. **AI_* vs SNOWFLAKE.CORTEX.*** — the `AI_*` names are the current entry point; `SNOWFLAKE.CORTEX.*` is the underlying namespace (still valid).
2. **Search vs Analyst** — Cortex Search retrieves unstructured text (RAG); Cortex Analyst generates SQL over structured data via semantic models.
3. **Semantic Views vs Semantic Models (YAML)** — Analyst can be backed by a YAML semantic model file or by a native Semantic View object.
4. **Agents vs Intelligence** — Cortex Agents is the orchestration API; Snowflake Intelligence is the natural-language app experience built on agents.
5. **Cross-region inference** — off by default; you must set `CORTEX_ENABLED_CROSS_REGION`, and requests may leave the local region (latency/availability trade-offs).
6. **Model naming churn** — memorize model *families and providers*, not exact version strings, which change frequently.

## 📈 Success Metrics

To master this domain, you should be able to:
- ✅ Name the model families/providers Cortex hosts and the current function naming
- ✅ Match each Cortex feature (Search, Analyst, Agents, Code) to its use case
- ✅ Choose the right interface (AI Studio / SQL / REST / MCP) for a scenario
- ✅ Explain semantic views, verified queries, and custom instructions for text-to-SQL
- ✅ Configure cross-region inference and understand its trade-offs
- ✅ Describe bring-your-own-model paths (Model Registry, SPCS) and Cortex Fine-tuning

---

**Next Steps:** After completing this domain, proceed to [Domain 2: Snowflake Gen AI & LLM Functions](../2_Snowflake_Gen_AI_and_LLM_Functions/README.md) to dive deep into specific LLM and vector functions.

***
[< Home](../README.md) | **📘 Domain 1: Snowflake for Gen AI Overview** | [Domain 2 >](../2_Snowflake_Gen_AI_and_LLM_Functions/README.md)
