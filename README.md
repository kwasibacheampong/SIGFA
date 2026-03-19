# SIGFA

### Social Impact Growth & Funding Accelerator

[![Status](https://img.shields.io/badge/Status-MVP%20Live-brightgreen?style=flat-square)]()
[![Pilot](https://img.shields.io/badge/Pilot-CAHN%20%C2%A31M%2B%20Secured-gold?style=flat-square)]()
[![Built With](https://img.shields.io/badge/Intelligence-Claude%20API-FF6B35?style=flat-square)](https://anthropic.com)
[![Platform](https://img.shields.io/badge/Platform-Base44-0099BB?style=flat-square)]()
[![By](https://img.shields.io/badge/Built%20by-Fruitful%20Bough-C9A84C?style=flat-square)](https://github.com/kwasibacheampong)

> **[Fruitful Bough](https://github.com/kwasibacheampong)** · Strategic architect of measurable value. Not advisory — structural. Not consultancy — engineering.

---

## Proven before it was built

SIGFA was not designed in the abstract. The methodology was first executed manually at the **Caribbean & African Health Network (CAHN)** between December 2023 and June 2024.

Results independently verifiable:

| Outcome | Detail |
|---------|--------|
| **£1M+** public funding secured | HIV and sexual health delivery across Lambeth, Southwark and Lewisham |
| **30%** increase in programme reach | Across target communities |
| **NHS partnership formalised** | Borough public health teams across three London ICBs |
| **Statutory compliance reporting embedded** | Outcome modelling across all programmes |

SIGFA digitises and scales what was built and delivered manually — making institutional-grade funding infrastructure accessible to all UK CICs, not just those with in-house expertise.

---

## What this is

SIGFA is a multi-sided AI-powered platform that bridges the structural funding gap between three groups that should be working together — and largely aren't:

```
UK Community Interest Companies (CICs)
            ↕
    NHS Trusts / ICBs
            ↕
  Corporate / Pharma ESG Capital
```

**The problem:** 100,000+ UK CICs are eligible for NHS and ESG funding but lack the institutional infrastructure to identify, pursue, and win it. NHS teams lack a discovery layer for CIC partners. Corporate ESG capital lacks verified impact routing.

**The solution:** A three-sided platform that gives each party what they need — and creates the connections the sector is missing.

---

## Three user sides

| User | Who they are | What SIGFA does for them |
|------|-------------|--------------------------|
| **CICs / Community Health Orgs** | Community Interest Companies, charities, social enterprises | Funding fit scoring, AI bid generation, NHS alignment analysis, impact modelling |
| **NHS Trusts / ICBs** | NHS Integrated Care Boards, public health teams | CIC partner discovery with readiness scores, health economics data, MoU tools |
| **Corporate / Pharma ESG** | Corporate ESG/CSR teams, impact investors | Portfolio dashboard, SDG mapping, risk scoring, outcome verification |

---

## Architecture

SIGFA is built on two integrated layers:

| Layer | Technology | Role |
|-------|-----------|------|
| **Intelligence** | Claude API (Anthropic) | Funding Fit Engine, Bid Builder, Impact Narrative Generator |
| **Application** | Base44 | Full-stack app shell, data model, dashboards, auth, scheduling, file storage |

Claude operates as a structured output engine throughout — not a chatbot, but a typed JSON machine producing scored assessments, bid drafts, and impact narratives at each pipeline stage.

---

## Platform modules

### CIC Portal
| Page | Purpose |
|------|---------|
| **Funding Fit Engine** | 3-step wizard → AI-scored readiness across 5 dimensions with funding matches |
| **Bid Builder** | AI-generated institutional funding bids using NHS/public health terminology |
| **Impact Engine** | Live health economics calculator: NHS cost avoidance, ROI, QALY modelling |
| **NHS Partnership Builder** | MoU templates, shared KPI entry, partnership status tracker |

### NHS Portal
| Page | Purpose |
|------|---------|
| **CIC Discovery** | Searchable directory with readiness and NHS alignment scores |
| **Partnerships** | Active partnership management, shared KPI dashboards |

### Corporate ESG Portal
| Page | Purpose |
|------|---------|
| **Portfolio Dashboard** | Total deployed, SDG radar chart, sector breakdown |
| **ESG Explorer** | Browse CICs by SDG, geography, and impact score |

---

## AI features — Claude API

Three structured Claude API prompts power the intelligence layer. Each returns validated JSON.

### 1. Funding Fit Engine
**Triggered:** When a CIC completes the Step 2 assessment checklist  
**Output:** `overall_readiness_score`, `compliance_score`, `impact_score`, `nhs_alignment_score`, `esg_score`, `gaps[3]`, `quick_wins[3]`, `funding_matches[{name, amount, fit%}]`, `summary`

### 2. Bid Builder
**Triggered:** When a CIC clicks "Generate Bid" for a funding stream  
**Output:** 350-word institutional funding bid executive summary in NHS/public health register — saved to `FUNDING_BID` table  
**Language context:** Health equity, cost avoidance, QALYs, ICBs, prevention mandate, Theory of Change, DSP Toolkit, ESG alignment, SDGs

### 3. Impact Narrative Generator
**Triggered:** Optional — on Impact Engine page after calculations  
**Output:** 150-word narrative suitable for NHS commissioners — health economics results translated into commissioning language for bid documents

> Full prompt schemas available in [`/prompts`](./prompts/).

---

## Data model — 7 entities

| Entity | Key calculated fields |
|--------|----------------------|
| `ORGANISATION` | `digital_maturity_score` (0–100) |
| `FUNDING_ASSESSMENT` | `overall_readiness_score`, `compliance_score`, `impact_score`, `nhs_alignment_score`, `esg_score` — all AI generated |
| `IMPACT_PROJECT` | `total_cost_avoidance` = (admissions × £2,800) + (screenings × £180 × 12) |
| `IMPACT_PROJECT` | `roi_percentage` = ((cost_avoidance − cost) / cost) × 100 |
| `IMPACT_PROJECT` | `qaly_estimate` = (admissions × 0.15) + (screenings × 0.05) |
| `IMPACT_PROJECT` | `nhs_cost_saving` = qaly_estimate × £20,000 (NICE threshold) |
| `FUNDING_BID` | AI-generated bid text, status tracking |
| `PARTNERSHIP` | MoU documents, shared KPIs, status |
| `ESG_PORTFOLIO` | SDG mapping, capital deployed, impact score |

NICE threshold used: £20,000 per QALY — the standard value used by NHS commissioning bodies.

---

## Market context

| Metric | Figure |
|--------|--------|
| UK CICs addressable | 100,000+ |
| NHS annual budget | £180bn |
| NHS prevention mandate | Active — ICBs required to evidence community partnership |
| Corporate ESG capital searching for verified UK social impact routes | Growing |

No AI infrastructure currently exists in this domain. SIGFA occupies a structurally vacant position.

---

## Business model

| Revenue stream | Model | Customer | Indicative ARR |
|---------------|-------|----------|---------------|
| Corporate Membership | Annual subscription | Pharma / Corporate ESG | £25k–£75k/yr |
| NHS Innovation Licence | Per-Trust SaaS licence | NHS Trusts, ICBs | £15k–£40k/yr |
| Institutional Sponsorship | Programme sponsor | Foundations, DFIs | £50k–£200k |
| Funding Round Commission | 2–5% success fee | Large CIC funding rounds | Variable |
| Data Analytics Subscription | Aggregated insights | Policy bodies, researchers | £10k–£30k/yr |

---

## Roadmap

| Phase | Timeline | Milestones | ARR Target |
|-------|----------|-----------|------------|
| **Foundation** | 2025 Q1–Q3 | MVP live · CAHN anchor pilot · 10 CIC onboardings · First NHS ICB partnership | £200k |
| **Growth** | 2025 Q4–2026 Q2 | 50 CICs · 3 NHS Trust licences · 2 corporate ESG partnerships | £800k |
| **Scale** | 2026 Q3–2027 | 250 CICs · National NHS coverage · 10 corporate partners · Data analytics layer | £3M |
| **Dominance** | 2028 | UK default social impact infrastructure · Policy data partnerships · Series A | £10M |
| **EU Expansion** | 2029–2030 | EU launch · 3 EU health systems · Pan-European ESG capital layer | £25M+ |

---

## Deployment — Base44

SIGFA is deployed on Base44 using a structured master prompt package. Base44 handles backend, frontend, database, authentication, hosting, and email notifications — enabling rapid MVP deployment without custom infrastructure overhead.

**To deploy:**
1. Create a Base44 account at [base44.app](https://base44.app)
2. Enable PLAN MODE before pasting the master prompt
3. Add `ANTHROPIC_API_KEY` in Settings → Secrets
4. Use model `claude-sonnet-4-20250514` for all AI features
5. Apply the five refinement prompts in `/deployment/` to polish each section

> Full deployment package in [`/deployment`](./deployment/).

---

## Repository structure

```
sigfa/
├── README.md
├── prompts/
│   ├── 01-funding-fit-engine.md        # System + user prompt, output schema
│   ├── 02-bid-builder.md
│   └── 03-impact-narrative.md
├── deployment/
│   ├── master-prompt.md                # Full Base44 master prompt
│   ├── refinement-A-landing.md         # Landing page polish prompt
│   ├── refinement-B-funding-fit.md
│   ├── refinement-C-health-economics.md
│   ├── refinement-D-corporate-esg.md
│   └── refinement-E-design-system.md
├── data-model/
│   └── entities.md                     # Full 7-entity schema with field types
└── CHANGELOG.md
```

---

## Part of the Fruitful Bough Platform Portfolio

| Platform | Domain | Status |
|----------|--------|--------|
| [Aurora OS](../aurora-os) | AI discovery & growth intelligence | Phase 1 build |
| [ACE-OS](../ace-os) | Airport commerce & experience operating system | Architecture complete |
| [ACO](../aviation-capacity-orchestrator) | Aviation digital twin capacity orchestrator | PRD complete |
| [FMCG GTM Accelerator](../uk-fmcg-gtm-accelerator) | UK grocery channel decision intelligence | PRD complete |
| **SIGFA** (this repo) | Social impact growth & funding accelerator | Pilot proven · MVP live |

---

*Built by [Kwasi Boakye Acheampong](https://github.com/kwasibacheampong) · Principal, Fruitful Bough · 2025–2026*  
*Integrity · Trust · Value*
