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
