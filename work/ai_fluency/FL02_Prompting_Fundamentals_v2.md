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
