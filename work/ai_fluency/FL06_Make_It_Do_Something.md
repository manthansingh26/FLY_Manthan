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
