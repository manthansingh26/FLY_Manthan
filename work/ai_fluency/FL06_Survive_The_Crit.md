# Survive the Crit

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 6)  

---

## 1. Design Review Submission

* **Reviewer:** Peer Engineer & Technical Portfolio Reviewer.
* **Proof Statement Provided:** *"I design and evaluate leakage-free machine learning scoring pipelines that turn raw search data into prioritized, human-reviewed editorial action."*

---

## 2. 10-Second Impression Test Answers

* **Question 1: In 10 seconds, what do I do?**
  * *Reviewer Answer:* "You build machine learning models to score and rank content pages for search traffic decay." (PASSED — Exact match to claim).
* **Question 2: Would you believe I'm good at it?**
  * *Reviewer Answer:* "Yes, because you immediately show the Random Forest Precision@50 benchmarks, zero leakage checks, and a live working paper rather than just claiming skills." (PASSED).

---

## 3. Feedback Sorting: Must-Fix vs. Nice-to-Have

### Must-Fix Items (Addressed Immediately on Live Site)
1. **Confusing Metric Labeling:** *Feedback:* "The 0.8400 Precision@50 score was confusing without explicitly stating it was evaluated on top-50 items."
   * *Fix Applied:* Updated table header to read `Precision@50 (Top-50 Review Items)` and added an explanatory footnote.
2. **CTA Visibility:** *Feedback:* "The GitHub repository link in the header was subtle."
   * *Fix Applied:* Styled the repository link with a high-contrast blue badge (`#2563EB`).

### Nice-to-Have Items (Saved for Future Iterations)
1. Add dark mode toggle switch.
2. Add interactive search filtering across the 30,000 CSV rows.

---

## 4. Live Verification Evidence

Both **Must-Fix** items were updated in `docs/index.html`, committed, and verified live on GitHub Pages at [https://manthansingh26.github.io/FLY_Manthan/](https://manthansingh26.github.io/FLY_Manthan/).
