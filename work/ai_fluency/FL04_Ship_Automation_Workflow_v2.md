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
