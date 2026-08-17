[< Domain 2](../2_Snowflake_Gen_AI_and_LLM_Functions/README.md) | **📘 Domain 3: Snowflake Gen AI Governance** | [Domain 4 >](../4_Snowflake_Document_AI/README.md)
***

# Domain 3: Snowflake Gen AI Governance

This domain covers how to **govern, secure, and control the cost** of generative AI workloads inside Snowflake. On the **SnowPro Specialty: Gen AI (C02)** exam (last updated April 30, 2026) this is the **highest-weighted domain at 29%** of scored questions (up from 22%).

Unlike generic "AI ethics" frameworks, C02 governance is **concrete and Snowflake-specific**: model allowlists, RBAC database roles, ACCOUNT_USAGE views, object tagging, guardrails, and AI observability built on TruLens. Master the exact object names and the SQL that grants, revokes, monitors, and evaluates AI services.

## 🎯 Domain Overview

Governance in Snowflake Cortex is enforced through the same primitives you already use for data: **Role-Based Access Control (RBAC)**, **account parameters**, **ACCOUNT_USAGE views**, and **object tagging** — plus AI-specific controls such as **Cortex Guard**, **AI_REDACT**, **cross-region inference settings**, and **AI Observability**. This domain teaches you to decide *which models* can run, *who* can call each Cortex service, *how much* it costs, and *how well* the application performs.

## 📚 Table of Contents

### **Objective Topics**
- [3.1 Model Access Controls](./3.1_Model_Access_Controls.md) — allowlists, application roles, RBAC, cross-region inference, Cortex Guard, AI_REDACT, reducing hallucinations & bias, REST API authentication
- [3.2 RBAC Roles & Privileges](./3.2_RBAC_Roles_and_Privileges.md) — GRANT/REVOKE database roles and privileges; `CORTEX_USER`, `CORTEX_ANALYST_USER`, `CORTEX_AGENT_USER`, `CORTEX_EMBED_USER`; per-service requirements
- [3.3 Cost Management](./3.3_Cost_Management.md) — per-service cost drivers, ACCOUNT_USAGE usage-history views, usage quotas, object tagging
- [3.4 AI Observability](./3.4_AI_Observability.md) — evaluation metrics, comparisons, tracing, logging, event tables, TruLens SDK, RAG Triad

## 🚀 Key Learning Objectives (C02 Domain 3.0)

### **3.1 Set up model access controls**
- Restrict which models can be used via the account-level allowlist parameter `CORTEX_MODELS_ALLOWLIST`
- Restrict access to specific models via **application roles** and **RBAC**
- Configure data safety and security: **cross-region inference**, **Guardrails / Cortex Guard**, sensitive-data handling with **AI_REDACT**
- Apply methods to reduce model **hallucinations and bias** (grounding/RAG, verified queries, fine-tuning, lower temperature)
- Choose the correct **REST API authentication** method (key-pair JWT, OAuth, PAT)

### **3.2 Grant and revoke RBAC and privileges**
- Grant/revoke the Cortex **database roles**: `SNOWFLAKE.CORTEX_USER`, `SNOWFLAKE.CORTEX_ANALYST_USER`, `SNOWFLAKE.CORTEX_AGENT_USER`, `SNOWFLAKE.CORTEX_EMBED_USER`
- Know the **specific privilege requirements** for Cortex Analyst, Cortex Search, Cortex Agents, and Snowflake Intelligence
- Grant/revoke privileges on **application roles** and limit access to specific roles

### **3.3 Manage, monitor, and optimize Cortex costs**
- Identify **cost drivers per service** (Agents, Search, Analyst, AI functions, Snowpark Container Services)
- Track consumption with **ACCOUNT_USAGE** views and **usage quotas**
- Use **object tagging** to attribute AI-service costs

### **3.4 Use Snowflake AI observability tools**
- Capture **evaluation metrics, comparisons, tracing, and logging** into **event tables**
- Instrument and evaluate AI apps with the **TruLens SDK**
- Apply **LLM-as-a-Judge** and the **RAG Triad** (context relevance, groundedness, answer relevance)

## 📋 Exam Focus Areas

### **High Priority**
1. `CORTEX_MODELS_ALLOWLIST` and cross-region inference parameters
2. The four Cortex **database roles** and their GRANT syntax
3. `METERING_DAILY_HISTORY` with `SERVICE_TYPE = 'AI_SERVICES'` for daily AI credit usage
4. Cortex Guard and AI_REDACT for safe/sensitive-data handling
5. TruLens-based AI Observability and the RAG Triad metrics

### **Medium Priority**
1. REST API authentication methods (key-pair JWT, OAuth, PAT)
2. Object tagging to attribute Cortex costs
3. Per-service cost types and the matching usage-history views

## 🔍 Common Exam Pitfalls

1. Confusing **account allowlist** (`CORTEX_MODELS_ALLOWLIST`) with **RBAC** — the allowlist governs *which models exist*; RBAC governs *who may call Cortex*.
2. Forgetting that Cortex functions require the **`SNOWFLAKE.CORTEX_USER`** database role, which is granted to `PUBLIC` by default but can be revoked.
3. Picking `METERING_HISTORY` (hourly, all services) when the daily AI-services view `METERING_DAILY_HISTORY` (filter `SERVICE_TYPE = 'AI_SERVICES'`) is the correct answer.
4. Assuming cross-region inference is on by default — it is **disabled** until `CORTEX_ENABLED_CROSS_REGION` is set.
5. Treating "reduce hallucinations" as a model setting only — grounding (RAG), verified queries, and lower temperature are the exam-expected answers.

## 📈 Success Metrics

To master this domain, you should be able to:
- ✅ Restrict usable models with an account allowlist and scope model access with RBAC
- ✅ Grant and revoke the correct Cortex database role for each service
- ✅ Monitor and attribute AI-service credit consumption with ACCOUNT_USAGE views and tags
- ✅ Apply Cortex Guard and AI_REDACT for safe and privacy-preserving inference
- ✅ Instrument an AI app with TruLens and evaluate it with the RAG Triad

---

**Next Steps:** Start with [3.1 Model Access Controls](./3.1_Model_Access_Controls.md), then continue through 3.2–3.4. After this domain, proceed to [Domain 4: Snowflake Document AI](../4_Snowflake_Document_AI/README.md).

***
[< Domain 2](../2_Snowflake_Gen_AI_and_LLM_Functions/README.md) | **📘 Domain 3: Snowflake Gen AI Governance** | [Domain 4 >](../4_Snowflake_Document_AI/README.md)
