# Findings Summary – SafeStore ISO/IEC 27001:2022 Stage 2 Audit

**Organisation:** SafeStore Pty Ltd (fictional)
**Audit type:** ISO/IEC 27001:2022 Stage 2 certification audit, one day
**Location:** SafeStore Melbourne HQ and approved virtual access
**Audit standard:** ISO 19011 · **Classification rules:** Certification Body Finding Criteria (reference document 14; see the README)

---

## 1. Corrected audit objectives, scope and criteria

| Element | Draft plan (deficient) | Corrected |
|---|---|---|
| Objectives | "Identify weaknesses…", "Determine whether SafeStore should receive certification" | Determine conformity of the ISMS with ISO/IEC 27001:2022, evaluate its effectiveness, and give the certification body a basis for its decision. The audit team only **recommends**; the certification body **decides**. |
| Scope | Includes the *physical operation of third-party data centres* and excludes *outsourced services* | Matches the ISMS Scope Statement: data-centre physical operation, customer endpoints and outsourced systems that don't support the service are **excluded**, while the cloud/backup suppliers that support the service stay **in scope** |
| Criteria | "A.8.3 Information backup", "A.8.28 Secure disposal", "A.6.4 Supplier security" | **A.8.13** Information backup, **A.7.14** Secure disposal or re-use of equipment, **A.5.19–A.5.22** Supplier security (A.8.28 is secure coding; A.6.4 is the disciplinary process) |
| Audit risk: evidence unavailable | "Use previous screenshots or reports" | Seek alternative current evidence, agree any plan change with the client, and state the limitation in the report |
| Audit risk: running out of time | "Reduce the time spent on remaining activities" | Monitor progress, reallocate work, and agree changes without compromising the audit objectives |
| Audit risk: disagreement | "Explain that the auditor's decision is final" | Discuss the evidence; resolve the disagreement, or record it in the report if it can't be resolved |

## 2. Sampling

| Criterion | Population | Sample | Method |
|---|---|---|---|
| A.8.3 | All user, developer, admin and temporary accounts | DEV-014, ADM-003, TEMP-007 | Judgement sample of the highest-risk account types |
| A.8.13 | Backup logs, month-end/offsite copies, restore tests | Recent daily logs, latest month-end and offsite copy, latest quarterly restore | Judgement sample of recent and month-end records |
| A.7.14 | 3 retired devices | All 3 | Whole small population (100%) |

Sampling was expanded only where a problem was found. No problem required it.

## 3. Findings

### C1 – A.8.3 Information access restriction (Conformity)
- The CTO and the Software Developer described the access controls in interview, and the account records matched what they said.
- All three sampled accounts were reviewed and conformed:
  - MFA is on for the admin and temporary-admin accounts.
  - The temporary account has an expiry date.
  - Developers have no permanent admin rights.

### C2 – A.8.13 Information backup (Conformity)
- Daily backups succeeded and were encrypted.
- The month-end offsite copy was confirmed.
- The quarterly restore test succeeded and was recorded.

### N1 – A.7.14 Secure disposal or re-use of equipment (Minor nonconformity)
- **Evidence:**
  - The secure-disposal procedure is still in draft.
  - There are no erasure or destruction records.
  - Three retired devices are held securely, awaiting disposal.
- **Why the criterion isn't met:** SafeStore can't show that data is removed or securely overwritten before equipment is disposed of or re-used.
- **Related findings:**
  - The SoA lists A.7.14 as *Not fully implemented*.
  - Risk R4 has a residual rating of 12 (High) and control effectiveness *Poor*.
  - The treatment for R4 and the related management-review action were both due 31 March 2025 and are still open.
- **Why minor:** the problem is limited and isolated. It affects 3 devices, they are stored securely and none has been disposed of, so it isn't a systemic breakdown.

### OFI1 – A.5.19–A.5.22 Supplier security
Suppliers are reviewed only when contracts are renewed. A documented, risk-based schedule for reviewing critical suppliers would complete the treatment for Risk R5.

### OFI2 – A.6.3 Awareness and training
The training dashboard screenshot has no date and no underlying records, so completion couldn't be independently verified. Keeping dated, system-generated completion records would let SafeStore show it is meeting its 100% training objective. The evidence limitation is recorded in the report.

**Totals:** 0 major · 1 minor · 2 OFIs

## 4. SoA vs risk register review

| Risk | Annex A controls | SoA status | Consistent? |
|---|---|---|---|
| R1 Access | A.5.15–A.5.18, A.8.2–A.8.3, A.8.5 | Implemented | Consistent |
| R2 Backup | A.8.13–A.8.14 | Implemented | Consistent |
| R3 Incident | A.5.24–A.5.28 | Not fully implemented | Consistent |
| R4 Disposal | A.7.14 | Not fully implemented | Consistent |
| R5 Supplier | A.5.19–A.5.22 | Not fully implemented | Consistent |
| R6 Vulnerabilities | A.8.8–A.8.9, A.8.16 | Implemented | Consistent |

**Documentation inconsistencies identified:**
1. The draft audit plan uses the wrong control references (backup, disposal and supplier).
2. The draft audit plan's scope conflicts with the ISMS Scope Statement.
3. Risk R4 lists "equipment records retained" as an existing control, but the evidence pack shows no disposal records.
4. Access-review frequency is defined differently in different places: "planned intervals" (Access Control Policy), annual (Internal Audit Summary) and quarterly (CTO interview).
5. Treatment actions and management-review actions due 31 March 2025 are still open.

The risk methodology contains all the characteristics required by ISO/IEC 27001 Clause 6.1.2: risk criteria and acceptance criteria, consistent and comparable results, identification of confidentiality, integrity and availability risks with named risk owners, analysis of likelihood and consequence, and evaluation with prioritisation.

## 5. Corrective action for N1

| Step | Detail |
|---|---|
| Correction | Keep the devices secured. Approve the procedure, then securely erase or destroy the 3 devices, obtain certificates and update the equipment register |
| Root cause (indicated; SafeStore to confirm) | The disposal procedure was never finalised or approved, and the overdue R4 treatment action was not escalated |
| Corrective action | Finalise and approve (CTO) a disposal and re-use procedure that defines methods, evidence and responsibilities. Retain records, update R4 and the SoA, and track overdue actions through risk and management reviews. Owner: Operations Manager |
| Follow-up | Verify both **implementation** (approved procedure, certificates, updated register) and **effectiveness** (later disposals follow the procedure). Status: *More evidence required* |

## 6. Conclusion and recommendation

The ISMS is effective overall, with one minor gap. **Recommend certification subject to corrective action.** The certification body makes the final decision.

---
*Cell-by-cell source citations for Stages 3–5 are in [`source-traceability/`](source-traceability/).*
