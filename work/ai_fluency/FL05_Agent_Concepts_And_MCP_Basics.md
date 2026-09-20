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
