[< Study Plan](./Study_Plan.md) | **🗓️ My 5-Week Study Plan (Aug 17 – Sep 20, 2026)** | [Practice Questions >](./Practice_Questions.md)
***

# My SnowPro Gen AI (C02) Study Plan — Personal Tracker

**Start:** Monday, Aug 17, 2026 · **Finish:** Sunday, Sep 20, 2026 · **Target exam:** Mon Sep 21 / Tue Sep 22
**Pace:** Relaxed — ~45–60 min on weekdays, ~2 hrs on weekend days (Sat/Sun). Built-in buffer/rest days and **two full mock exams** in the final week.

> Tick each box as you finish. If a day slips, use the buffer/rest days to catch up rather than reshuffling the whole plan. Weekdays = *read + understand*; weekends = *hands-on + review*.

## 📌 Before you start (do today, ~15 min)
- [ ] Create/confirm a **Snowflake trial account** with Cortex enabled (a region where Cortex is available).
- [ ] Grant yourself `SNOWFLAKE.CORTEX_USER` so you can run `AI_*` functions.
- [ ] Bookmark the repo [Home](../README.md) and the [Exam Strategy](./Exam_Strategy.md).

---

## Week 1 — Domain 1: Gen AI Overview (18%)
*Goal: understand the whole Cortex surface and how the pieces compose.*

| ✔ | Date | Focus | Chapter | Est. |
|---|------|-------|---------|------|
| [ ] | **Mon Aug 17** | Kickoff + trial setup, then read Cortex overview | [1.1 Cortex Overview](../1_Snowflake_for_Gen_AI_Overview/1.1_Snowflake_Cortex_Overview.md) | 1h |
| [ ] | **Tue Aug 18** | Interfaces: AI Studio, SQL, REST API, MCP | [1.2 Cortex AI Features & Interfaces](../1_Snowflake_for_Gen_AI_Overview/1.2_Snowflake_Cortex_AI_Features.md) | 45m |
| [ ] | **Wed Aug 19** | Vector data type basics | [1.3 Vector Data Types](../1_Snowflake_for_Gen_AI_Overview/1.3_Vector_Data_Types_Operations.md) | 45m |
| [ ] | **Thu Aug 20** | Search / Analyst / Semantic Views | [1.4 Search, Analyst & Semantic Views](../1_Snowflake_for_Gen_AI_Overview/1.4_Cortex_Search_Analyst_Semantic_Views.md) | 1h |
| [ ] | **Fri Aug 21** | Agents, Snowflake Intelligence, Cortex Code | [1.5 Agents, Intelligence & Code](../1_Snowflake_for_Gen_AI_Overview/1.5_Agents_Intelligence_and_Code.md) | 45m |
| [ ] | **Sat Aug 22** | BYO models + **hands-on**: run `AI_COMPLETE`; build a mini Cortex Search service | [1.6 Bringing Your Own Models](../1_Snowflake_for_Gen_AI_Overview/1.6_Bringing_Your_Own_Models.md) | 2h |
| [ ] | **Sun Aug 23** | Domain 1 review + Domain 1 practice Qs; open Cortex Analyst on a semantic view | [Practice Questions](./Practice_Questions.md) | 2h |

**Week 1 gate:** I can explain when to use Search vs Analyst vs Agents vs Snowflake Intelligence, and what a Semantic View is.

---

## Week 2 — Domain 2: Gen AI Functions, Part 1 (38%)
*Goal: master the `AI_*` catalog, `AI_COMPLETE`, and vector/helper functions.*

| ✔ | Date | Focus | Chapter | Est. |
|---|------|-------|---------|------|
| [ ] | **Mon Aug 24** | AISQL catalog — general + task-specific `AI_*` (part 1) | [2.1 AI SQL Function Catalog](../2_Snowflake_Gen_AI_and_LLM_Functions/2.1_Cortex_LLM_Functions.md) | 1h |
| [ ] | **Tue Aug 25** | AISQL catalog — finish + drill "which function for which task" | [2.1 (revisit)](../2_Snowflake_Gen_AI_and_LLM_Functions/2.1_Cortex_LLM_Functions.md) | 45m |
| [ ] | **Wed Aug 26** | `AI_COMPLETE` + structured outputs (JSON schema), `TRY_COMPLETE` | [2.2 AI_COMPLETE & Structured Outputs](../2_Snowflake_Gen_AI_and_LLM_Functions/2.2_Cortex_LLM_Complete_Functions.md) | 1h |
| [ ] | **Thu Aug 27** | `VECTOR_*` metrics + helpers (`SPLIT_TEXT_*`, `AI_COUNT_TOKENS`, `TO_FILE`, `PROMPT`) | [2.3 Vector & Helper Functions](../2_Snowflake_Gen_AI_and_LLM_Functions/2.3_Vector_and_Helper_Functions.md) | 1h |
| [ ] | **Fri Aug 28** | 🟡 Buffer / light review — catch up on anything unfinished | — | 30m |
| [ ] | **Sat Aug 29** | **Hands-on**: run *every* `AI_*` function once; build a structured-output extraction | — | 2h |
| [ ] | **Sun Aug 30** | Review 2.1–2.3 + Domain 2 practice Qs (part 1) | [Practice Questions](./Practice_Questions.md) | 2h |

**Week 2 gate:** Given a described task (classify vs extract vs filter vs agg vs redact…), I name the right function and its key parameters, and I can pick the right vector metric.

---

## Week 3 — Domain 2 Part 2 + Domain 3 start (38% → 29%)
*Goal: finish functions (use-cases, chat/pipelines) and open governance.*

| ✔ | Date | Focus | Chapter | Est. |
|---|------|-------|---------|------|
| [ ] | **Mon Aug 31** | Use-case analysis: unstructured / structured / multimodal | [2.4 Data Analysis by Use Case](../2_Snowflake_Gen_AI_and_LLM_Functions/2.4_Data_Analysis_By_Use_Case.md) | 1h |
| [ ] | **Tue Sep 1** | Chat interfaces (Streamlit, multi-turn memory), pipelines, 3rd-party models | [2.5 Chat Interfaces & Pipelines](../2_Snowflake_Gen_AI_and_LLM_Functions/2.5_Chat_Interfaces_and_Pipelines.md) | 1h |
| [ ] | **Wed Sep 2** | Domain 2 full review + Domain 2 practice Qs (part 2) | [Practice Questions](./Practice_Questions.md) | 1h |
| [ ] | **Thu Sep 3** | Model access controls (allowlist, Cortex Guard, `AI_REDACT`) | [3.1 Model Access Controls](../3_Snowflake_Gen_AI_Governance/3.1_Model_Access_Controls.md) | 1h |
| [ ] | **Fri Sep 4** | RBAC roles & privileges (`CORTEX_*_USER`) | [3.2 RBAC Roles & Privileges](../3_Snowflake_Gen_AI_Governance/3.2_RBAC_Roles_and_Privileges.md) | 45m |
| [ ] | **Sat Sep 5** | **Hands-on**: Streamlit multi-turn chat + practice GRANT/REVOKE of Cortex roles | — | 2h |
| [ ] | **Sun Sep 6** | 🟢 Rest / light recall (re-read week's Study Questions) | — | 30m |

**Week 3 gate:** I can build a governed chat app and list the four `CORTEX_*_USER` roles and what each unlocks.

---

## Week 4 — Domain 3 finish + Domain 4 (29% + 15%)
*Goal: lock in cost/observability and document processing.*

| ✔ | Date | Focus | Chapter | Est. |
|---|------|-------|---------|------|
| [ ] | **Mon Sep 7** | Cost management: usage-history views, object tagging | [3.3 Cost Management](../3_Snowflake_Gen_AI_Governance/3.3_Cost_Management.md) | 1h |
| [ ] | **Tue Sep 8** | AI Observability: TruLens, RAG Triad, event tables | [3.4 AI Observability](../3_Snowflake_Gen_AI_Governance/3.4_AI_Observability.md) | 45m |
| [ ] | **Wed Sep 9** | Domain 3 review + Domain 3 practice Qs (governance is 29% — don't skip) | [Practice Questions](./Practice_Questions.md) | 1h |
| [ ] | **Thu Sep 10** | Document parsing: `AI_PARSE_DOCUMENT` (OCR/LAYOUT), `AI_EXTRACT` | [4.1 Document Parsing Functions](../4_Snowflake_Document_AI/4.1_Document_AI_Overview.md) | 1h |
| [ ] | **Fri Sep 11** | Document pipelines (Streams/Tasks), troubleshooting, arctic-extract fine-tuning | [4.2 Document Pipelines & Optimization](../4_Snowflake_Document_AI/4.2_Document_Pipelines_and_Optimization.md) | 45m |
| [ ] | **Sat Sep 12** | **Hands-on**: parse a PDF both modes + `AI_EXTRACT` invoice fields + a Stream+Task pipeline | — | 2h |
| [ ] | **Sun Sep 13** | Domain 4 review + Domain 4 practice Qs | [Practice Questions](./Practice_Questions.md) | 2h |

**Week 4 gate:** I can choose OCR vs LAYOUT correctly and answer any governance question (roles, allowlist, usage views, observability) from memory.

---

## Week 5 — Integration, Mock Exams & Final Review
*Goal: tie the four domains together and rehearse under time.*

| ✔ | Date | Focus | Chapter | Est. |
|---|------|-------|---------|------|
| [ ] | **Mon Sep 14** | **Capstone**: end-to-end RAG (parse → chunk → embed → Cortex Search → `AI_COMPLETE`) | [Scenario: RAG](../scenarios/01_Building_RAG_Applications.md) | 2h |
| [ ] | **Tue Sep 15** | Cross-cutting themes review (RAG+governance, vectors+structured data, agentic/fine-tuning) | [Home §Key Emphasis Areas](../README.md) | 1h |
| [ ] | **Wed Sep 16** | **Full mock exam #1** — official samples + new-topic Qs + bank; mark every miss | [Practice Questions](./Practice_Questions.md) | 1.5h |
| [ ] | **Thu Sep 17** | Re-drill weakest domain (usually Governance 29% or Functions 38%) | (your miss list) | 1h |
| [ ] | **Fri Sep 18** | **Full mock exam #2** — timed, 65 Q / 115 min feel; review misses | [Practice Questions](./Practice_Questions.md) | 1.5h |
| [ ] | **Sat Sep 19** | Final gaps + read [Exam Strategy](./Exam_Strategy.md) + run the readiness checklist below | — | 2h |
| [ ] | **Sun Sep 20** | 🟢 Light review only + rest before exam day | — | 30m |

**Week 5 gate:** 80%+ on both mocks, ≥75% in each domain, and every readiness box below ticked.

---

## 🎯 Final readiness check (before booking/sitting the exam)
- [ ] Name the right `AI_*` function for any described task.
- [ ] Explain Search vs Analyst vs Agents vs Snowflake Intelligence.
- [ ] Choose OCR vs LAYOUT for `AI_PARSE_DOCUMENT` given a goal.
- [ ] List the four `CORTEX_*_USER` roles and what each unlocks.
- [ ] Point to the right usage view (daily AI credits → `METERING_DAILY_HISTORY`, `SERVICE_TYPE='AI_SERVICES'`).
- [ ] Describe how TruLens evaluates RAG (context relevance, groundedness, answer relevance).
- [ ] Explain the three cross-cutting themes: RAG + governance, vector search with structured data, model deployment & agentic workflows.
- [ ] Scored **80%+** on both mock exams, with **≥75% in each domain**.

## 🔁 Daily habits
- Start each session by re-reading the previous day's **Study Questions** (2 min recall).
- Keep a running "missed it" list; those become your Week 5 re-drill (Sep 17).
- Every function you read about, **run once** in the trial account the same week.

## 🗓️ Exam day (Mon Sep 21 / Tue Sep 22)
- Light review only (this file's gates + the [cheat sheet](./Exam_Strategy.md)). No new material.
- 65 questions / 115 min → ~1.75 min each; flag-and-return on anything not obvious in 30s.

***
[< Study Plan](./Study_Plan.md) | **🗓️ My 5-Week Study Plan (Aug 17 – Sep 20, 2026)** | [Practice Questions >](./Practice_Questions.md)
