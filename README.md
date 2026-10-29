# SafeStore ISO/IEC 27001:2022 Mock Certification Audit

A complete, end-to-end **mock Stage 2 ISO/IEC 27001:2022 certification audit** of *SafeStore Pty Ltd*, a fictional Australian cloud-storage provider. The audit was performed as a Lead Auditor case study following **ISO 19011** (guidelines for auditing management systems). It covers the full audit lifecycle: planning, leading the team, conducting the audit, reporting and closing, and professional conduct.

> **Scenario:** SafeStore provides secure cloud storage hosted in Australian data centres (CloudX, PowerDash, CollabCentral, O365, Azure/AWS backups). The certification body has issued a *deliberately deficient* draft audit plan and an evidence pack. The task is to correct the plan, run the audit, grade the findings against the certification body's criteria, and recommend whether SafeStore should be certified.

---

## Audit outcome at a glance

| Ref | Control (ISO/IEC 27001:2022 Annex A) | Result | Key evidence |
|---|---|---|---|
| **C1** | A.8.3 Information access restriction | ✅ Conformity | MFA on privileged accounts; temporary admin access expires automatically; 3 sampled accounts (developer, admin, temporary admin) reviewed and conforming |
| **C2** | A.8.13 Information backup | ✅ Conformity | Daily encrypted backups; month-end offsite copy; quarterly restore test successful and recorded |
| **N1** | A.7.14 Secure disposal or re-use of equipment | ⚠️ **Minor nonconformity** | Disposal procedure still in draft; no erasure/destruction records for 3 retired devices (held securely) |
| **OFI1** | A.5.19–A.5.22 Supplier security | 💡 Opportunity for improvement | Suppliers reviewed only at contract renewal; no documented review schedule |
| **OFI2** | A.6.3 Awareness and training | 💡 Opportunity for improvement | Training dashboard screenshot has no report date or underlying records (evidence limitation stated) |

**Conclusion:** The ISMS is effective overall, with one minor gap.
**Recommendation:** Recommend certification, subject to corrective action on N1. The final decision rests with the certification body.

See [`docs/findings-summary.md`](docs/findings-summary.md) for the full findings, the corrective-action plan, the problems found in the draft audit plan, and the results of the documentation review.

---

## Repository structure

```
safestore-iso27001-audit/
├── README.md
├── audit-workbooks/                 ← Completed audit deliverables (the project work)
│   ├── Stage1_Plan.xlsx                 Draft plan evaluation + corrected final audit plan
│   ├── Stage2_Lead_the_Team.xlsx        Opening meeting, team briefing/allocation, team management & finding review
│   ├── Stage3_Conduct.xlsx              Audit checklist, sampling record, findings (ISO 19011 A.18 format), team debrief, SoA review
│   ├── Stage4_Report_and_Close.xlsx     Closing meeting, final audit report, corrective action & follow-up
│   └── Stage5_Professional_Behaviour.xlsx  Ethics scenarios, self-evaluation, professional reflection
└── docs/
    ├── findings-summary.md          Narrative summary of the audit and its results
    └── source-traceability/         Cell-by-cell citation of where each answer comes from
        ├── Stage3_Answer_Sources.xlsx
        ├── Stage4_Answer_Sources.xlsx
        └── Stage5_Answer_Sources.xlsx
```

---

## Reference documents (not included)

The workbooks were answered using 14 source documents provided by the course: SafeStore's ISMS documentation, the audit brief, and the certification body's grading rules. They are course materials, so they are **not published in this repository**. Here is what each one contains and how it was used.

### SafeStore ISMS documentation

| # | Document | What it contains | How it was used in the audit |
|---|---|---|---|
| 1 | **ISMS Scope Statement** | Scope covers secure cloud storage in Australian data centres (CloudX, PowerDash, CollabCentral, O365, Azure/AWS backups), with Melbourne HQ as the boundary. It excludes the physical operation of third-party data centres, customer endpoints and outsourced systems that don't support the service | Used to correct the draft plan's scope and to confirm the SoA is consistent with the ISMS scope |
| 2 | **ISMS Policy Manual** | Commitment to confidentiality, integrity and availability; high-level security objectives; responsibilities of the Managing Director, CTO, Operations Manager, Support Lead, Developer and all staff; annual review | Used as an audit criterion and to confirm who receives the report and who owns the ISMS |
| 3 | **ISMS Roles & Responsibilities** | Detailed ISMS duties for each role, including approving procedures, root-cause analysis, keeping records and reporting weaknesses | Used to assign owners for the corrective action and to set the escalation routes |
| 4 | **Information Security Objectives** | Measurable targets, for example 100% training completion, 98% successful backup jobs, 100% successful restore tests and zero repeat audit findings | Used to support OFI2 (training records) and to frame follow-up |
| 5 | **Risk Assessment & Treatment Plan** | Risk methodology (5×5 likelihood × consequence scoring, acceptance criteria, treatment options) and a risk register R1–R6 with owners, residual ratings, treatments and due dates | Used to link N1 to Risk R4 (residual 12, High; controls rated *Poor*), to check the methodology against Clause 6.1.2, and to cross-check the SoA |
| 6 | **Statement of Applicability (revised)** | Every Annex A control with its applicability, implementation status and justification. A.7.14, A.5.19–A.5.22 and A.5.24–A.5.28 are marked *Not fully implemented* | Used for the SoA-vs-risk-register review and as the criteria reference for each finding |
| 7 | **Legal & Regulatory Register** | Privacy Act 1988, Australian Privacy Principles, Notifiable Data Breaches scheme, contract obligations and the ASD Essential Eight (voluntary) | Used to set the legal criteria and to support secure disposal of personal information |
| 8 | **Access Control Policy** | Least privilege, access reviews at planned intervals, MFA for privileged access, expiry dates for temporary accounts, and just-in-time elevation | Used as the criterion for conformity C1 (A.8.3) |
| 9 | **Backup & Data Retention Procedure** | Daily incremental and weekly full backups, encryption, an offsite copy, quarterly restore tests, monthly log reviews, and destruction certificates for backup media | Used as the criterion for conformity C2 (A.8.13) and to support the N1 correction |
| 10 | **Incident Management Procedure** | Incident roles (the CTO as incident owner, the Operations Manager as coordinator), reporting, escalation and progress reporting | Used to set the escalation route and to plan the response to an ethics scenario (sensitive evidence sent to a personal email) |
| 11 | **Internal Audit & Management Review Summary** | The 2024 internal audit (2 minor NCs, both closed in December 2024) and the January 2025 management review, which has open actions on supplier reviews and the disposal procedure | Used to show the earlier corrective actions were verified and closed, and to identify that the N1 and OFI1 actions are overdue |

### Audit brief and certification body criteria

| # | Document | What it contains | How it was used in the audit |
|---|---|---|---|
| 12 | **Draft Audit Plan (deliberately deficient)** | One-day Stage 2 plan with flawed objectives, a scope that conflicts with the ISMS scope, wrong control references (A.8.3, A.8.28, A.6.4) and poor responses to audit risks (e.g., *"Explain that the auditor's decision is final"*) | Evaluated and corrected in Stage 1, then used as the baseline for the schedule and team roles |
| 13 | **Audit Evidence Pack** | Interview responses (CTO, Operations Manager, Developer, Support Lead), the access-control sample, backup and restore results, disposal evidence, supplier and training evidence, and the audit status | The objective evidence behind every finding: C1, C2, N1, OFI1 and OFI2 |
| 14 | **Certification Body Finding Criteria** | Definitions of Conformity, Minor NC, Major NC, Opportunity for Improvement and Insufficient Evidence | Used to grade every finding by criterion, evidence, extent and significance |

`docs/source-traceability/` lists, cell by cell, which of these documents and sections supports each answer.

---

## Audit lifecycle covered

| Stage | ISO 19011 activity | What was produced |
|---|---|---|
| **1. Plan** | Audit feasibility; preparing the audit plan | Evaluation of the deficient draft plan; corrected final audit plan (objectives, scope, criteria, schedule, sampling, audit risks, communication, confidentiality) |
| **2. Lead the team** | Opening meeting; team briefing and work allocation | Opening-meeting record; team briefing; work allocation; responses to a threat to objectivity and to documented information that could not be provided in time; finding review |
| **3. Conduct** | Collecting and verifying evidence; generating findings | Audit checklist and sampling record for A.8.3, A.8.13 and A.7.14; findings in ISO 19011 A.18 format; team debrief; SoA-vs-risk-register and ISMS documentation review |
| **4. Report & close** | Closing meeting; audit report; follow-up | Closing-meeting record; final audit report; corrective action (correction, root cause, action) and follow-up verification for N1 |
| **5. Professional behaviour** | ISO 19011 audit principles (integrity, fair presentation, due professional care, confidentiality, independence, evidence-based approach, risk-based approach) | Responses to five ethics scenarios; Lead Auditor self-evaluation and development plan; professional reflection |

---

## Skills demonstrated

- **ISO/IEC 27001:2022** – Clauses 4–10, Annex A controls, Statement of Applicability, risk assessment methodology (Clause 6.1.2) and risk treatment (6.1.3)
- **ISO 19011 audit practice** – audit planning, feasibility, sampling (judgement-based), objective evidence, A.18 finding format, closing meetings, report content, follow-up
- **Finding classification** – conformity / minor NC / major NC / OFI / insufficient evidence, judged on criterion, evidence, extent and significance
- **Risk-based thinking** – linking findings to the risk register (e.g., N1 ↔ Risk R4, residual 12 High) and the SoA
- **Document control and consistency review** – spotting mislabelled control references, scope conflicts and gaps between documents and evidence
- **Corrective action management** – correction vs root cause vs corrective action; verifying both implementation and effectiveness
- **Auditor ethics** – impartiality, conflicts of interest, confidentiality, handling pressure and disagreements, and the line between giving an OFI and consulting

---

## How to read this project

1. Read [Reference documents](#reference-documents-not-included) above to learn the scenario. Documents 12 and 13 form the audit brief.
2. Open the workbooks in `audit-workbooks/` in order, from Stage 1 to Stage 5. Pale-yellow cells hold the answers.
3. Use `docs/source-traceability/` to see which reference document and section supports each answer.

> GitHub can't preview `.xlsx` files in the browser. Use **Download raw file** and open the file in Excel, Google Sheets or LibreOffice.

---

## Disclaimer

This is a **training exercise** completed as part of the *GRC Mastery* Lead Auditor course. SafeStore Pty Ltd is a fictional organisation, and the people, systems and events in this project are illustrative. The reference documents and workbook templates are course materials provided for educational purposes and are not professional advice. Nothing here is a real certification audit.

---

## Author

**Tyler Leath** – building a career in GRC, IAM and compliance.
- LinkedIn: [linkedin.com/in/tyler-leath-a93781143](https://www.linkedin.com/in/tyler-leath-a93781143)
- GitHub: [github.com/tylerleath4-star](https://github.com/tylerleath4-star)
