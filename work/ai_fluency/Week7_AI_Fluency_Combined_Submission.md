# General AI Fluency — Week 7 Deliverables

This document contains both completed deliverables for Week 7 of General AI Fluency:
1. **Break Your Own Site:** Edge-Case Hardening & Triage Log
2. **Plant Your Flag:** Live Domain, SEO Meta, & FlyRank Badge Installation

---

# Break Your Own Site

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 7)  

---

## 1. Edge-Case Hardening & Stress Test Log

The live portfolio and calculator tool (`docs/index.html`) were stress-tested across non-happy-path inputs and browser environments.

| Test Case / Edge Scenario | Observed Behavior (Before) | Fix Applied (After) | Status |
|---|---|---|---|
| **Negative Inputs** | Form allowed negative numbers (`-500` impressions, `-50` days). | Added input `min="0"` constraints & JavaScript `Math.max(0, val)` validation. | **FIXED** |
| **Empty / NaN Input** | Submitting empty form produced `NaN` score. | Added default fallback `|| 0` parsing to handle empty fields gracefully. | **FIXED** |
| **Rapid Double Click** | Clicking button rapidly caused duplicated UI state. | Added button debounce & instantaneous state lock during calculations. | **FIXED** |
| **SEO & Open Graph Meta** | Shared links lacked social preview card image and description. | Added full Open Graph (`og:title`, `og:image`, `og:description`) & Twitter Card tags. | **FIXED** |

---

## 2. Triage Matrix: Fix-Now vs. Known Limitations

### Fix-Now Items (All Addressed)
1. **Input Validation:** Enforced strict non-negative constraints on all interactive form fields.
2. **Open Graph Social Share Preview:** Embedded Open Graph meta tags and default preview image (`work/figures/action_mix.png`).
3. **SVG Favicon:** Added light-weight SVG vector favicon for browser tab identification.

### Known Limitations (Documented Design Boundaries)
1. **Static Pre-computed Models:** The live calculator uses the client-side transparent baseline scoring formula ($score = 2 	imes stale + 3 	imes visible + \ln(1 + imp)$). Full Random Forest model inference requires local Python execution.
2. **Client-Side Storage:** User inputs are processed in-memory during the session and are not stored in a persistent database.


---

# Plant Your Flag: Domain + Badge

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 7)  

---

## 1. Deployed Production URL & HTTPS Verification

* **Live Custom/Subdomain Address:** [https://manthansingh26.github.io/FLY_Manthan/](https://manthansingh26.github.io/FLY_Manthan/)
* **HTTPS Security:** Verified SSL certificate active (2048-bit RSA encryption, forced HTTPS redirect enabled).
* **Repository Source:** Branch `main`, directory `/docs`.

---

## 2. Social Preview, Favicon, & Title Verification

* **Page Title:** `Applied Search Intelligence: Content Opportunity Scoring — FlyRank ML Research`
* **Favicon:** Vector SVG favicon active on browser tab.
* **Open Graph Preview Tags:**
  ```html
  <meta property="og:title" content="Applied Search Intelligence: Content Opportunity Scoring">
  <meta property="og:description" content="A decision-support ML pipeline evaluating 30,000 search pages to predict content decay. Random Forest model achieves 0.8400 Precision@50 under honest client-holdout validation.">
  <meta property="og:image" content="https://manthansingh26.github.io/FLY_Manthan/work/figures/action_mix.png">
  ```

---

## 3. FlyRank Graduate Badge Installation

* **Badge Status:** Installed in the site footer of `docs/index.html`.
* **Verification Target:** Links to [FlyRank.ai Verification](https://internship-badge.netlify.app/) and program credentials.

