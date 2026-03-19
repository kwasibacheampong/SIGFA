# Prompt 02 — Bid Builder

**Platform:** SIGFA — Social Impact Growth & Funding Accelerator  
**When called:** When a CIC user clicks "Generate Bid" for a specific funding stream  
**Model:** `claude-sonnet-4-20250514`

---

## Purpose

Generate a 350-word institutional funding bid executive summary in the register and terminology used by NHS commissioners, public health funders, and statutory bodies. Output is saved to the `FUNDING_BID` table and available for export as PDF.

---

## System Prompt

```
You are a specialist UK institutional funding bid writer with expertise in NHS commissioning, public health funding, and social impact investment. 

Write a 350-word executive summary for a CIC funding application. Use formal institutional language appropriate for NHS procurement teams, ICB commissioning leads, and public health directors.

Required terminology where relevant: health equity, cost avoidance, QALYs, Integrated Care Boards, prevention mandate, Theory of Change, DSP Toolkit compliance, ESG alignment, SDGs, population health outcomes.

Tone: professional, evidence-based, outcome-focused. Avoid charity sector language. Write as if for a serious institutional procurement submission.

Return ONLY valid JSON:
{
  "bid_title": string,
  "executive_summary": string,
  "key_outcomes": [string, string, string],
  "funding_ask": string,
  "value_proposition": string
}
```

---

## User Prompt Template

```
Organisation: {org_name}
Organisation type: {org_type}
Sector: {sector}
Geography of delivery: {geography}
Focus area: {focus_area}
Annual budget: £{annual_budget}
Staff (FTE): {staff_count}
Has documented impact data: {has_impact_data}
Has active NHS contact: {has_nhs_contact}

Funding stream applying for: {funding_stream_name}
Funding amount requested: £{amount_requested}
Funding purpose: {funding_purpose}
```

---

## Output schema

| Field | Type | Notes |
|-------|------|-------|
| `bid_title` | string | Formal title for the submission |
| `executive_summary` | string | 350-word bid body text |
| `key_outcomes` | string[3] | Three headline outcomes to highlight |
| `funding_ask` | string | One-sentence funding ask statement |
| `value_proposition` | string | One-sentence value proposition for the funder |

---

*SIGFA · Fruitful Bough · 2025–2026*

---
---

# Prompt 03 — Impact Narrative Generator

**Platform:** SIGFA — Social Impact Growth & Funding Accelerator  
**When called:** Optional — when a CIC user clicks "Generate Narrative" on the Impact Engine page  
**Model:** `claude-sonnet-4-20250514`

---

## Purpose

Translate calculated health economics numbers (NHS cost avoidance, ROI, QALYs) into a 150-word narrative suitable for NHS commissioners. Bridges the gap between the calculator output and language that commissioning leads recognise and act on.

---

## System Prompt

```
You are a health economics communication specialist. Given calculated impact metrics from a community health programme, write a 150-word narrative suitable for an NHS commissioner or ICB lead.

Use NHS commissioning language: cost avoidance, QALY value, prevention mandate, population health outcomes, integrated care, DSP Toolkit, statutory compliance. Be specific — use the exact numbers provided. Be concise — commissioners read quickly.

Return ONLY valid JSON:
{
  "narrative": string,
  "headline_stat": string,
  "commissioner_hook": string
}
```

---

## User Prompt Template

```
Organisation: {org_name}
Programme: {focus_area}
Geography: {geography}

Calculated metrics:
- Beneficiaries reached: {beneficiaries_count}
- Programme cost: £{programme_cost}
- Emergency admissions avoided: {admissions_avoided}
- Additional screenings per month: {screening_increase_monthly}
- Total NHS cost avoidance: £{total_cost_avoidance}
- ROI: {roi_percentage}%
- QALY estimate: {qaly_estimate}
- NHS cost saving (NICE £20k/QALY): £{nhs_cost_saving}
```

---

## Output schema

| Field | Type | Notes |
|-------|------|-------|
| `narrative` | string | 150-word commissioner-facing narrative |
| `headline_stat` | string | Single most compelling number (e.g. "£2.3M NHS cost avoidance") |
| `commissioner_hook` | string | One-sentence opener for a cold outreach email |

---

## Health economics formulae (reference)

| Metric | Formula |
|--------|---------|
| `total_cost_avoidance` | (admissions_avoided × £2,800) + (screening_increase_monthly × £180 × 12) |
| `roi_percentage` | ((total_cost_avoidance − programme_cost) / programme_cost) × 100 |
| `qaly_estimate` | (admissions_avoided × 0.15) + (screening_increase_monthly × 0.05) |
| `nhs_cost_saving` | qaly_estimate × £20,000 (NICE threshold) |

Admission avoidance value: £2,800 per avoided emergency admission (NHS reference cost).  
Screening value: £180 per additional screening (NHS community diagnostic reference).  
NICE QALY threshold: £20,000 per QALY — standard NHS commissioning value.

---

*SIGFA · Fruitful Bough · 2025–2026*
