# Deliverable: Threat Hunt Hypothesis

**Trigger:** When source report contains behavioral TTPs that are huntable — specific process behaviors, network patterns, registry activity, or file artifacts that can be queried in a SIEM or EDR.
**Audience:** Threat hunting teams, incident response teams.
**Purpose:** Converts TTPs into actionable hunt procedures with log sources and prioritization. Analysts execute this directly against their environment.

---

## Format

---

THREAT HUNT HYPOTHESIS
TLP:[marking] | [Date] | Source: [Report citation]
Threat Actor: [Actor name] | Hunt Priority: High / Medium / Low
Reviewed by: ______________________________

**Hypothesis Statement**
[2-3 sentences. What actor, what behaviors, what the hunt is looking for, why existing detections may not catch it.]

---

**Section 1 — Hunt Hypotheses Table**

| Procedure | Description | Logs and Event IDs |
|-----------|-------------|-------------------|
| [Short title] | [Detailed description with specific search patterns. File paths, process names, command-line patterns, registry keys — sourced from report. Confidence level noted inline.] | [Specific log sources and Sysmon or Windows Event IDs] |

Rules:
- Only actionable procedures. No generic or ambiguous entries.
- Every procedure cites the source behavior that justifies it.
- Confidence noted per procedure where applicable.
- Procedures sourced from source report only — do not add generic hunt procedures not supported by source.

---

**Section 2 — Prioritization**

| Priority | Procedure | Effort | Rationale |
|----------|-----------|--------|-----------|
| P1 | [Name] | Low / Medium / High | [Why this is highest yield — IOC match, high fidelity indicator, low false positive rate] |
| P2 | [Name] | Low / Medium / High | [Rationale] |
| P3 | [Name] | Low / Medium / High | [Rationale] |

---

**Section 3 — Detection Rules**

If source report contains detection rules in any language: surface verbatim here, labeled with language and source.

If source contains no detection rules:
> No detection rules were provided in [source]. Sigma rules for all hunt procedures above are available in the Core Analysis Output. Those rules require validation by a qualified detection engineer before operational deployment.

Do not reproduce Sigma rule blocks here. Reference Core Analysis Output by name only.

---

**Section 4 — If Positive: Escalation Path**

[Numbered steps specific to this threat. What to preserve before remediation, what telemetry to pull, who to notify, what to hand off to IR. Derive from the specific threat behaviors in this report — not a generic IR checklist.]

---

*Hunt procedures are sourced from [report citation]. Confidence levels reflect analyst assessment of source evidence quality. Nothing in this output is guaranteed to be complete, accurate, or error-free. Queries must be adapted to your specific SIEM, EDR, and log schema before execution.*
