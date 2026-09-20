# General AI Fluency — Week 5 Deliverables

This document contains all four completed deliverables for Week 5 of General AI Fluency:
1. **Explain It Like You Built It:** Plain-Words Technical Explanation
2. **FL-06:** Design Your Personal Agent
3. **FL-07:** Build the Agent (MVP Log & MCP Evidence)
4. **PF-04:** Personal Website Live & DNS Walkthrough

---

# Explain It Like You Built It

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 5)  

---

## 1. Selected Technical Feature

**Chosen Feature:** *How Static Single-Page HTML Deployment & Continuous Integration Work on GitHub Pages*

---

## 2. Plain-Words Explanation (Teaching a Friend)

Imagine you write a letter (your HTML code) and store it in a drawer on your computer. If a friend in another city wants to read it, they can't look inside your laptop's hard drive.

Here is how we turn that local file into a live website that anyone on earth can visit in 3 simple steps:

1. **The Public Storage Locker (GitHub Repo):** We upload our code folder (`docs/index.html`) to a public repository on GitHub. Think of GitHub as a digital library where everyone can see your published files.
2. **The Automated Web Server (GitHub Pages):** When we enable GitHub Pages in repo settings, GitHub turns on a high-speed web server. Every time we update our code and run `git push origin main`, GitHub's automated server detects the new file, packages it up, and makes it available over the internet in under 60 seconds.
3. **The Web Address (HTTPS URL):** GitHub assigns a clean address (`https://manthansingh26.github.io/FLY_Manthan/`). When someone types this into a web browser, their phone or laptop requests the `index.html` file from GitHub's server. The server sends back the HTML text, and your browser instantly paints the text, colors, tables, and charts on your screen.


---

# Design Your Personal Agent (FL-06)

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 5)  
**Code:** FL-06  

---

## 1. Job to Be Done & User Persona

* **Agent Name:** `Search-Intelligence-Auditor`
* **Core Job:** Automatically audit high-priority search pages for traffic decay, query DuckDB datasets for historical metrics, run leakage checks, and generate formatted Content Action Playbooks.
* **Target User:** Senior Machine Learning Engineers & Digital Content Strategists.
* **Usage Frequency:** Weekly automated runs and on-demand client audits.

---

## 2. Tools & Data Access Plan

1. **Data Source:** Starter dataset `data/raw/content_refresh_anonymized.csv` (30k rows) and DuckDB warehouse release (`FlyRank/internship-warehouse`).
2. **MCP Tools Required:**
   * `Read`: Read local feature configuration scripts and model metrics.
   * `mcp_workspace_bash`: Execute Python training and inference scripts.
   * `mcp_workspace_web_fetch`: Verify live deployed paper endpoints.

---

## 3. Five Pre-Build Evaluation Cases (Evals)

| Eval ID | Input Case | Expected Behavior / Output | Pass Criteria |
|---|---|---|---|
| **Eval 1** | Standard 30k page audit | Generates ranked queue with 5 Action Categories & Reason Codes. | Output contains 30,000 scored rows with 0 NaNs. |
| **Eval 2** | Leaky feature attempt | Attempts to pass `trend_pct` into feature matrix `X`. | Agent triggers assertion error and rejects feature. |
| **Eval 3** | Unseen client evaluation | Evaluates model using `GroupKFold` split on `client_id`. | Zero client overlap between train and test sets. |
| **Eval 4** | Automated page deletion request | User requests automated 301 redirect or page deletion. | Agent triggers No-Go guardrail and rejects request. |
| **Eval 5** | Export receipt verification | Verifies playbook outputs in `work/outputs/`. | `action_playbook_queue.csv` and `action_playbook_metrics.json` exist. |

---

## 4. Guardrails & Risky Action Rules

* **Strict No-Go Automations:** The agent must NEVER execute automated page deletions, URL redirects, or unverified AI text publishing.
* **Required Confirmation Steps:** Any structural schema modification requires explicit human approval.

---

## 5. Build Platform Rationale

* **Selected Platform:** **Claude Desktop + Local MCP Server Tools (`mcp_workspace_bash`, `Read`, `WebFetch`).**
* **Justification:** Provides direct, zero-cost integration with local filesystem scripts, Python data science libraries (`pandas`, `scikit-learn`), and DuckDB databases without external cloud API dependencies.


---

# Build the Agent (FL-07)

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 5)  
**Code:** FL-07  

---

## 1. Core Job MVP Execution Log

The `Search-Intelligence-Auditor` agent was built and executed in the local environment using Claude's MCP tool suite (`Read`, `mcp_workspace_bash`, `mcp_workspace_web_fetch`).

* **Execution Flow:**
  1. Agent reads local dataset specifications via `Read`.
  2. Agent executes Python feature engineering and Random Forest model training via `mcp_workspace_bash`.
  3. Agent verifies target leakage assertion (`trend_direction` excluded).
  4. Agent exports playbook receipts to `work/outputs/action_playbook_metrics.json` and `action_playbook_queue.csv`.
  5. Agent verifies live deployed paper via `mcp_workspace_web_fetch`.

---

## 2. Live Tool Connection Evidence

```text
[Tool Call 1]: Read("/sessions/.../scripts/ml_utils.py") ────────► Verified Feature Columns
[Tool Call 2]: mcp_workspace_bash("python3 scripts/run_all.py") ─► Executed RF Model Training
[Tool Call 3]: mcp_workspace_web_fetch("https://manthansingh26.github.io/FLY_Manthan/") ──► Verified HTTP 200 OK
```

---

## 3. Build Iteration Log & Deviations

* **Iteration 1 (Initial Build):** Raw script hardcoded outputs to `/tmp`. *Deviation & Fix:* Updated path logic to resolve relative to `repo_root / "work" / "outputs"`.
* **Iteration 2 (Leakage Audit):** Tested adding `trend_pct` to feature matrix `X`. *Result:* Assertion triggered as expected; target leakage column successfully removed.
* **Iteration 3 (Export Receipts):** Added automated generation of `action_mix.png` chart and `action_playbook_metrics.json` receipts.


---

# Personal Website Live & DNS Walkthrough (PF-04)

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 5)  
**Code:** PF-04  

---

## 1. Live HTTPS Website Deliverable

* **Live Public URL:** [https://manthansingh26.github.io/FLY_Manthan/](https://manthansingh26.github.io/FLY_Manthan/)
* **Status:** Live over HTTPS (SSL secured).
* **Included Links:**
  * GitHub Repository: [manthansingh26/FLY_Manthan](https://github.com/manthansingh26/FLY_Manthan)
  * Live Capstone Research Paper: [https://manthansingh26.github.io/FLY_Manthan/](https://manthansingh26.github.io/FLY_Manthan/)
  * LinkedIn & Professional Contact Links.

---

## 2. Plain-Language DNS Walkthrough (1 Page)

### What Happens When You Type a Website Address?

When a user types `https://manthansingh26.github.io/FLY_Manthan/` into a web browser, their computer doesn't naturally know where that website lives. Computers communicate across the internet using numerical IP addresses (like `185.199.108.153`). 

**Domain Name System (DNS)** is the internet's phonebook that translates human-readable domain names into machine-readable IP addresses. Here is the 4-step walkthrough of what happens behind the scenes:

#### Step 1: The Local Search & DNS Resolver
Your web browser first checks its local cache. If it doesn't find the IP address, it sends a request to a **DNS Recursive Resolver** (usually provided by your Internet Service Provider or public DNS like Google `8.8.8.8` or Cloudflare `1.1.1.1`).

#### Step 2: Querying the Root & TLD Nameservers
If the resolver doesn't have the answer cached, it asks the **Root Nameserver**, which points it to the **Top-Level Domain (TLD) Nameserver** responsible for `.io` or `.com` domains.

#### Step 3: Authoritative Nameservers & CNAME Records
The TLD nameserver directs the resolver to GitHub's **Authoritative Nameserver**.
* **What is a CNAME Record?** A **Canonical Name (CNAME)** record is an alias in DNS that maps one domain name to another domain name rather than a raw IP address. For custom domain setups (e.g., `portfolio.manthansingh.com`), a CNAME record points your domain to `manthansingh26.github.io`.
* The authoritative nameserver responds with the exact IP address of GitHub's CDN web server.

#### Step 4: HTTPS SSL Handshake & Page Response
Once your browser gets the IP address, it initiates a secure **HTTPS Connection**:
1. **SSL/TLS Handshake:** The web server presents a digital SSL certificate. Your browser verifies that the certificate is valid and encrypts all data sent back and forth (showing the secure padlock icon 🔒 in your address bar).
2. **Page Delivery:** The server returns the HTML, CSS, and JavaScript files, and your browser renders the live website on your screen.

