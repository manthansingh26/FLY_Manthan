# FL-01 — AI Workflow Audit and Tool Setup

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 1)  
**Code:** FL-01  

---

## 1. Weekly Task Classification (Ethan Mollick Framework)

Below is an audit of 12 recurring tasks from my real weekly workflow across Machine Learning engineering, research, and technical project management.

| Task Description | Category | One-Line Rationale |
|---|---|---|
| **1. Exploratory Data Analysis & Feature Engineering** | Collaborate with AI | AI suggests candidate statistical features; human validates leakage boundaries and domain relevance. |
| **2. Technical Report & Model Documentation** | Delegate with review | AI drafts report outline and summaries from raw JSON receipts; human edits for tone, safety, and precision. |
| **3. Writing Unit Tests & Validation Assertions** | Collaborate with AI | AI generates edge-case test suites; human executes and verifies assertions against real data shapes. |
| **4. High-Stakes Client Communications & Email Drafts** | Just me | Requires deep personal rapport, confidential context, and strategic relationship management. |
| **5. Data Ingestion & Schema Normalization Scripts** | Fully Automate | Deterministic Python and DuckDB scripts handle repetitive data cleaning without human intervention. |
| **6. Academic Paper & Literature Summarization** | Delegate with review | AI extracts core methodology and claims; human verifies key proofs and experimental limitations. |
| **7. System Architecture & Trade-Off Decisions** | Just me | High-stakes architectural choices require human accountability, security compliance, and long-term vision. |
| **8. Stack Trace & Python Exception Debugging** | Collaborate with AI | AI isolates potential exception causes; human tests and applies fixes in the local environment. |
| **9. Markdown Table & CSV Output Formatting** | Fully Automate | Automated scripts format summary statistics directly into Markdown/HTML tables. |
| **10. Daily Standup Summary Generation** | Delegate with review | AI aggregates git commit logs into bullet points; human verifies accuracy before posting. |
| **11. Personal Branding & Career Strategy** | Just me | Core professional identity, personal values, and career directional choices cannot be outsourced. |
| **12. Matplotlib & SVG Chart Customization** | Collaborate with AI | AI drafts styling and axis configurations; human fine-tunes visual polish and readability. |

---

## 2. Tool Setup & Claude Project Configuration

* **Tool Accounts Configured:** Claude (Anthropic), ChatGPT (OpenAI), Gemini (Google), and Perplexity.
* **Anthropic Academy Status:** Enrolled in *AI Fluency: Framework & Foundations*.

### Claude Project Configuration
* **Project Name:** `FlyRank-Applied-ML-Portfolio`
* **Custom Instructions:**
  > "You are an expert AI & ML Engineering Tutor. Act as a critical thinking partner for a Senior Machine Learning Engineer building applied search intelligence pipelines. Emphasize honest validation (grouped splits, zero target leakage), public-safe decision-support language (observed, measured, directional), and concise, evidence-backed explanations. Never generate unverified claims."

---

## 3. Three Target Tasks for Assignments FL-02 to FL-04

1. **Target Task 1: Content Decay Opportunity Scoring Pipeline**
   * *Definition of Done Well:* Achieves Precision@50 $\ge 0.5400$ on unseen client-holdout splits (`GroupKFold`), zero forbidden leakage columns in feature matrix, and reproducible execution.
2. **Target Task 2: Automated Model Report & Artifact Generation**
   * *Definition of Done Well:* Exports self-contained HTML/Markdown reports with responsive charts (`action_mix.png`) and metrics receipts (`action_playbook_metrics.json`).
3. **Target Task 3: Technical Storytelling & Research Paper Presentation**
   * *Definition of Done Well:* Deploys a live 9-section research paper on GitHub Pages (`https://manthansingh26.github.io/FLY_Manthan/`) with safe claim language, a 5-minute showcase outline, and data credit to FlyRank.ai.
