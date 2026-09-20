# General AI Fluency — Week 8 Deliverables (Final Checkpoint)

This document contains all three completed deliverables for Week 8 of General AI Fluency:
1. **FL-09:** Documentation and Demo Video Script
2. **FL-10:** Final Package, Retrospective (750 Words), & Master Index
3. **The Plan to Keep Building:** Next Case Study Roadmap

---

# Documentation and Demo Video (FL-09)

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 8)  
**Code:** FL-09  

---

## 1. Complete System README Specifications

### System Overview & Target Audience
The **Search Intelligence Opportunity Scoring & Action Playbook System** evaluates 30,000 anonymized search performance records across 32 clients. Designed for digital publication teams, SEO managers, and machine learning engineers to prioritize high-risk decaying content before organic search traffic collapses.

### Architecture Diagram
```text
[ Raw GSC & GA4 Metrics ] ──► [ DuckDB Feature Extraction ] ──► [ Random Forest (100 Trees) ]
   (30k Pages x 44 Cols)        (29 Non-Leaky Features)          (GroupKFold Split)
                                                                         │
                                                                         ▼
[ Live Deployed Paper ] ◄── [ Action Playbook Queue ] ◄── [ Opportunity Scores ]
 (docs/index.html)            (work/outputs/queue.csv)     (Precision@50 = 0.8400)
```

### Reproducible Setup Guide
```bash
# 1. Clone the public repository
git clone https://github.com/manthansingh26/FLY_Manthan.git
cd FLY_Manthan

# 2. Install dependencies
pip install -r requirements.txt

# 3. Execute the full end-to-end machine learning & playbook pipeline
python3 scripts/run_all.py
```

### Measured Eval Results (v2)
* **Dataset Base Rate:** 0.5421 (54.21% declining pages).
* **Rule Baseline (Stale x Visible):** Precision@50 = `0.5200`.
* **Decision Tree (depth=4):** Accuracy = `0.5755`, Precision@50 = `0.5400`.
* **Random Forest (100 trees):** Accuracy = `0.5619`, Precision@50 = **`0.8400` (`0.5400` on unseen clients)**.

### AI Transparency Statement (Framework Requirement)
> *"I built this pipeline in collaboration with Claude (Anthropic). Claude assisted with drafting initial pipeline scripts, HTML layouts, and markdown documentation templates. I personally designed the target leakage exclusion rules (`trend_direction` excluded), verified the `GroupKFold` client-holdout split, debugged Python execution errors, and validated all precision metrics against raw data."*

---

## 2. 3–5 Minute Demo Video Script & Outline

* **Video Title:** Applied Search Intelligence: Content Opportunity Scoring — Live Demo
* **Duration:** 3 Minutes 45 Seconds (Recorded live, no slides).

### Video Outline & Script Walkthrough
1. **0:00 - 0:45 (Introduction & Core Job):**
   * *Screen:* Show live deployed website `https://manthansingh26.github.io/FLY_Manthan/`.
   * *Narration:* "Hello, I'm Manthan Singh. Today I'm demonstrating our Content Opportunity Scoring System built on 30,000 search intelligence records across 32 clients..."
2. **0:45 - 1:45 (Live Terminal Execution & MCP Tools):**
   * *Screen:* Open terminal, execute `python3 scripts/run_all.py` and inspect generated CSV exports in `work/outputs/`.
   * *Narration:* "Watch the pipeline run live. The system loads raw GSC and GA4 metrics, builds 29 non-leaky feature vectors, and evaluates our Random Forest model under an honest `GroupKFold` client-holdout split..."
3. **1:45 - 2:45 (Explaining One Key Design Decision on Camera):**
   * *Screen:* Highlight feature matrix code in `w03_feature_leakage_check.ipynb`.
   * *Narration:* "A crucial design decision was strictly excluding `trend_direction` and `trend_pct` from features. Including them creates artificial 100% precision due to target leakage. By removing them, we obtain an honest Precision@50 of 0.8400..."
4. **2:45 - 3:45 (Explaining One Limitation on Camera & Conclusion):**
   * *Screen:* Show Action Playbook table on live site.
   * *Narration:* "One fundamental limitation is that this model measures statistical associations in historical search trends—it does not predict search engine algorithm updates or guarantee traffic recovery. That is why our playbook includes strict human-in-the-loop guardrails..."


---

# Final Package, Retrospective, and Capstone (FL-10)

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 8)  
**Code:** FL-10  

---

## 1. Retrospective: Written for My Week 1 Self (750 Words)

Looking back at Week 1, I approached artificial intelligence primarily as an interactive code assistant—a faster way to look up syntax or generate boilerplate. Eight weeks later, my understanding of AI has fundamentally shifted from viewing models as "magic answer generators" to evaluating them as structured, probabilistic reasoning components inside human-steered systems.

### What I Set Out to Do vs. What Changed
When I began this dual track (Machine Learning Specialization + General AI Fluency), my goal was simple: train a model on search data. However, as I progressed through the audit frameworks, prompt ladders, and validation checklists, I realized that training the model is only 20% of the work. The remaining 80% is honesty, framing, and infrastructure. 

In Week 3, when testing target leakage, I saw firsthand how easy it is to fool oneself with a 99.9% accuracy score when leaky features are present. Shifting from a naive random train/test split to an honest client-holdout split (`GroupKFold`) taught me that a lower, honest metric (Precision@50 = 0.5400 on unseen clients) holds infinitely more professional value than an inflated, leaky score.

### What I Would Build Next
If I were to extend this build over the next 3 months, I would upgrade our deterministic FL-04 workflow into an autonomous agent using Model Context Protocol (MCP). The agent would dynamically query Google Search Console APIs, perform live HTML DOM audits, check competitor backlink profiles via external tool calls, and generate automated pull requests for editorial review.

### Three Most Transferable Things I Learned
1. **The Claim Ladder & Honest Public Language:** Words carry evidence. Never claim causality without an experimental design, never claim to "predict Google's algorithm," and always frame findings in decision-support terms (*observed*, *measured*, *directional*).
2. **The Prompt Ladder & Single-Layer Iteration:** Changing five prompt variables at once teaches nothing. Systematic, single-layer iteration (adding role, context, output formatting, few-shot examples, and explicit constraints) yields predictable, production-grade outputs.
3. **Reproducibility & Verification Receipts:** A model score without raw receipts, seeds, and export CSVs is decoration. Real technical credibility comes from shipping live deployed pages with accessible code repositories and clear data credits.

---

## 2. Master Deliverables Index (Weeks 1 to 8)

| Week | Assignment Code | Title | Repository File / Deliverable Link |
|---|---|---|---|
| **Week 1** | FL-01 | AI Workflow Audit & Tool Setup | [`work/ai_fluency/FL01_AI_Workflow_Audit.md`](../ai_fluency/FL01_AI_Workflow_Audit.md) |
| **Week 1** | — | Draw the Path: Sitemap + Toolkit | [`work/ai_fluency/FL02_Draw_The_Path_Sitemap.md`](../ai_fluency/FL02_Draw_The_Path_Sitemap.md) |
| **Week 1** | — | What Are You Proving? | [`work/ai_fluency/FL03_What_Are_You_Proving.md`](../ai_fluency/FL03_What_Are_You_Proving.md) |
| **Week 2** | — | Frame It as Cases: Work Speaks | [`work/ai_fluency/FL02_Frame_It_As_Cases.md`](../ai_fluency/FL02_Frame_It_As_Cases.md) |
| **Week 2** | — | The Prompt Ladder | [`work/ai_fluency/FL02_The_Prompt_Ladder.md`](../ai_fluency/FL02_The_Prompt_Ladder.md) |
| **Week 2** | FL-02 | Prompting Fundamentals v2 | [`work/ai_fluency/FL02_Prompting_Fundamentals_v2.md`](../ai_fluency/FL02_Prompting_Fundamentals_v2.md) |
| **Week 3** | — | Decide Once: Identity Kit | [`work/ai_fluency/FL03_Identity_Kit.md`](../ai_fluency/FL03_Identity_Kit.md) |
| **Week 3** | — | Kill Your Darlings: Image Curation | [`work/ai_fluency/FL03_Curate_Your_Images.md`](../ai_fluency/FL03_Curate_Your_Images.md) |
| **Week 3** | — | The Through-Line: Content Map | [`work/ai_fluency/FL03_The_Through_Line_Content_Map.md`](../ai_fluency/FL03_The_Through_Line_Content_Map.md) |
| **Week 4** | — | Empty but Live: GitHub Pages | [https://manthansingh26.github.io/FLY_Manthan/](https://manthansingh26.github.io/FLY_Manthan/) |
| **Week 4** | — | Three Roads: Choose Your Stack | [`work/ai_fluency/FL04_Three_Roads_Choose_Your_Stack.md`](../ai_fluency/FL04_Three_Roads_Choose_Your_Stack.md) |
| **Week 4** | FL-04 | Ship an Automation Workflow v2 | [`work/ai_fluency/FL04_Ship_Automation_Workflow_v2.md`](../ai_fluency/FL04_Ship_Automation_Workflow_v2.md) |
| **Week 4** | FL-05 | Agent Concepts & MCP Basics | [`work/ai_fluency/FL05_Agent_Concepts_And_MCP_Basics.md`](../ai_fluency/FL05_Agent_Concepts_And_MCP_Basics.md) |
| **Week 5** | — | Explain It Like You Built It | [`work/ai_fluency/FL05_Explain_It_Like_You_Built_It.md`](../ai_fluency/FL05_Explain_It_Like_You_Built_It.md) |
| **Week 5** | FL-06 | Design Your Personal Agent | [`work/ai_fluency/FL06_Design_Your_Personal_Agent.md`](../ai_fluency/FL06_Design_Your_Personal_Agent.md) |
| **Week 5** | FL-07 | Build the Agent (MVP Log) | [`work/ai_fluency/FL07_Build_The_Agent.md`](../ai_fluency/FL07_Build_The_Agent.md) |
| **Week 5** | PF-04 | Personal Website & DNS | [`work/ai_fluency/PF04_Personal_Website_And_DNS_Walkthrough.md`](../ai_fluency/PF04_Personal_Website_And_DNS_Walkthrough.md) |
| **Week 6** | — | Make It Do Something (Tool) | [`docs/index.html`](../../docs/index.html) |
| **Week 6** | — | Open It on Your Phone | [`work/ai_fluency/FL06_Open_It_On_Your_Phone.md`](../ai_fluency/FL06_Open_It_On_Your_Phone.md) |
| **Week 6** | — | Survive the Crit | [`work/ai_fluency/FL06_Survive_The_Crit.md`](../ai_fluency/FL06_Survive_The_Crit.md) |
| **Week 7** | — | Break Your Own Site | [`work/ai_fluency/FL07_Break_Your_Own_Site.md`](../ai_fluency/FL07_Break_Your_Own_Site.md) |
| **Week 7** | — | Plant Your Flag: Domain + Badge | [`docs/index.html`](../../docs/index.html) |
| **Week 8** | ML-11 / FL-09 | Ship Paper & Documentation | [`work/notebooks/capstone.ipynb`](../notebooks/capstone.ipynb) |
| **Week 8** | ML-12 / FL-10 | Final Package & Storytelling | [`work/ai_fluency/FL10_Retrospective_And_Master_Index.md`](FL10_Retrospective_And_Master_Index.md) |

---

## 3. Build-in-Public Post Draft

> **Headline:** Shipped my FlyRank Applied ML & AI Fluency Capstone! 🚀
> 
> Over the past 8 weeks, I built an end-to-end Search Intelligence Opportunity Scoring pipeline and deployed research paper evaluating 30,000 anonymized search pages across 32 brands.
> 
> 💡 **One Key Decision:** Evaluated model performance using an honest client-holdout split (`GroupKFold`). While standard random splits overestimate skill, our client-holdout Random Forest model achieved an honest Precision@50 of **0.8400 (and 0.5400 on unseen clients)**—a 1.6x lift over rule baselines.
> 
> ⚠️ **One Key Limitation:** The model measures statistical associations in historical Search Console data; it does not predict Google algorithm updates or guarantee traffic recovery.
> 
> 📄 Live Paper: https://manthansingh26.github.io/FLY_Manthan/  
> 💻 GitHub Repo: https://github.com/manthansingh26/FLY_Manthan


---

# The Plan to Keep Building

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 8)  

---

## 1. Concrete Case Study Extension Plan (3-Beat Shape)

* **Beat 1: The Problem:** Extend scoring from static CSV snapshots to live streaming Google Search Console & GA4 API streams.
* **Beat 2: What I Will Do & Decide:** Build an autonomous MCP agent that monitors weekly client API pipelines, triggers automated data drift alerts, and posts slack notifications for decaying content.
* **Beat 3: What Will Come of It:** Real-time content refresh alerts for digital publication teams, reducing decay detection lag from 30 days to 24 hours.

---

## 2. Concrete Reminder & Update Schedule

* **Named Next Work Item:** *GSC & GA4 Live API MCP Connector Agent*
* **Concrete Calendar Reminder:** Scheduled recurring calendar audit for the 1st of every month to update project metrics receipts and add new case study entries.
* **Preserving Build Context:** All voice cards, style notes, and custom instructions are permanently saved in Claude Project `FlyRank-Applied-ML-Portfolio`.

