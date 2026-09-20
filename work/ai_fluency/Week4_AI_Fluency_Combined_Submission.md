# General AI Fluency — Week 4 Deliverables

This document contains all four completed deliverables for Week 4 of General AI Fluency:
1. **Empty but Live:** Live Deployment Verification
2. **Three Roads:** Stack Selection & Rationale
3. **FL-04:** Ship an Automation Workflow v2
4. **FL-05:** Agent Concepts and MCP Basics

---

# Empty but Live: Ship a Blank Page

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 4)  

---

## 1. Live Deployment & Host Configuration

* **Live Public URL:** [https://manthansingh26.github.io/FLY_Manthan/](https://manthansingh26.github.io/FLY_Manthan/)
* **Hosting Platform:** GitHub Pages (Free tier, auto-deployed from `/docs` directory on `main` branch).
* **Repository:** [manthansingh26/FLY_Manthan](https://github.com/manthansingh26/FLY_Manthan)

---

## 2. Verification Protocol

* **Incognito Desktop Verification:** Confirmed `https://manthansingh26.github.io/FLY_Manthan/` loads cleanly in private browser sessions with zero authentication barriers.
* **Secondary Device (Mobile) Verification:** Verified responsive HTML grid rendering, legible typography (`Inter`), and high-contrast tables on iOS Safari and Android Chrome.

---

## 3. Project Knowledge Base Configuration

* **Claude Project Name:** `FlyRank-Applied-ML-Portfolio`
* **Loaded Artifacts:**
  * Identity Kit (`FL03_Identity_Kit.md`)
  * Case Study (`FL02_Frame_It_As_Cases.md`)
  * Content & CTA Map (`FL03_The_Through_Line_Content_Map.md`)
  * Live HTML Document (`docs/index.html`)


---

# Three Roads: Choose Your Stack with AI

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 4)  

---

## 1. Constraint Input Definition

1. **Cost Constraint:** 100% Free tier (Zero hosting or database maintenance costs).
2. **Skill Level:** Advanced Applied ML & Data Engineering (Comfortable with HTML/CSS, Python pipelines, static site hosting).
3. **Portfolio Functionality:** Display long-form scientific paper, interactive SVG/PNG charts, benchmark tables, and code receipts.
4. **Dynamic Needs:** No server-side database required yet; static HTML with embedded JSON metrics receipts satisfies all user needs.

---

## 2. Comparison of Three Stack Options

| Option | Technology Stack | Hosting & Backend | Trade-offs & Maintenance |
|---|---|---|---|
| **Road 1 (Simplest)** | **Vanilla HTML5 + CSS3 + GitHub Pages** | GitHub Pages (`/docs` folder), No Backend | **Pros:** Zero build tools, instantaneous load times, 100% free, 0% maintenance. <br>**Cons:** Manual HTML structure formatting. |
| **Road 2 (Moderate)** | **Hugo / Astro Static Site Generator** | Netlify / Vercel Free Tier, Markdown Content | **Pros:** Templating engine, component reuse. <br>**Cons:** Requires npm/build step configuration and package updates. |
| **Road 3 (Powerful)** | **Next.js 14 + Tailwind CSS + Vercel** | Vercel Free Tier + Serverless API Routes | **Pros:** Full dynamic React rendering, serverless endpoints. <br>**Cons:** High maintenance overhead, potential cold starts, unnecessary for static paper receipts. |

---

## 3. Chosen Stack Rationale

> **Selected Stack:** **Road 1 — Vanilla HTML5 + CSS3 hosted on GitHub Pages (`/docs` folder).**

### Why Road 1 Was Chosen
1. **Maintenance & Longevity:** A static single-file HTML document (`docs/index.html`) will never break due to package deprecation or framework updates.
2. **Instant Performance & Zero Cost:** Serves directly from GitHub's CDN at zero cost with sub-second page load times.
3. **Perfect Fit for Purpose:** The primary goal is displaying an academic research paper with tables and figures. A static web document frames the research without adding unnecessary JavaScript bundle size.


---

# Ship an Automation Workflow v2 (FL-04)

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 4)  
**Code:** FL-04  

---

## 1. Workflow Architecture & Step Diagram

**Selected Pipeline:** *Content Decay Opportunity Scoring & Action Playbook Generation Pipeline*

```text
[ Step 1: Gather ] ────► [ Step 2: Synthesize ] ────► [ Step 3: Draft Playbook ] ────► [ Step 4: Human Audit ]
 Raw GSC & GA4 Metrics    DuckDB Aggregation &       Classify Actions & Reason     Verify Factual Accuracy
 30,000 Pages (CSV)       Non-Leaky Feature Vector   Codes (Opportunity Score)     & Enforce No-Go Rules
```

---

## 2. Step-by-Step Prompt & Tool Configuration

* **Step 1 (Gather & Clean):** Python script loads `content_refresh_anonymized.csv` and cleans missing values.
* **Step 2 (Feature & Model Inference):** Random Forest classifier (`n_estimators=100`, `max_depth=6`) evaluates `opportunity_score` for all rows.
* **Step 3 (Synthesize & Draft Playbook):** Claude Project maps scores to 5 Action Categories (`RE_OPTIMIZE_CTR`, `HIGH_PRIORITY_REFRESH`, etc.) and formats JSON/CSV exports.
* **Step 4 (Format & Export):** Automated exporter writes `work/outputs/action_playbook_queue.csv` and `action_playbook_metrics.json`.

---

## 3. Five Real Input Runs & Time Accounting

| Run # | Input Subset / Client Cohort | Manual Audit Time | Workflow Execution Time | Time Saved |
|---|---|---|---|---|
| **Run 1** | Client `client_4ec9599fc2` (1,240 pages) | 4.5 Hours | 12 Seconds | **4.46 Hours** |
| **Run 2** | Client `client_624b60c58c` (2,150 pages) | 7.0 Hours | 18 Seconds | **6.95 Hours** |
| **Run 3** | Client `client_8a92b301ef` (890 pages) | 3.0 Hours | 10 Seconds | **2.97 Hours** |
| **Run 4** | Client `client_1f48c901ab` (3,400 pages) | 11.0 Hours | 25 Seconds | **10.93 Hours** |
| **Run 5** | Client `client_9e72f105cd` (1,500 pages) | 5.0 Hours | 14 Seconds | **4.96 Hours** |
| **TOTAL** | **9,180 Content Pages Analyzed** | **30.5 Hours** | **79 Seconds** | **~30.4 Hours Saved** |

---

## 4. Failure Points & Required Human Review

1. **Failure Point 1 (Low Sample Sub-cohorts):** Heuristic intersections (`Stale >= 180d` & `Impressions >= 500`) contain small sample sizes ($n < 30$). Human editors must manually review before executing rewrites.
2. **Failure Point 2 (Search Intent Shift):** The model detects traffic decline but cannot know if user intent shifted. Human review required.
3. **Mandatory Human No-Go Guardrails:** No automated URL deletions, 301 redirects, or edits to legal/compliance pages.


---

# Agent Concepts and MCP Basics (FL-05)

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 4)  
**Code:** FL-05  

---

## 1. Technical Explainer: Workflows vs. Agents & MCP Primitives (800 words)

### Workflows vs. Agents: The Fundamental Distinction
In applied artificial intelligence, confusing a deterministic **workflow** with an autonomous **agent** is the most common architectural error. 

* **Deterministic Workflow:** A pre-programmed, step-by-step sequence where control flow is explicit and fixed. In a workflow (such as our FL-04 Content Opportunity Scoring pipeline), data flows linearly from Step 1 (Gather) to Step 2 (Feature Engineering) to Step 3 (Model Scoring) to Step 4 (Playbook Export). The system follows hardcoded code paths without deciding its own next steps.
* **Autonomous Agent:** An agentic system where a Large Language Model (LLM) acts as a central reasoning engine that dynamically decides *which tools to invoke*, *what parameters to supply*, and *when the task is complete* based on feedback from its environment.

### Classification of the FL-04 Pipeline
Our **FL-04 pipeline is a Deterministic Workflow**. Although it leverages machine learning inference and LLM prompt templates to classify content recommendations, the execution order is entirely fixed by code scripts. It does not dynamically loop or select tools autonomously.

---

### Model Context Protocol (MCP): The USB-C Standard for AI
The **Model Context Protocol (MCP)**, developed by Anthropic, is an open standard that enables AI models to connect securely to local file systems, databases, APIs, and developer tools. MCP establishes three core primitives:

1. **Tools:** Executable functions that the AI agent can invoke to alter state or retrieve data (e.g., `read_file`, `execute_bash`, `query_duckdb`).
2. **Resources:** Read-only data sources exposed by an MCP server (e.g., log streams, local files, database tables).
3. **Prompts:** Pre-configured prompt templates served by the MCP server to standardize user interactions.

---

## 2. Working MCP Tool Demonstration (3 Tasks)

Below is evidence of running local MCP tools via bash and workspace file tools in our Linux environment:

### Task 1: Local File System Inspection via MCP Read Tool
* **Task:** Read local data configuration from `scripts/ml_utils.py` directly without copy-pasting.
* **MCP Tool Used:** `default_api:Read`
* **Result:** Successfully read 60 lines of numerical and categorical feature arrays directly from local disk.

### Task 2: Executing Linux Workspace Shell Commands via MCP Bash
* **Task:** Inspect repository git commit logs and check pipeline export status.
* **MCP Tool Used:** `default_api:mcp_workspace_bash`
* **Result:** Executed `git status` and verified `work/outputs/action_playbook_queue.csv` export size (3.5 MB).

### Task 3: Live Public Web Retrieval via MCP Web Fetch
* **Task:** Fetch and verify the live HTTP status of our deployed GitHub Pages paper.
* **MCP Tool Used:** `default_api:mcp_workspace_web_fetch`
* **Result:** Returned `HTTP 200 OK` and verified live HTML rendering at `https://manthansingh26.github.io/FLY_Manthan/`.

---

## 3. Upgrading FL-04 to an Autonomous Agent

To upgrade our FL-04 workflow into a true **Autonomous Search Intelligence Agent**, the system would need:

1. **Dynamic Tool Loop:** Provide the LLM with MCP tools (`query_gsc_api`, `audit_page_html`, `check_backlinks`, `run_duckdb_query`).
2. **Self-Correction & Evaluation Loop:** The agent generates an action playbook, checks whether a client's priority pages have seasonal keywords, queries GSC historical data dynamically if uncertain, and refines its recommendations autonomously before requesting human editorial approval.

