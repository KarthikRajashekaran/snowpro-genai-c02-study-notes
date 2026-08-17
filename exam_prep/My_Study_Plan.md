[< Study Plan](./Study_Plan.md) | **🗓️ My 3-Week Study Plan (Aug 17 – Sep 6, 2026)** | [Practice Questions >](./Practice_Questions.md)
***

# My SnowPro Gen AI (C02) Study Plan — Personal Tracker

**Start:** Monday, Aug 17, 2026 · **Finish:** Sunday, Sep 6, 2026 · **Target exam:** Mon Sep 7 / Tue Sep 8
**Pace:** Steady — ~1–1.5 hrs on weekdays, ~3 hrs on weekend days (Sat/Sun).

> Tick each box as you finish. If a day slips, don't reshuffle everything — just carry that one item to the next day and keep the weekend anchors. Weekdays = *read + understand*; weekends = *hands-on + review*.

## 📌 Before you start (do today, ~15 min)
- [ ] Create/confirm a **Snowflake trial account** with Cortex enabled (a region where Cortex is available).
- [ ] Grant yourself `SNOWFLAKE.CORTEX_USER` so you can run `AI_*` functions.
- [ ] Bookmark the repo [Home](../README.md) and the [Exam Strategy](./Exam_Strategy.md).

---

## Week 1 — Domain 1: Gen AI Overview (18%)
*Goal: understand the whole Cortex surface and how the pieces compose.*

| ✔ | Date | Focus | Chapter | Est. |
|---|------|-------|---------|------|
| [ ] | **Mon Aug 17** | Kickoff + trial setup, then read Cortex overview | [1.1 Cortex Overview](../1_Snowflake_for_Gen_AI_Overview/1.1_Snowflake_Cortex_Overview.md) | 1.5h |
| [ ] | **Tue Aug 18** | Interfaces: AI Studio, SQL, REST API, MCP | [1.2 Cortex AI Features & Interfaces](../1_Snowflake_for_Gen_AI_Overview/1.2_Snowflake_Cortex_AI_Features.md) | 1h |
| [ ] | **Wed Aug 19** | Vector data type basics | [1.3 Vector Data Types](../1_Snowflake_for_Gen_AI_Overview/1.3_Vector_Data_Types_Operations.md) | 1h |
| [ ] | **Thu Aug 20** | Search / Analyst / Semantic Views (big one) | [1.4 Search, Analyst & Semantic Views](../1_Snowflake_for_Gen_AI_Overview/1.4_Cortex_Search_Analyst_Semantic_Views.md) | 1.5h |
| [ ] | **Fri Aug 21** | Agents, Snowflake Intelligence, Cortex Code | [1.5 Agents, Intelligence & Code](../1_Snowflake_for_Gen_AI_Overview/1.5_Agents_Intelligence_and_Code.md) | 1h |
| [ ] | **Sat Aug 22** | BYO models + **hands-on**: run `AI_COMPLETE`; build a mini Cortex Search service | [1.6 Bringing Your Own Models](../1_Snowflake_for_Gen_AI_Overview/1.6_Bringing_Your_Own_Models.md) | 3h |
| [ ] | **Sun Aug 23** | Domain 1 review + Domain 1 practice Qs; open Cortex Analyst on a semantic view | [Practice Questions](./Practice_Questions.md) | 3h |

**Week 1 gate:** I can explain when to use Search vs Analyst vs Agents vs Snowflake Intelligence, and what a Semantic View is.

---

## Week 2 — Domain 2: Gen AI Functions (38%) — the big one
*Goal: pick and write the right `AI_*` function for any task, from memory.*

| ✔ | Date | Focus | Chapter | Est. |
|---|------|-------|---------|------|
| [ ] | **Mon Aug 24** | AISQL catalog — drill every `AI_*` function's purpose | [2.1 AI SQL Function Catalog](../2_Snowflake_Gen_AI_and_LLM_Functions/2.1_Cortex_LLM_Functions.md) | 1.5h |
| [ ] | **Tue Aug 25** | `AI_COMPLETE` + structured outputs (JSON schema), `TRY_COMPLETE` | [2.2 AI_COMPLETE & Structured Outputs](../2_Snowflake_Gen_AI_and_LLM_Functions/2.2_Cortex_LLM_Complete_Functions.md) | 1h |
| [ ] | **Wed Aug 26** | `VECTOR_*` metrics + helpers (`SPLIT_TEXT_*`, `AI_COUNT_TOKENS`, `TO_FILE`, `PROMPT`) | [2.3 Vector & Helper Functions](../2_Snowflake_Gen_AI_and_LLM_Functions/2.3_Vector_and_Helper_Functions.md) | 1h |
| [ ] | **Thu Aug 27** | Use-case analysis: unstructured / structured / multimodal | [2.4 Data Analysis by Use Case](../2_Snowflake_Gen_AI_and_LLM_Functions/2.4_Data_Analysis_By_Use_Case.md) | 1.5h |
| [ ] | **Fri Aug 28** | Chat interfaces (Streamlit, multi-turn memory), pipelines, 3rd-party models | [2.5 Chat Interfaces & Pipelines](../2_Snowflake_Gen_AI_and_LLM_Functions/2.5_Chat_Interfaces_and_Pipelines.md) | 1h |
| [ ] | **Sat Aug 29** | **Hands-on**: run *every* `AI_*` function once; build a structured-output extraction; a Streamlit multi-turn chat | — | 3h |
| [ ] | **Sun Aug 30** | Domain 2 review + Domain 2 practice Qs; re-drill weak functions | [Practice Questions](./Practice_Questions.md) | 3h |

**Week 2 gate:** Given a described task (classify vs extract vs filter vs agg vs redact…), I instantly name the right function and its key parameters.

---

## Week 3 — Domains 3 & 4 + Final Review (29% + 15%)
*Goal: lock in governance (heavily weighted!) and document processing, then rehearse.*

| ✔ | Date | Focus | Chapter | Est. |
|---|------|-------|---------|------|
| [ ] | **Mon Aug 31** | Model access controls + RBAC roles/privileges | [3.1 Model Access Controls](../3_Snowflake_Gen_AI_Governance/3.1_Model_Access_Controls.md) · [3.2 RBAC Roles](../3_Snowflake_Gen_AI_Governance/3.2_RBAC_Roles_and_Privileges.md) | 1.5h |
| [ ] | **Tue Sep 1** | Cost management: usage-history views, object tagging | [3.3 Cost Management](../3_Snowflake_Gen_AI_Governance/3.3_Cost_Management.md) | 1h |
| [ ] | **Wed Sep 2** | AI Observability: TruLens, RAG Triad, event tables | [3.4 AI Observability](../3_Snowflake_Gen_AI_Governance/3.4_AI_Observability.md) | 1h |
| [ ] | **Thu Sep 3** | Document parsing: `AI_PARSE_DOCUMENT` (OCR/LAYOUT), `AI_EXTRACT` | [4.1 Document Parsing Functions](../4_Snowflake_Document_AI/4.1_Document_AI_Overview.md) | 1.5h |
| [ ] | **Fri Sep 4** | Document pipelines (Streams/Tasks), troubleshooting, arctic-extract fine-tuning | [4.2 Document Pipelines & Optimization](../4_Snowflake_Document_AI/4.2_Document_Pipelines_and_Optimization.md) | 1h |
| [ ] | **Sat Sep 5** | Governance + Doc practice Qs; **Capstone**: end-to-end RAG (parse → chunk → embed → Cortex Search → `AI_COMPLETE`) | [Scenario: RAG](../scenarios/01_Building_RAG_Applications.md) | 3h |
| [ ] | **Sun Sep 6** | **Full mock**: official C02 samples + new-topic Qs + question bank; review every miss; read [Exam Strategy](./Exam_Strategy.md) | [Practice Questions](./Practice_Questions.md) | 3h |

**Week 3 gate:** I can answer any governance question (roles, allowlist, usage views, observability) from memory and choose OCR vs LAYOUT correctly.

---

## 🎯 Final readiness check (before booking/sitting the exam)
- [ ] Name the right `AI_*` function for any described task.
- [ ] Explain Search vs Analyst vs Agents vs Snowflake Intelligence.
- [ ] Choose OCR vs LAYOUT for `AI_PARSE_DOCUMENT` given a goal.
- [ ] List the four `CORTEX_*_USER` roles and what each unlocks.
- [ ] Point to the right usage view (daily AI credits → `METERING_DAILY_HISTORY`, `SERVICE_TYPE='AI_SERVICES'`).
- [ ] Describe how TruLens evaluates RAG (context relevance, groundedness, answer relevance).
- [ ] Scored **80%+** on the full practice set, with **≥75% in each domain**.

## 🔁 Daily habits
- Start each session by re-reading the previous day's **Study Questions** (2 min recall).
- Keep a running "missed it" list; those become your Sep 6 review.
- Every function you read about, **run once** in the trial account the same week.

## 🗓️ Exam day (Mon Sep 7 / Tue Sep 8)
- Light review only (this file's gates + the [cheat sheet](./Exam_Strategy.md)). No new material.
- 65 questions / 115 min → ~1.75 min each; flag-and-return on anything not obvious in 30s.

***
[< Study Plan](./Study_Plan.md) | **🗓️ My 3-Week Study Plan (Aug 17 – Sep 6, 2026)** | [Practice Questions >](./Practice_Questions.md)
