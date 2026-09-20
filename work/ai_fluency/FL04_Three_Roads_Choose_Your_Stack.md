# Three Roads: Choose Your Stack with AI

**Author:** Manthan Singh  
**Track:** General AI Fluency (Week 4)  

---

## 1. Constraint Input Definition

1. **Cost Constraint:** 100% Free tier (Zero hosting or database maintenance costs).
2. **Skill Level:** Advanced Applied ML & Data Engineering (Comfortable with HTML/CSS, Python pipelines, static site hosting).
3. **Portfolio Functionality:** Display long-form scientific paper, interactive SVG/PNG charts, benchmark tables, and code receipts.
4. **Dynamic Needs:** No server-side database required yet; static HTML with embedded JSON metrics receipts satisfies all user needs.

---

## 2. Comparison of Three Stack Options

| Option | Technology Stack | Hosting & Backend | Trade-offs & Maintenance |
|---|---|---|---|
| **Road 1 (Simplest)** | **Vanilla HTML5 + CSS3 + GitHub Pages** | GitHub Pages (`/docs` folder), No Backend | **Pros:** Zero build tools, instantaneous load times, 100% free, 0% maintenance. <br>**Cons:** Manual HTML structure formatting. |
| **Road 2 (Moderate)** | **Hugo / Astro Static Site Generator** | Netlify / Vercel Free Tier, Markdown Content | **Pros:** Templating engine, component reuse. <br>**Cons:** Requires npm/build step configuration and package updates. |
| **Road 3 (Powerful)** | **Next.js 14 + Tailwind CSS + Vercel** | Vercel Free Tier + Serverless API Routes | **Pros:** Full dynamic React rendering, serverless endpoints. <br>**Cons:** High maintenance overhead, potential cold starts, unnecessary for static paper receipts. |

---

## 3. Chosen Stack Rationale

> **Selected Stack:** **Road 1 — Vanilla HTML5 + CSS3 hosted on GitHub Pages (`/docs` folder).**

### Why Road 1 Was Chosen
1. **Maintenance & Longevity:** A static single-file HTML document (`docs/index.html`) will never break due to package deprecation or framework updates.
2. **Instant Performance & Zero Cost:** Serves directly from GitHub's CDN at zero cost with sub-second page load times.
3. **Perfect Fit for Purpose:** The primary goal is displaying an academic research paper with tables and figures. A static web document frames the research without adding unnecessary JavaScript bundle size.
