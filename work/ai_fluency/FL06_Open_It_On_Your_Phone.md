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
