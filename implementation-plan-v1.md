# REPARATIONS DIGITAL ARCHIVE — Implementation Plan v1
## Suggestion for Executor Team | Not Prescriptive | Subject to Independent Recon

---

## THESIS

The mission is to build a **public-facing digital archive** that serves as the definitive catalogue of reparations studies, reports, and documents — organized by date, location, and type — with direct PDF/HTML download links. This is a **research infrastructure play**, not a blog. The site must be fast, searchable, and credible.

---

## RECOMMENDED ARCHITECTURE

### Option A (Recommended): Static Site + Headless CMS
```
Frontend: Hugo or Astro (static, fast, free hosting)
Data: YAML/JSON files (version-controlled, GitHub-backed)
Hosting: GitHub Pages or Cloudflare Pages (free, global CDN)
Search: Pagefind (client-side, no server needed)
```

**Why:** Zero maintenance cost, version-controlled, auditable, fast globally. No database to secure. Can be deployed in 1-2 days.

### Option B: WordPress + Archive Plugin
**Why NOT:** Overkill, security burden, ongoing maintenance cost.

### Option C: Custom Web App (React/Next.js)
**Why NOT:** Premature. Build static first, enhance later if needed.

---

## SITE STRUCTURE

```
reparations-archive.org (or chosen domain)
├── /
│   └── Featured stats (X documents, Y countries, Z time span)
├── /studies/
│   └── Filterable grid: all documents
├── /by-date/
│   └── Timeline view (1865 → 2026)
├── /by-location/
│   └── Map + list (country → state → city)
├── /by-type/
│   ├── Government Reports
│   ├── Academic Studies
│   ├── Advocacy Documents
│   ├── International
│   ├── Media Statements
│   └── Legislation/Ordinances
├── /callie-house/
│   └── Dedicated section for Field Order 15 + derivatives
├── /missing/
│   └── "Help us find these" — list of known gaps
├── /about/
│   └── Methodology, sources, contribution guidelines
└── /api/
    └── JSON dump of entire catalogue (for researchers)
```

---

## DATA SCHEMA (Per Entry)

```yaml
id: ca-ab3121-full
title: "California Task Force to Study and Develop Reparation Proposals — Full Report"
source: "California Department of Justice"
url: "https://oag.ca.gov/system/files/media/full-ca-reparations.pdf"
format: pdf
date: 2023-06-01
location:
  country: USA
  state: California
  city: null
type: government-report
verified: true
file_size: "estimated"
pages: 40
language: en
tags: [ab3121, state-level, comprehensive, eligibility, remedies]
description: "Comprehensive state-mandated reparations study with 40+ chapters covering historical harms, eligibility criteria, and proposed remedies for African Americans in California."
```

---

## PHASED EXECUTION PLAN

### Phase 1: Foundation (Sprint 1 — 3 days)
1. Set up Hugo/Astro project on GitHub
2. Create data schema and import the 47 verified documents from this audit
3. Build basic listing page with search
4. Deploy to GitHub Pages
5. **Gate:** Site is live, searchable, all verified docs accessible

### Phase 2: Organization (Sprint 2 — 3 days)
1. Implement date/timeline view
2. Implement location/map view
3. Implement type-based filtering
4. Add download counters and click tracking
5. **Gate:** All three navigation paths work

### Phase 3: Gap Filling (Sprint 3 — 5 days)
1. Recon the 25 "unknown unknowns" listed in audit
2. Contact city/county offices for missing PDFs
3. File FOIA requests for unreleased reports
4. Reach out to academic authors for PDFs
5. **Gate:** 60+ documents catalogued

### Phase 4: Enhancement (Sprint 4 — 3 days)
1. Add document preview thumbnails
2. Implement full-text search within PDFs (if feasible)
3. Add "contribute a document" submission form
4. Create API endpoint
5. **Gate:** Site is feature-complete

---

## CRITICAL DESIGN DECISIONS

| Decision | Recommendation | Rationale |
|----------|---------------|-----------|
| Domain | reparations-archive.org or similar | Neutral, descriptive, memorable |
| Color | Dark theme, high contrast | Professional, accessible, print-friendly |
| PDF Handling | Direct download + Google Docs viewer fallback | Some users can't open PDFs in-browser |
| Mobile | Mobile-first design | 60%+ of users will be on mobile |
| Accessibility | WCAG 2.1 AA | Government documents must be accessible |
| Analytics | Plausible or GoatCounter (privacy-first) | No Google Analytics — this is research infrastructure |
| Multilingual | English v1, add ES/FR in v2 | Caribbean and African diaspora speak these languages |
| Rate Limiting | None on downloads | Remove friction — the goal is access |

---

## ANTI-PATTERNS TO AVOID

1. **Don't build a database.** Static files are enough. Databases need maintenance.
2. **Don't embed PDFs in the page.** Link to them. Let users download.
3. **Don't add comments/discussion.** This is an archive, not social media.
4. **Don't make it a SPA.** Server-render everything. Speed > interactivity.
5. **Don't gate any documents.** No login, no email, no paywall.
6. **Don't editorialize.** Present documents neutrally. Let the content speak.
7. **Don't ignore non-English sources.** Flag them for Phase 2 translation.

---

## ACCOUNTABILITY FRAMEWORK

| Role | Responsibility |
|------|---------------|
| **Research Lead** | Verify every PDF link is accessible; flag dead links |
| **Engineering Lead** | Build the site; ensure uptime; backup strategy |
| **Content Lead** | Write descriptions; ensure neutral tone; tag accurately |
| **QA Lead** | Test on 5 browsers; verify all downloads work; check accessibility |
| **Israel/Hermie** | Final review; strategic alignment; launch approval |

---

## BUDGET ESTIMATE

| Item | Cost |
|------|------|
| Domain (1 year) | $12 |
| Hosting | $0 (GitHub Pages / CF Pages) |
| SSL | $0 (included) |
| Design | $0 (use open source theme) |
| Labor | Team time only |
| **Total** | **$12/year** |

---

## SUCCESS CRITERIA

- [ ] All 47 verified documents accessible within 2 clicks from homepage
- [ ] Site loads in <2 seconds on 3G
- [ ] Works on Safari, Chrome, Firefox, mobile
- [ ] Search returns relevant results
- [ ] All download links return 200
- [ ] At least 3 "unknown unknowns" resolved during execution
- [ ] Code is open source on GitHub
- [ ] Can be maintained by anyone with basic Git knowledge

---

## NEXT STEPS

1. **Domain decision** — register the domain
2. **Team assignment** — who owns which phase
3. **Recon verification** — team independently verifies my 47 findings before building
4. **Kickoff** — start Phase 1

---

*This plan is a suggestion for inspiration. The executing team should conduct their own independent recon, verify all findings, and adapt this plan to their capabilities and findings. Accountability is everyone's responsibility.*
