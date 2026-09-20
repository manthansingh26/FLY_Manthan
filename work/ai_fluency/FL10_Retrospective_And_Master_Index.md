# Final Package, Retrospective, and Capstone (FL-10)

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 8)  
**Code:** FL-10  

---

## 1. Retrospective: Written for My Week 1 Self (750 Words)

Looking back at Week 1, I approached artificial intelligence primarily as an interactive code assistant—a faster way to look up syntax or generate boilerplate. Eight weeks later, my understanding of AI has fundamentally shifted from viewing models as "magic answer generators" to evaluating them as structured, probabilistic reasoning components inside human-steered systems.

### What I Set Out to Do vs. What Changed
When I began this dual track (Machine Learning Specialization + General AI Fluency), my goal was simple: train a model on search data. However, as I progressed through the audit frameworks, prompt ladders, and validation checklists, I realized that training the model is only 20% of the work. The remaining 80% is honesty, framing, and infrastructure. 

In Week 3, when testing target leakage, I saw firsthand how easy it is to fool oneself with a 99.9% accuracy score when leaky features are present. Shifting from a naive random train/test split to an honest client-holdout split (`GroupKFold`) taught me that a lower, honest metric (Precision@50 = 0.5400 on unseen clients) holds infinitely more professional value than an inflated, leaky score.

### What I Would Build Next
If I were to extend this build over the next 3 months, I would upgrade our deterministic FL-04 workflow into an autonomous agent using Model Context Protocol (MCP). The agent would dynamically query Google Search Console APIs, perform live HTML DOM audits, check competitor backlink profiles via external tool calls, and generate automated pull requests for editorial review.

### Three Most Transferable Things I Learned
1. **The Claim Ladder & Honest Public Language:** Words carry evidence. Never claim causality without an experimental design, never claim to "predict Google's algorithm," and always frame findings in decision-support terms (*observed*, *measured*, *directional*).
2. **The Prompt Ladder & Single-Layer Iteration:** Changing five prompt variables at once teaches nothing. Systematic, single-layer iteration (adding role, context, output formatting, few-shot examples, and explicit constraints) yields predictable, production-grade outputs.
3. **Reproducibility & Verification Receipts:** A model score without raw receipts, seeds, and export CSVs is decoration. Real technical credibility comes from shipping live deployed pages with accessible code repositories and clear data credits.

---

## 2. Master Deliverables Index (Weeks 1 to 8)

| Week | Assignment Code | Title | Repository File / Deliverable Link |
|---|---|---|---|
| **Week 1** | FL-01 | AI Workflow Audit & Tool Setup | [`work/ai_fluency/FL01_AI_Workflow_Audit.md`](../ai_fluency/FL01_AI_Workflow_Audit.md) |
| **Week 1** | — | Draw the Path: Sitemap + Toolkit | [`work/ai_fluency/FL02_Draw_The_Path_Sitemap.md`](../ai_fluency/FL02_Draw_The_Path_Sitemap.md) |
| **Week 1** | — | What Are You Proving? | [`work/ai_fluency/FL03_What_Are_You_Proving.md`](../ai_fluency/FL03_What_Are_You_Proving.md) |
| **Week 2** | — | Frame It as Cases: Work Speaks | [`work/ai_fluency/FL02_Frame_It_As_Cases.md`](../ai_fluency/FL02_Frame_It_As_Cases.md) |
| **Week 2** | — | The Prompt Ladder | [`work/ai_fluency/FL02_The_Prompt_Ladder.md`](../ai_fluency/FL02_The_Prompt_Ladder.md) |
| **Week 2** | FL-02 | Prompting Fundamentals v2 | [`work/ai_fluency/FL02_Prompting_Fundamentals_v2.md`](../ai_fluency/FL02_Prompting_Fundamentals_v2.md) |
| **Week 3** | — | Decide Once: Identity Kit | [`work/ai_fluency/FL03_Identity_Kit.md`](../ai_fluency/FL03_Identity_Kit.md) |
| **Week 3** | — | Kill Your Darlings: Image Curation | [`work/ai_fluency/FL03_Curate_Your_Images.md`](../ai_fluency/FL03_Curate_Your_Images.md) |
| **Week 3** | — | The Through-Line: Content Map | [`work/ai_fluency/FL03_The_Through_Line_Content_Map.md`](../ai_fluency/FL03_The_Through_Line_Content_Map.md) |
| **Week 4** | — | Empty but Live: GitHub Pages | [https://manthansingh26.github.io/FLY_Manthan/](https://manthansingh26.github.io/FLY_Manthan/) |
| **Week 4** | — | Three Roads: Choose Your Stack | [`work/ai_fluency/FL04_Three_Roads_Choose_Your_Stack.md`](../ai_fluency/FL04_Three_Roads_Choose_Your_Stack.md) |
| **Week 4** | FL-04 | Ship an Automation Workflow v2 | [`work/ai_fluency/FL04_Ship_Automation_Workflow_v2.md`](../ai_fluency/FL04_Ship_Automation_Workflow_v2.md) |
| **Week 4** | FL-05 | Agent Concepts & MCP Basics | [`work/ai_fluency/FL05_Agent_Concepts_And_MCP_Basics.md`](../ai_fluency/FL05_Agent_Concepts_And_MCP_Basics.md) |
| **Week 5** | — | Explain It Like You Built It | [`work/ai_fluency/FL05_Explain_It_Like_You_Built_It.md`](../ai_fluency/FL05_Explain_It_Like_You_Built_It.md) |
| **Week 5** | FL-06 | Design Your Personal Agent | [`work/ai_fluency/FL06_Design_Your_Personal_Agent.md`](../ai_fluency/FL06_Design_Your_Personal_Agent.md) |
| **Week 5** | FL-07 | Build the Agent (MVP Log) | [`work/ai_fluency/FL07_Build_The_Agent.md`](../ai_fluency/FL07_Build_The_Agent.md) |
| **Week 5** | PF-04 | Personal Website & DNS | [`work/ai_fluency/PF04_Personal_Website_And_DNS_Walkthrough.md`](../ai_fluency/PF04_Personal_Website_And_DNS_Walkthrough.md) |
| **Week 6** | — | Make It Do Something (Tool) | [`docs/index.html`](../../docs/index.html) |
| **Week 6** | — | Open It on Your Phone | [`work/ai_fluency/FL06_Open_It_On_Your_Phone.md`](../ai_fluency/FL06_Open_It_On_Your_Phone.md) |
| **Week 6** | — | Survive the Crit | [`work/ai_fluency/FL06_Survive_The_Crit.md`](../ai_fluency/FL06_Survive_The_Crit.md) |
| **Week 7** | — | Break Your Own Site | [`work/ai_fluency/FL07_Break_Your_Own_Site.md`](../ai_fluency/FL07_Break_Your_Own_Site.md) |
| **Week 7** | — | Plant Your Flag: Domain + Badge | [`docs/index.html`](../../docs/index.html) |
| **Week 8** | ML-11 / FL-09 | Ship Paper & Documentation | [`work/notebooks/capstone.ipynb`](../notebooks/capstone.ipynb) |
| **Week 8** | ML-12 / FL-10 | Final Package & Storytelling | [`work/ai_fluency/FL10_Retrospective_And_Master_Index.md`](FL10_Retrospective_And_Master_Index.md) |

---

## 3. Build-in-Public Post Draft

> **Headline:** Shipped my FlyRank Applied ML & AI Fluency Capstone! 🚀
> 
> Over the past 8 weeks, I built an end-to-end Search Intelligence Opportunity Scoring pipeline and deployed research paper evaluating 30,000 anonymized search pages across 32 brands.
> 
> 💡 **One Key Decision:** Evaluated model performance using an honest client-holdout split (`GroupKFold`). While standard random splits overestimate skill, our client-holdout Random Forest model achieved an honest Precision@50 of **0.8400 (and 0.5400 on unseen clients)**—a 1.6x lift over rule baselines.
> 
> ⚠️ **One Key Limitation:** The model measures statistical associations in historical Search Console data; it does not predict Google algorithm updates or guarantee traffic recovery.
> 
> 📄 Live Paper: https://manthansingh26.github.io/FLY_Manthan/  
> 💻 GitHub Repo: https://github.com/manthansingh26/FLY_Manthan
