# General AI Fluency — Week 2 Deliverables

This document contains all three completed deliverables for Week 2 of General AI Fluency:
1. **Frame It as Cases:** Work That Speaks for Itself
2. **The Prompt Ladder:** 6-Run Optimization & Analysis
3. **FL-02:** Prompting Fundamentals on Real Tasks v2

---

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


---

# The Prompt Ladder

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 2)  

---

## Overview

This assignment evaluates prompt optimization across 6 versions (1 weak baseline + 5 single-layer additions) applied to the machine learning domain task: *Evaluating model performance for content decay scoring*.

---

## Run 0: Naive Baseline Prompt (Weak)

```text
Explain this model data to me.
```

* **Output Excerpt:** "Model data refers to the numbers and statistics collected when training a machine learning model, such as accuracy, loss, training time, dataset size, and hyperparameter values..."
* **Notes:**
  * *What Changed:* Initial lazy 5-word prompt.
  * *What Improved:* N/A (Baseline).
  * *What Failed:* Completely generic definition of machine learning terminology; failed to address any specific dataset, metric, or task.
  * *Next Layer Needed:* Add a clear goal.

---

## Run 1: Layer 1 — Clear Goal

```text
Explain the performance gap between a Decision Tree and a Random Forest on a content scoring task.
```

* **Output Excerpt:** "A Decision Tree splits data based on single feature thresholds, which can overfit. A Random Forest combines multiple trees, reducing variance and improving ranking precision..."
* **Notes:**
  * *What Changed:* Added a specific comparative goal.
  * *What Improved in Output:* Shifted from generic definitions to a focused explanation of model variance and ensemble tree performance.
  * *What Failed:* High-level textbook explanation; lacked real dataset numbers or evaluation context.
  * *Next Layer Needed:* Add real dataset context.

---

## Run 2: Layer 2 — Real Context

```text
Explain the performance gap between a Decision Tree (Accuracy 0.5755, Precision@50 0.5400) and a Random Forest (Accuracy 0.5619, Precision@50 0.8400) trained on 30,000 Search Console pages evaluated under GroupKFold client-holdout validation.
```

* **Output Excerpt:** "In a client-holdout split, Random Forest achieves 0.8400 Precision@50 because ensemble bagging captures non-linear interactions across traffic velocity features without memorizing specific client signatures, whereas a single Decision Tree lacks depth to rank top-50 items effectively..."
* **Notes:**
  * *What Changed:* Supplied real metrics (Precision@50) and validation constraints (`GroupKFold`).
  * *What Improved in Output:* Grounded the explanation in actual numbers; correctly analyzed why top-K precision increased despite similar overall accuracy.
  * *What Failed:* Output was unstructured paragraphs without clear executive summary formatting.
  * *Next Layer Needed:* Add target audience.

---

## Run 3: Layer 3 — Target Audience

```text
Explain the performance gap between a Decision Tree (Precision@50 0.5400) and a Random Forest (Precision@50 0.8400) on 30,000 search pages under GroupKFold validation to an Editorial Operations Director who does not know ML jargon.
```

* **Output Excerpt:** "Imagine picking the top 50 pages that need urgent updates. A simple Decision Tree rule gets 27 out of 50 right (54%). The Random Forest model gets 42 out of 50 right (84%). It does this by looking at traffic history and update age together rather than one rule at a time..."
* **Notes:**
  * *What Changed:* Specified non-technical audience (Editorial Operations Director).
  * *What Improved in Output:* Replaced statistical jargon with clear business metaphors (27/50 vs 42/50 correct picks).
  * *What Failed:* Lacked structured action steps for how the team should act on the 84% precision score.
  * *Next Layer Needed:* Specify output structure.

---

## Run 4: Layer 4 — Output Structure

```text
Explain the performance gap between Decision Tree (Precision@50 0.5400) and Random Forest (Precision@50 0.8400) to an Editorial Director. Format as: 1) Executive Summary (2 sentences), 2) Business Impact Table, 3) Recommended Next Action.
```

* **Output Excerpt:**
  > **1. Executive Summary:** The Random Forest model increases the accuracy of our top-50 content refresh queue from 54% to 84% on new websites. This allows editorial teams to focus effort exclusively on high-risk pages without wasting budget.
  > 
  > **2. Business Impact Table:**
  > | Method | Correct Top-50 Picks | Editorial Efficiency |
  > |---|---|---|
  > | Single Rule Tree | 27 / 50 (54%) | Baseline |
  > | Random Forest | 42 / 50 (84%) | +55% precision gain |
  > 
  > **3. Recommended Action:** Deploy the Random Forest queue to prioritize weekly editor content audits.
* **Notes:**
  * *What Changed:* Enforced strict Markdown section headers and table layout.
  * *What Improved in Output:* Dramatically improved readability; executive summary and table can be read in 15 seconds.
  * *What Failed:* Didn't state negative constraints or safety boundaries (no causal claims).
  * *Next Layer Needed:* Add constraints & safety guardrails.

---

## Run 5: Layer 5 — Constraints & Verification Guardrails

```text
Explain the performance gap between Decision Tree (Precision@50 0.5400) and Random Forest (Precision@50 0.8400) to an Editorial Director. Format as: 1) Executive Summary, 2) Business Impact Table, 3) Recommended Action. Constraints: Use public-safe language (observed, measured, decision-support). Never claim the model predicts Google's algorithm or causes traffic recovery.
```

* **Output Excerpt:**
  > **1. Executive Summary:** In measured client-holdout evaluations, our Random Forest scoring model achieved an observed **Precision@50 of 0.8400**, compared to **0.5400** for a single Decision Tree. This provides a directional decision-support queue for editorial prioritization.
  > 
  > **2. Business Impact Table:**
  > | Evaluation Method | Measured Precision@50 | Operational Value |
  > |---|---|---|
  > | Single Tree Rule | 0.5400 | Baseline candidate selection |
  > | Random Forest | 0.8400 | +55% observed precision lift |
  > 
  > **3. Recommended Action & Safety Limits:** Use the queue to guide manual content audits. Note: The model identifies statistical associations in historical data; it does not predict search engine algorithm changes or guarantee ranking recovery.
* **Notes:**
  * *What Changed:* Enforced strict public-safe claim constraints.
  * *What Improved in Output:* Eliminated all overconfident language; explicitly included safety caveats and honest framing.
  * *What Failed:* N/A — Best finalized prompt.

---

## Final Reusable Prompt Template

```text
Act as a Senior ML Strategy Lead explaining model evaluation metrics to [TARGET AUDIENCE].

Context: We evaluated [MODEL 1] vs [MODEL 2] on [DATASET SPECIFICATION] using [VALIDATION METHOD].
Metrics:
- Model 1: [METRIC NAME] = [VALUE]
- Model 2: [METRIC NAME] = [VALUE]

Format your response into three sections:
1. Executive Summary (2 sentences max)
2. Business Impact Table
3. Recommended Action & Safety Boundaries

Constraints:
- Use public-safe language (observed, measured, directional, decision-support).
- Never use causal terms ("causes", "guarantees", "predicts algorithm").
```


---

# Prompting Fundamentals on Real Tasks v2 (FL-02)

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 2)  
**Code:** FL-02  

---

## Target Task from FL-01 Audit
**Target Task:** *Content Decay Opportunity Scoring & Action Playbook Generation*

---

## Prompt Iteration Log (6 Versions)

### Version 0: Naive One-Line Prompt
```text
Give me a content refresh queue from this data.
```
* **Output:** "Here is a general structure for a content refresh queue: 1. Title, 2. URL, 3. Views, 4. Action required (Update/Delete/Keep)..."
* **Iteration Note:** Completely unanchored template; lacked data fields, scoring logic, or reason codes.

### Version 1: Technique — Role Assignment
```text
Act as a Lead Content Strategist. Give me a content refresh queue for a digital publisher with 30,000 articles.
```
* **Output:** "As a Lead Content Strategist, I recommend auditing content by age and traffic. Focus first on high-traffic pages older than 6 months..."
* **Iteration Note:** Adopted an authoritative persona, but still lacked technical scoring algorithms.

### Version 2: Technique — Context & Motivation
```text
Act as a Lead Content Strategist. We have 30,000 pseudonymized search pages. Content teams need to prioritize pages before search traffic drops. Create a scoring logic that combines update staleness and 90-day Search Console impressions.
```
* **Output:** "To prevent traffic drops, assign points: +2 points for pages untouched in 180+ days, +3 points for pages with 500+ impressions. Rank pages by total score..."
* **Iteration Note:** Successfully established the baseline scoring logic ($score = 2 	imes stale + 3 	imes visible$).

### Version 3: Technique — Output Structure
```text
Act as a Lead Content Strategist. Create a content refresh queue logic. Output a Markdown table with columns: Action Category, Reason Code, Criteria, and Recommended Editorial Action.
```
* **Output:**
  | Action Category | Reason Code | Criteria | Recommended Action |
  |---|---|---|---|
  | HIGH_PRIORITY_REFRESH | HIGH_VISIBILITY_STALE | Score >= 0.60 & Imp >= 500 & Stale >= 180d | Immediate editorial rewrite |
  | RE_OPTIMIZE_CTR | LOW_CTR_HIGH_IMP | Imp >= 500 & CTR < 0.5% | Re-optimize title & meta tags |
* **Iteration Note:** Produced a clean structured playbook table matching exact enterprise schema.

### Version 4: Technique — Few-Shot Examples
```text
Act as a Lead Content Strategist. Generate reason codes for content queue items based on the following examples:
Example 1: Imp=5000, Stale=200d -> Action: HIGH_PRIORITY_REFRESH | Reason: HIGH_VISIBILITY_STALE
Example 2: Imp=8000, CTR=0.2% -> Action: RE_OPTIMIZE_CTR | Reason: LOW_CTR_HIGH_IMPRESSIONS
Now categorize: Imp=12000, Stale=190d, CTR=0.3%
```
* **Output:** "Action: HIGH_PRIORITY_REFRESH | Reason: HIGH_VISIBILITY_STALE (Secondary note: Low CTR requires meta tag update)."
* **Iteration Note:** Few-shot examples taught the model to multi-label complex edge cases accurately.

### Version 5: Technique — Step Decomposition & Guardrails
```text
Act as a Lead Content Strategist. Work step-by-step:
Step 1: Define non-leaky feature thresholds.
Step 2: Assign Action Category and Reason Code.
Step 3: Output the Playbook Table.
Step 4: Include strict No-Go rules for automation.
Constraint: Use decision-support language (observed, measured). Never automate page deletions or legal content updates.
```
* **Output:** Includes complete step-by-step logic, full playbook matrix, and explicit human-in-the-loop no-go rules.
* **Iteration Note:** Perfect final structured output combining all prompting best practices.

---

## Cross-Model Comparison (Claude vs ChatGPT)

| Dimension | Claude 3.5 / Haiku | ChatGPT (GPT-4o) |
|---|---|---|
| **Tone & Style** | Direct, precise, technical, highly structured. | Conversational, descriptive, slightly more verbose. |
| **Constraint Following** | Strictly obeyed negative constraints (zero forbidden terms). | Included safety warnings but added extra commentary. |
| **Table Formatting** | Clean, compact Markdown tables. | Well-formatted Markdown with extra bullet point breakdowns. |
| **Failure Points** | Required explicit prompts to add qualitative context. | Tended to re-introduce buzzwords if not heavily constrained. |

---

## Final Reusable Prompt Template

```text
Act as a Lead Content & Search Intelligence Strategist.

Task: Build a Content Action Playbook for [DATASET SPECIFICATION].

Instructions:
1. Define non-leaky historical signals (Age, Staleness, Impressions, CTR).
2. Map model opportunity scores to 5 Action Categories: [CATEGORY LIST].
3. Format output as a Markdown table with columns: Action Category, Reason Code, Criteria, Action Required.
4. Include a mandatory Human Review Checklist and a Strict No-Go Automation List.

Constraints:
- Use public-safe language (observed, measured, directional, decision-support).
- Never automate URL deletions, 301 redirects, or legal/compliance content edits.
```

