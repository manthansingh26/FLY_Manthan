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
