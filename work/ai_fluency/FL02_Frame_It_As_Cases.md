# Frame It as Cases: Work That Speaks for Itself

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 2)  

---

## 1. Standing Voice Card

> **Voice Card:** *"Direct, evidence-backed, precise, readable, zero hype."*

*Added to Claude Project `FlyRank-Applied-ML-Portfolio` as a standing instruction.*

---

## 2. Framed Case Study: Search Intelligence Opportunity Scoring

### Beat 1: The Problem
Digital publishing teams manage thousands of articles across dozens of domains, but manual content audits are slow and reactive. By the time traffic drops are noticed in analytics dashboards, search visibility has already collapsed. Editors needed a transparent, data-driven way to prioritize high-risk pages for refresh before traffic loss occurred.

### Beat 2: What I Did & Decided
I designed and evaluated an applied machine learning pipeline using 30,000 pseudonymized search intelligence records across 32 clients. 
* **Key Architectural Decisions:**
  * **Feature Engineering:** Built 29 non-leaky historical signals combining Search Console impressions, click-through rates, page age, update staleness, and GA4 engagement metrics.
  * **Target Leakage Safeguards:** Excluded `trend_direction` and `trend_pct` from features to prevent target leakage.
  * **Honest Validation Design:** Used `GroupKFold` grouped by `client_id` ($K=5$) to evaluate generalization on unseen client websites rather than memorizing site signatures.
  * **Model Benchmarking:** Evaluated Logistic Regression, Decision Trees, and Random Forests against a hand-written rule baseline.

### Beat 3: The Outcome
* **Measured Lift:** The Random Forest scoring model achieved a **Precision@50 of 0.8400 (and 0.5400 on unseen test clients)**, outperforming the heuristic baseline (**0.5200**) by **~1.6×**.
* **Operational Playbook:** Mapped opportunity scores into 5 human-reviewed action categories (`RE_OPTIMIZE_CTR`, `HIGH_PRIORITY_REFRESH`, `CONTENT_EXPANSION`, `GENERAL_REFRESH`, `MONITOR_ONLY`) with explicit no-go automation rules.
* **Public Receipts:** Deployed a live 9-section research paper on GitHub Pages with complete reproducible code receipts: [https://manthansingh26.github.io/FLY_Manthan/](https://manthansingh26.github.io/FLY_Manthan/).

---

## 3. Bio & Call-to-Action (CTA)

* **Bio:** Manthan Singh is an Applied Machine Learning Engineer specializing in leakage-free predictive scoring pipelines, search intelligence, and reproducible AI systems.
* **Contact CTA:** View the live capstone paper and GitHub codebase at [manthansingh26/FLY_Manthan](https://github.com/manthansingh26/FLY_Manthan).

---

## 4. Before & After Copy Editing

* **Generic AI Draft (Before):**
  > *"We utilized cutting-edge machine learning algorithms to leverage synergy between search engine metrics and content health scores, driving massive ROI for digital content stakeholders through revolutionary automated predictive capabilities."*

* **Edited Version (After):**
  > *"We trained a Random Forest model on 30,000 anonymized Search Console pages, achieving an 84% Precision@50 under client-holdout validation—a 1.6x efficiency boost over heuristic baselines."*
