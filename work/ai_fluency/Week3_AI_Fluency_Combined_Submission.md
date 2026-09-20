# General AI Fluency — Week 3 Deliverables

This document contains all four completed deliverables for Week 3 of General AI Fluency:
1. **Consistency, Not Talent:** Design & Framing Philosophy
2. **FL03 Identity Kit:** Fonts, Palette, Logo, & Claude Style Note
3. **Curate Your Images:** Image Inventory & Rejection Critiques
4. **The Through-Line:** One-Line Claim, Content Map, & CTAs

---

# Decide Once: Build Your Identity Kit

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 3)  

---

## 1. Visual Design & Framing Philosophy

The design of a portfolio exists to frame the technical proof, never to upstage it. Clean typography, restrained spacing, and a quiet color palette allow real code receipts, benchmark metrics, and paper outputs to be the loudest element on the page.

---

## 2. Typography Choices

* **Heading Font:** `Inter` (Clean, modern sans-serif for high legibility on titles).
* **Body Font:** `-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto` (System font stack for instantaneous rendering and native performance).
* **Code / Monospace Font:** `JetBrains Mono` / `Fira Code` (For code blocks and metric receipts).

---

## 3. Restrained Color Palette

| Usage | Color Name | Hex Code | Visual Rationale |
|---|---|---|---|
| **Background** | Slate Light Background | `#F8FAFC` | Near-white slate background to reduce eye strain and maintain focus. |
| **Primary Text** | Slate Dark Text | `#0F172A` | Near-black high-contrast text for dark-mode-equivalent crispness. |
| **Primary Brand** | Slate Header / Card | `#1E293B` | Deep slate for headers, container borders, and structural cards. |
| **Accent / Action** | Royal Tech Blue | `#2563EB` | Vibrant blue used strictly for primary CTAs, links, and high-priority metrics. |
| **Accent Light** | Soft Blue Highlight | `#DBEAFE` | Soft background fill for table highlights and badge indicators. |

---

## 4. Logo & Favicon Design

* **Logo Monogram:** `[MS]` set in **Inter Bold** (`#0F172A`) with a subtle `2563EB` accent period: **MS.**
* **Favicon:** 32x32 SVG vector icon featuring a clean blue terminal icon `>_` set on a dark slate background (`#0F172A`).

---

## 5. Standing Claude Project Style Note

> **Style Note:**
> *"Use Inter for headings and system sans-serif for body text. Palette: `#F8FAFC` background, `#0F172A` body text, `#1E293B` container cards, and `#2563EB` accent blue for CTAs. Maintain a clean, academic, decision-support mood that frames technical work without decorative fluff."*


---

# Kill Your Darlings: Curate Your Images

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 3)  

---

## 1. Required Portfolio Image Inventory

| Image Target | Type | Source | Purpose |
|---|---|---|---|
| **Author Headshot** | Real Photo | Professional High-Res Photo | Establishes genuine personal identity and accountability. |
| **GitHub Pages Research Paper** | Real Capture | Full-page browser screenshot of `index.html` | Demonstrates deployed, live capstone paper. |
| **Precision@50 Model Benchmark Chart** | Real Export | `work/figures/action_mix.png` (Matplotlib export) | Proves model vs baseline performance lift. |
| **DuckDB / Python Terminal Receipts** | Real Capture | Screenshot of clean terminal execution | Validates real-world code execution and local environment. |
| **Background Texture / Card Accent** | AI Generated | Midjourney / DALL-E 3 (Consistent Slate Prompt) | Connective visual accent for hero background. |

---

## 2. AI Image Generation Prompt & Consistency Standard

To ensure connective visual elements remain consistent with the Identity Kit:

* **Consistent Generation Prompt:**
  > *"Minimalist abstract slate background, deep blue subtle gradient geometric lines, quiet tech aesthetic, high contrast, clean vector style, dark slate #0F172A and royal blue #2563EB --no noise, --no photorealistic text"*

---

## 3. Image Discernment & Rejection Notes (The Critique)

* **Rejection Case 1: AI-Generated 'Futuristic Cyber Dashboard'**
  * *Reason for Rejection:* AI produced a glowing futuristic holographic dashboard with fake 3D charts. 
  * *Discernment Rationale:* Fake AI-generated dashboards destroy credibility. Replacing a real browser screenshot of `docs/index.html` with a glowing AI mockup looks amateur. Real screenshots of actual running code beat AI stand-ins every single time.
* **Rejection Case 2: AI-Generated Photorealistic Stock Office Photo**
  * *Reason for Rejection:* AI generated a generic stock photo of a person at a laptop.
  * *Discernment Rationale:* Stock photos feel artificial and insincere. Using a real professional photo of myself builds genuine trust with hiring managers.


---

# The Through-Line: Map Content & CTAs

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 3)  

---

## 1. The One-Line Claim

> **One-Line Claim:** *"I design and evaluate leakage-free machine learning scoring pipelines that turn raw search data into prioritized, human-reviewed editorial action."*

---

## 2. Page-by-Page Content & CTA Map

```text
[ Hero Section ] ──────► [ Case Study: Search Intelligence ] ──────► [ Action Playbook & Contact ]
  Claim: Leakage-free ML     Lead Work: Random Forest Model            CTA: View GitHub Repo /
  CTA: Read Case Study       CTA: Inspect Benchmark Metrics                 Schedule Technical Call
```

### Page 1: Hero / Landing Section
* **Section Order:**
  1. Header Bar with Monogram `MS.` & Navigation.
  2. Headline Statement: The One-Line Claim.
  3. Executive Sub-headline: 30k Dataset, GroupKFold Split, 1.6x Precision Lift over Baseline.
* **Call to Action (CTA):** Primary Button: `[Read Capstone Research Paper]` (Scrolls to Case Study).

### Page 2: Case Study — Applied Search Intelligence
* **Section Order:**
  1. Problem Statement: Content decay & manual review bottlenecks.
  2. Data Safety & Leakage Audit: Target leakage exclusion rules.
  3. Empirical Benchmark Table: Baseline vs Logistic Regression vs Decision Tree vs Random Forest (Precision@50 = 0.8400).
  4. Feature Importance Ranking: `days_with_impressions` (20.2%), `impressions_per_day` (18.9%).
* **Call to Action (CTA):** Secondary Link: `[Inspect Reproducible Receipts on GitHub]`.

### Page 3: Content Action Playbook & Final Contact
* **Section Order:**
  1. Playbook Action Matrix: `RE_OPTIMIZE_CTR`, `HIGH_PRIORITY_REFRESH`, `CONTENT_EXPANSION`.
  2. Strict No-Go Automation List: No auto-deletions, no unverified AI text generation.
  3. Reproducibility & Data Credit: FlyRank.ai credit & license.
* **Call to Action (CTA):** Primary Action: `[Contact for ML Engineering Roles / View GitHub Repo]`.

---

## 3. Proof Gathering Checklist

- [x] Live Deployed GitHub Pages Research Paper (`https://manthansingh26.github.io/FLY_Manthan/`)
- [x] Reproducibility Receipts (`work/outputs/action_playbook_metrics.json`)
- [x] High-Res Matplotlib Export (`work/figures/action_mix.png`)
- [x] Clean Public Repository (`https://github.com/manthansingh26/FLY_Manthan`)
- [x] Professional Author Headshot

