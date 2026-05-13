# Lab 3 — QuickLoan Mobile Ethical Data Governance Review

**File:** `QuickLoan_Governance_Review.docx`  
**Organisation:** QuickLoan Mobile  
**Role:** Independent Data Governance Consultant  
**Applicable Law:** Rwanda Law No. 058/2021 of 13/10/2021

---

## 📄 Google Doc Link

> **[Open in Google Docs →](https://docs.google.com/document/d/1bkQ5_HFGId7SGKOV5FSQC-w44BhgDJeb/edit?usp=sharing&ouid=115037054348909797309&rtpof=true&sd=true)**  

---

## What This Document Contains

A three-part governance review of QuickLoan Mobile's data pipeline, covering a Governance Review Card, a corrected data flow diagram with six annotations, and a summary essay.

### Deliverable 1 — Governance Review Card

| Row | Risk | Summary |
|---|---|---|
| 1 | Data Quality | Incomplete and inconsistently formatted records produce unreliable ML credit scores. Fix: server-side validation at API Gateway + standardisation in Preprocessing Service |
| 2 | Legal & Compliance | Excessive PII collection (contact list, GPS, device logs) with no consent screen. Classification: **SENSITIVE**. Violates Rwanda DPL Art. 13-14 and Art. 7. Penalty risk: RWF 2M–5M or 1% turnover (Art. 53) |
| 3 | Bias & Fairness | Fully automated loan decisions with no logging or human review. DPIA required per Rwanda DPL Art. 38. Fix: audit logging at Decision Service + monthly Demographic Parity check |
| 4 | Reporting Metric | Group Approval Rate Disparity (GARD) — Grouped Bar Chart updated monthly. Threshold: < 10 percentage points. Breach triggers mandatory model review |

### Deliverable 2 — Corrected Data Flow Diagram Annotations

Six corrections documented:
1. Data minimisation at User App (Art. 7)
2. Consent Gate between API Gateway and Raw Data DB (Art. 13-14)
3. SENSITIVE classification + retention policy on Raw Data DB (Art. 8, 38)
4. Explicit preprocessing rules in Preprocessing Service (Art. 38)
5. Immutable audit logging at Decision Service (Art. 38 — DPIA requirement)
6. Data masking/pseudonymisation in Analytics DB (Art. 38)

### Deliverable 3 — Summary of Review Process
How Data Lifecycle and Classification principles identified the risks, and how the GARD metric creates accountability through visibility — enabling the Rwanda Data Protection Office to verify fairness month by month.

---

## Rwanda Law No. 058/2021 References
- **Art. 7** — Data Minimisation and Purpose Limitation
- **Art. 8** — Storage Limitation
- **Art. 13–14** — Lawful Basis and Consent
- **Art. 38** — Technical Safeguards, Data Accuracy, DPIA for Automated Decision-Making
- **Art. 40** — Designation of the Data Protection Officer
- **Art. 53** — Administrative Sanctions: RWF 2,000,000–5,000,000 or 1% of global annual turnover

**Sources:**
- https://www.risa.gov.rw/data-protection-and-privacy-law
- https://dpo.gov.rw
- Full legal text: https://www.risa.gov.rw/fileadmin/user_upload/RISA/Publications/2.Laws/Law_relating_to_the_protection_of_personal_data_and_privacy.pdf
