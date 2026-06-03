# Deliverable: Patch Notification

**Trigger:** Only when the source report explicitly identifies one or more CVEs.
**Audience:** System owners, IT administrators, patch management teams.
**Purpose:** Single-purpose remediation notice. What to patch, who owns it, by when. No detection rules — those live in Core Analysis Output and are not the concern of this audience.

---

## Format Rules

**Single CVE:** Generate the full detailed format below.
**Multiple CVEs:** Generate the Priority Triage Table first, then repeat the Vulnerability Detail block for each CVE below it.
**CVSS scores:** Source only. If not in source: "Not specified in source material." Never estimate or generate a score.
**KEV status:** Always check whether the CVE appears in the CISA KEV catalog. If KEV-listed, display the KEV Alert block prominently at the top — never buried.

---

## Format

---

VULNERABILITY PATCH NOTIFICATION
TLP:[marking] | [Date] | Source: [Report citation]
Distribution: IT Administrators, System Owners, Patch Management
Reviewed by: ______________________________

---

[IF CVE IS ON CISA KEV — display this block at the very top, before everything else:]

> KEV ALERT — ACTIVE EXPLOITATION CONFIRMED
> CISA added [CVE-ID] to the Known Exploited Vulnerabilities catalog on [date] based on confirmed evidence of active exploitation in the wild. Federal Civilian Executive Branch agencies are required to remediate under BOD 22-01. All organizations are strongly urged to prioritize remediation regardless of federal mandate applicability. Verify current remediation deadline at: https://www.cisa.gov/known-exploited-vulnerabilities-catalog

---

[FOR MULTIPLE CVEs — Priority Triage Table first:]

| CVE | Product | CVSS | KEV Listed | Ransomware Association | Patch Available | Priority |
|-----|---------|------|------------|----------------------|-----------------|----------|
| CVE-XXXX-XXXXX | Product | [Score or "Not specified in source"] | Yes [date] / No | Known / Unknown / No | Yes / No / Pending | Critical / High / Medium |

*CVSS scores sourced from [report/NVD]. Fields marked "Not specified in source material" reflect source data only — no values generated.*

---

[VULNERABILITY DETAIL — repeat for each CVE:]

**Vulnerability Summary**

| Field | Detail |
|-------|--------|
| CVE ID | |
| Affected Product | |
| Vulnerability Type | [e.g., SQL Injection, Path Traversal, Buffer Overflow] |
| CVSS Score | [From source only. If absent: "Not specified in source material"] |
| KEV Status | [Listed [date] / Not listed — monitor] |
| Ransomware Association | [Known / Unknown / Not applicable — from KEV catalog entry] |
| Exploitation Status | [Active in wild / PoC available / No known exploitation] |
| Patch Available | [Yes / No / Pending] |
| Federal Remediation Deadline | [If KEV: "Per BOD 22-01 — verify current deadline at cisa.gov/known-exploited-vulnerabilities-catalog" / If not KEV: "Not applicable"] |

**What This Vulnerability Does**
[Plain language explanation. What can an attacker do if they exploit it? What systems or data are at risk downstream? Where analyst interpretation extends beyond the literal source text, note it explicitly.]

**Who Is Affected**
[Specific affected products, versions, and deployment contexts from source. If version not in source: "Affected versions not specified in source material — consult vendor advisory directly."]

**Required Actions**

| Priority | Action | Owner | Deadline |
|----------|--------|-------|----------|
| Immediate | [Action] | [Role] | [Timeframe] |
| Short Term | [Action] | [Role] | [Timeframe] |
| Ongoing | [Action] | [Role] | [Timeframe] |

[Where credential rotation, session invalidation, or downstream remediation steps are implied by the vulnerability type, include them and note they are analyst-derived from the vulnerability description rather than explicitly stated in source.]

**Mitigation and Patch Guidance**
[Vendor patch references, workarounds, and CISA guidance links from source. If specific patch version numbers or step-by-step remediation are not available in source, state this explicitly and direct to vendor advisory.]

---

*This notification is based solely on [source citation]. Fields not addressed in source material are explicitly marked. No CVSS scores, patch versions, or technical details have been generated beyond what appears in source documents. Verify current patch status and vendor guidance directly before remediating. Nothing in this output is guaranteed to be complete, accurate, or error-free.*
