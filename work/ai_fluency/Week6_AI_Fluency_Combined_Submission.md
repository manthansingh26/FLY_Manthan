# General AI Fluency — Week 6 Deliverables

This document contains all three completed deliverables for Week 6 of General AI Fluency:
1. **Make It Do Something:** Live Interactive Feature & Backend Explainer
2. **Open It on Your Phone:** Mobile Responsiveness & Accessibility Fix Log
3. **Survive the Crit:** Peer Design Review & Live Fix Evidence

---

# Make It Do Something

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 6)  

---

## 1. Deployed Interactive Feature Specification

* **Interactive Feature:** *Live Content Opportunity Score & Action Priority Calculator*
* **Live Public URL:** [https://manthansingh26.github.io/FLY_Manthan/](https://manthansingh26.github.io/FLY_Manthan/)
* **Functionality:** Visitors can input 90-day Search Console impressions, days since last update, and current CTR to calculate an instant Opportunity Score, recommended action category (`HIGH_PRIORITY_REFRESH`, `RE_OPTIMIZE_CTR`, etc.), and human-readable reason code directly on the live page.

---

## 2. Plain-Words Backend & Data Flow Explainer

### What is a Backend?
A **backend** is the engine room of a digital application. While the frontend is the visual layout you see in your browser, the backend processes logic, queries databases, and calculates outputs behind the scenes.

### Data Flow in Our Interactive Tool
1. **User Input (Frontend):** A visitor enters three numbers into the live calculator interface (`impressions_90d`, `days_since_last_update`, `ctr`).
2. **Data Pipeline & Calculation:** The JavaScript event listener intercepts the form submission, applies our non-leaky mathematical scoring formula:
   $$\text{Score} = (\text{stale} \times 2.0) + (\text{high\_imp} \times 3.0) + \ln(1 + \text{impressions})$$
3. **Dynamic UI Render (Response):** The system returns the calculated score, assigns the appropriate Action Badge, and displays actionable editorial advice without requiring a full page refresh.

---

## 3. Free Tier Hosting & End-to-End Verification

* **Hosting:** GitHub Pages Free Tier.
* **Test Verification:** Verified input form execution live on desktop and mobile browsers.


---

# Open It on Your Phone

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 6)  

---

## 1. Mobile Responsiveness Audit & Fix Log

The portfolio and research paper (`docs/index.html`) were audited on a real smartphone (iOS Safari & Android Chrome) and across simulated viewport widths (375px, 768px, 1024px, 1440px).

| Audit Category | Issue Found (Before) | Fix Applied (After) | Verification Result |
|---|---|---|---|
| **Viewport & Scaling** | Table columns spilled past screen edge on 375px mobile width. | Added CSS `overflow-x: auto;` wrapper around all metric tables. | Tables scroll smoothly horizontally on mobile without breaking page width. |
| **Tap Targets** | Navigation links and buttons were 32px height (hard to tap on mobile). | Set minimum touch target height to `48px` with `padding: 12px 18px`. | All links and CTAs pass Google Mobile Accessibility guidelines. |
| **Typography & Contrast** | Sub-headers were 14px (too small on high-DPI phone screens). | Standardized body font to `16px` (`1.0rem`) and line height to `1.7`. | Crisp, highly legible text across dark and light viewports. |
| **Image Optimization** | `action_mix.png` chart scaled fixed width. | Set `img { max-width: 100%; height: auto; }`. | Charts auto-scale perfectly to phone screen width. |

---

## 2. Link & Performance Audit

* **Link Check:** All 12 hyperlinks (GitHub repo, live paper, FlyRank data credit, raw metrics JSONs) verified working with zero 404 errors.
* **Image Compression:** `action_mix.png` optimized to under 40 KB for instantaneous mobile loading over 4G connections.


---

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

