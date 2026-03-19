# SIGFA — Base44 Deployment Refinement Prompts

Use these after the initial Base44 build to polish each section. Copy and paste each prompt directly into the Base44 chat.

---

## Prompt A — Landing Page

```
Polish the landing page. Use dark navy (#0B1F3A) background with emerald (#0D9B6C) and gold (#D4A843) accents. Hero headline: "AI-Powered Infrastructure for Social Impact Funding". Add 3 role cards for CIC, NHS and Corporate. Stats bar: £1M+ Funding Mobilised | 100k+ UK CICs | £180bn NHS Budget | 30% Reach Growth. Add a proof section referencing the CAHN pilot and £1M result. Make it feel institutional and enterprise-grade.
```

---

## Prompt B — Funding Fit Engine

```
Build the Funding Fit Engine as a 3-step wizard. Step 1: organisation details form. Step 2: compliance checklist (4 toggleable items: filed accounts, governance, impact data, NHS contact). Step 3: results page with 5 circular score rings (Overall, Compliance, Impact, NHS Alignment, ESG Ready), 3 funding matches with progress bars and fit %, gaps column in red, quick wins in green, and AI summary. Save assessment results to database.
```

---

## Prompt C — Health Economics Engine

```
Build the impact calculator with 4 sliders: Beneficiaries Reached (0–5000), Programme Cost £ (£10k–£1M), Emergency Admissions Avoided (0–500), Additional Screenings per Month (0–500). Show 3 live KPI cards: NHS Cost Avoidance = (admissions × £2,800) + (screenings × £180 × 12); ROI % = ((saving − cost) / cost × 100); QALYs = admissions × 0.15 + screenings × 0.05. Add bar chart showing cost vs savings breakdown.
```

---

## Prompt D — Corporate ESG Dashboard

```
Build the corporate dashboard with 4 KPI cards (total capital deployed, active programmes, average impact score, total cost avoidance generated). Add a radar chart showing SDG alignment across SDG 3, 10, 17, 8 and 11. Add a pie chart showing portfolio breakdown by sector. Add a portfolio table with columns: Programme Name, CIC, Sector, Geography, Capital Deployed, Impact Score, SDG Tags, Status.
```

---

## Prompt E — Design System

```
Apply SIGFA brand throughout the entire app. Dark navy (#0B1F3A) page backgrounds, emerald (#0D9B6C) for primary accents and CTAs, gold (#D4A843) for KPI values and secondary accents, slate (#8BA3BE) for secondary text. Georgia/serif for all headings. SIGFA logo: letter "S" in a rounded emerald square + bold wordmark. Make all dashboards feel professional and institutional — suitable for NHS procurement teams, investors and visa assessors.
```

---

## API setup in Base44

1. Go to app Settings → Secrets tab
2. Add key: `ANTHROPIC_API_KEY` → value: your key from [console.anthropic.com](https://console.anthropic.com)
3. Model to use in all AI features: `claude-sonnet-4-20250514`
4. AI context to embed in all Base44 prompts:

```
SIGFA operates in the UK social impact and public health sector. Generate professional, evidence-based content using NHS/public health terminology: health equity, cost avoidance, QALYs, ICBs, prevention mandate, Theory of Change, DSP Toolkit, ESG alignment, SDGs. Tone: institutional but accessible. All monetary values in GBP (£).
```

---

*SIGFA · Fruitful Bough · 2025–2026*
