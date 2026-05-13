# Lab 1 — Data Quality Detective Challenge

**File:** `MedTrack_Data_Quality_Report.docx`  
**Organisation:** MedTrack Ghana  
**Role:** Junior Developer  
**Applicable Law:** Rwanda Law No. 058/2021 of 13/10/2021

---

## 📄 Google Doc Link

> **[Open in Google Docs →](https://docs.google.com/document/d/1RfKAt3cIrC6PHqZfEYXoi6w_dEuRq65r/edit?usp=sharing&ouid=115037054348909797309&rtpof=true&sd=true)**  

---

## What This Document Contains

A Data Quality Assessment Report covering the MedTrack patient appointment database, which was causing SMS reminder failures, duplicate patient counts, and billing errors.

### Task 1 — Data Quality Dimension Violations
Six dimensions identified with specific record-level examples:

| Dimension | Example |
|---|---|
| Accuracy | P002: phone stored as 244789012 (missing leading zero) |
| Completeness | P004: patient name field entirely blank |
| Consistency | "Dr. Osei" vs "dr. osei" / "Paid" vs "paid" |
| Timeliness | P003: date 10/16/2025 outside expected window |
| Validity | Three different date formats in six rows |
| Uniqueness | P002 appears twice with conflicting phone numbers |

### Task 2 — Business Impact Assessment
Each issue traced to its operational consequence: SMS failures, billing losses, inflated revenue reports, and missed appointment reminders.

### Task 3 — Recommended Solutions
Three practical fixes: ISO 8601 date enforcement, phone number validation constraint, PaymentStatus enum with INITCAP normalisation.

### Task 4 — Biggest Risk of Poor Data Consistency
The core argument: bad data does not throw exceptions — it corrupts silently. The fix must happen at the data entry boundary, not downstream.

---

## Rwanda Law No. 058/2021 References
- **Art. 38** — Data controllers must implement appropriate technical measures to ensure data accuracy and integrity
- **Art. 8** — Data must not be stored longer than necessary for the stated purpose
- **Art. 53** — Administrative sanctions: RWF 2,000,000–5,000,000 or 1% of global turnover for non-compliance

**Source:** https://www.risa.gov.rw/data-protection-and-privacy-law
