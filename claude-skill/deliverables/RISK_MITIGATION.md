# Deliverable: Risk Mitigation Plan

**Trigger:** Always generated.
**Audience:** All teams — each row of the action table has an assigned owner.
**Purpose:** Closes the operational cycle. Converts the threat picture into prioritized, owner-assigned actions with deadlines. Pairs with the Threat Assessment as the closing bookend of the operational cycle.

---

## Format

---

RISK MITIGATION PLAN
TLP:[marking] | [Date] | Source: [Report citation]
Reviewed by: ______________________________

**Threat Summary**
[2-3 sentences: what the threat is, who is behind it, current activity status. Then structured fields below.]

| Field | Detail |
|-------|--------|
| Threat Actor | |
| Campaign Status | Active / Emerging / Historical |
| Targeting | [Specific industries, regions, organization types from source] |

---

**Attack Vector Analysis**

| Attack Phase | Technique | Specific Method | Source Reference |
|--------------|-----------|-----------------|------------------|
| [Tactic] | [T#### Name] | [Specific method — not generic descriptions] | [Page, section, or quote from source] |

Include all attack phases present in source. Every row cites source. If attack vector information is limited: "Attack vector details not comprehensively addressed in available reporting."

---

**Impact Assessment**

| Impact Type | Severity | Rationale | Source Basis |
|-------------|----------|-----------|--------------|
| [Type] | Critical / High / Medium / Low | [From source] | [Quote or reference] |

Do not speculate about impacts not discussed in source.

---

**Technical Indicators**

Do not reproduce the full IOC table from Core Analysis Output. State: "Full IOC list with confidence scores is available in the Core Analysis Output." List only indicators directly relevant to mitigation prioritization — maximum 6 rows.

| Type | Value | Relevant To |
|------|-------|-------------|
| [Hash / Domain / IP] | [Value] | [Which mitigation action it informs] |

---

**Risk Mitigation Recommendations**

| Priority | Action | Specific Implementation | Addresses | Owner |
|----------|--------|------------------------|-----------|-------|
| Immediate (24hrs) | [Action] | [Exact steps] | [T#### technique ID] | [Role] |
| Short Term (72hrs) | [Action] | [Exact steps] | [T#### technique ID] | [Role] |
| Medium Term (30 days) | [Action] | [Exact steps] | [T#### technique ID] | [Role] |

Rules:
- Every action must directly counter a specific technique from the source report.
- Mitigations map to explicit ATT&CK Technique IDs — not step numbers.
- Implementation must be specific. No generic advice without explicit context from source.
- If source does not provide sufficient detail: "Source reporting does not contain sufficient technical detail to provide specific implementation steps for [area]. Consult vendor guidance directly."

---

**Detection**

Do not reproduce Sigma rules from Core Analysis Output. State: "Detection rules for all behaviors above are available in the Core Analysis Output. Sigma rules require validation by a qualified detection engineer before deployment."

---

**Gaps and Uncertainties**

Information not addressed in source: [List specific aspects the report does not cover]
Low confidence areas: [Where source uses uncertain language or conflicts exist]
Recommended follow-up collection: [Specific intelligence gaps to prioritize]

If reporting is comprehensive: "Available reporting provides comprehensive coverage with no significant gaps identified."

---

**Source**

[Full citation for each source document used — title, author, date, TLP marking, URL if available]

---

*This plan is based solely on the source documents listed above. All recommendations are directly traceable to findings in those documents. No speculative recommendations have been included. Where source reporting does not provide sufficient detail to support a specific recommendation, that gap is noted above. Nothing in this output is guaranteed to be complete, accurate, or error-free.*
