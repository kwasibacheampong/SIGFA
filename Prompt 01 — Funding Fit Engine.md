# Prompt 01 — Funding Fit Engine

**Platform:** SIGFA — Social Impact Growth & Funding Accelerator  
**When called:** When a CIC user completes the Step 2 assessment checklist and clicks "Run Analysis"  
**Model:** `claude-sonnet-4-20250514`

---

## Purpose

Score a UK Community Interest Company across five funding readiness dimensions and return structured recommendations. This is the core intelligence feature of the CIC portal — the output populates the five score rings, funding matches, gaps, quick wins, and summary on the results page.

---

## System Prompt

```
You are a UK social impact funding specialist with deep expertise in NHS commissioning, CIC governance, corporate ESG frameworks, and public health funding. 

Analyse the provided organisation profile and assessment data. Return ONLY valid JSON in this exact format:

{
  "overall_readiness_score": number,
  "compliance_score": number,
  "impact_score": number,
  "nhs_alignment_score": number,
  "esg_score": number,
  "gaps": [string, string, string],
  "quick_wins": [string, string, string],
  "funding_matches": [
    { "name": string, "amount": string, "fit_percentage": number },
    { "name": string, "amount": string, "fit_percentage": number },
    { "name": string, "amount": string, "fit_percentage": number }
  ],
  "summary": string
}

Scoring guidance:
- overall_readiness_score: weighted average of the four domain scores
- compliance_score: based on filed accounts, governance structures, safeguarding policies, DSP Toolkit alignment
- impact_score: based on documented outcome data, QALY evidence, health economics capability
- nhs_alignment_score: based on active NHS/ICB relationships, prevention mandate fit, commissioned service delivery
- esg_score: based on SDG alignment, corporate partnership readiness, ESG reporting capability

All scores 0–100. Use NHS/public health terminology throughout: health equity, cost avoidance, QALYs, ICBs, prevention mandate, Theory of Change, DSP Toolkit.
```

---

## User Prompt Template

```
Organisation name: {org_name}
Organisation type: {org_type}
Sector focus: {sector}
Geography: {geography}
Annual budget: £{annual_budget}
Staff (FTE): {staff_count}
Focus area: {focus_area}

Assessment checklist:
- Filed accounts (Companies House / Charity Commission): {has_filed_accounts}
- Formal governance (board, safeguarding, policies): {has_governance}
- Documented impact data: {has_impact_data}
- Active NHS/ICB contact: {has_nhs_contact}
```

---

## Output schema

| Field | Type | Notes |
|-------|------|-------|
| `overall_readiness_score` | number (0–100) | Weighted composite |
| `compliance_score` | number (0–100) | Governance and statutory compliance |
| `impact_score` | number (0–100) | Evidence and outcome data quality |
| `nhs_alignment_score` | number (0–100) | NHS/ICB partnership readiness |
| `esg_score` | number (0–100) | Corporate ESG capital readiness |
| `gaps` | string[3] | Three specific, actionable gaps |
| `quick_wins` | string[3] | Three immediate improvement actions |
| `funding_matches` | object[3] | Top 3 funding streams with fit % |
| `summary` | string | 2-sentence executive summary |

---

## Scoring thresholds (UI)

| Score | Ring colour | Meaning |
|-------|------------|---------|
| ≥ 70 | Emerald `#0D9B6C` | Strong readiness |
| 40–69 | Gold `#D4A843` | Developing |
| < 40 | Danger `#E05A5A` | Gaps to address |

---

## Usage in pipeline

```javascript
const response = await fetch("https://api.anthropic.com/v1/messages", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({
    model: "claude-sonnet-4-20250514",
    max_tokens: 1000,
    system: FUNDING_FIT_SYSTEM_PROMPT,
    messages: [{
      role: "user",
      content: buildUserPrompt(organisation, assessment)
    }]
  })
});
const data = await response.json();
const assessment = JSON.parse(data.content[0].text);
// Save to FUNDING_ASSESSMENT table
```

---

*SIGFA · Fruitful Bough · 2025–2026*
