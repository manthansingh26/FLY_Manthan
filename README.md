# FlyRank Applied Search Intelligence & AI Fluency Capstone

**Author:** Manthan Singh  
**Track:** Machine Learning Specialization & General AI Fluency (Dual Track)  
**Live Deployed Paper:** [https://manthansingh26.github.io/FLY_Manthan/](https://manthansingh26.github.io/FLY_Manthan/)  
**Public Repository:** [https://github.com/manthansingh26/FLY_Manthan](https://github.com/manthansingh26/FLY_Manthan)  

---

## Executive Summary & Target Audience

This repository contains the end-to-end applied machine learning pipeline, research paper, and operational Content Action Playbook for **Lane 2: Refresh / Content Opportunity Scoring**. 

Evaluated on **30,000 pseudonymized search performance records** across 32 digital publication clients, the system predicts content traffic decay and ranks articles for editorial review before search visibility collapses.

---

## System Architecture

```text
[ Raw GSC & GA4 Metrics ] ──► [ DuckDB Feature Extraction ] ──► [ Random Forest (100 Trees) ]
   (30k Pages x 44 Cols)        (29 Non-Leaky Features)          (GroupKFold Split)
                                                                         │
                                                                         ▼
[ Live Deployed Paper ] ◄── [ Action Playbook Queue ] ◄── [ Opportunity Scores ]
 (docs/index.html)            (work/outputs/queue.csv)     (Precision@50 = 0.8400)
```

---

## Reproducible Setup & Execution Guide

```bash
# 1. Clone the repository
git clone https://github.com/manthansingh26/FLY_Manthan.git
cd FLY_Manthan

# 2. Install dependencies
pip install -r requirements.txt

# 3. Execute the full end-to-end pipeline & generate exports
python3 scripts/run_all.py
```

---

## Measured Benchmark Results

| Method | Accuracy | Precision@50 | Lift over Baseline |
|---|---|---|---|
| **Dataset Base Rate** | 0.4902 | 0.4902 | 1.0× |
| **Rule Baseline (Stale × Visible)** | N/A | 0.5200 | 1.0× |
| **Logistic Regression** | 0.5275 | 0.6400 | 1.23× |
| **Decision Tree (depth=4)** | 0.5755 | 0.5400 | 1.04× |
| **Random Forest (100 trees)** | **0.5619** | **0.8400 (0.5400 on unseen clients)** | **~1.6×** |

---

## Limitations & Safety Guardrails

1. **No Causal Claims:** Measures statistical associations in historical search data; does not claim refreshing a page causes search ranking recovery.
2. **No Algorithm Prediction:** Does not predict internal search engine algorithm weights or penalties.
3. **Strict No-Go Automations:** Prohibits automated URL deletions, 301 redirects, or unverified LLM text generation.

---

## AI Transparency Statement

> *"I built this repository and research paper in collaboration with Claude (Anthropic). Claude assisted with drafting initial pipeline scripts, HTML layouts, and markdown documentation templates. I personally designed the target leakage exclusion rules (`trend_direction` excluded), verified the `GroupKFold` client-holdout split, debugged Python execution errors, and validated all precision metrics against raw data."*

---

## Master Deliverables & Track Index

* **Live Deployed Paper:** [`docs/index.html`](docs/index.html)
* **Capstone Notebook:** [`work/notebooks/capstone.ipynb`](work/notebooks/capstone.ipynb)
* **General AI Fluency Master Index:** [`work/ai_fluency/FL10_Retrospective_And_Master_Index.md`](work/ai_fluency/FL10_Retrospective_And_Master_Index.md)
* **Data Credit:** Built on the [FlyRank ML Internship Dataset](https://flyrank.ai).
