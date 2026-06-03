# Deliverable: Threat Assessment

**Trigger:** Always generated.
**Audience:** CTI team, operational leadership.
**Purpose:** IPB-informed threat picture covering operational environment, attack surface, threat profile, predicted scenarios, and intelligence gaps. Entry point of the operational cycle — pairs with the Risk Mitigation Plan as the closing bookend.

---

## Format

---

THREAT ASSESSMENT
TLP:[marking] | [Date] | Source: [Report citation]
Reviewed by: ______________________________

**Executive Summary**
[3-4 sentences: threat actor and objective, systems at highest risk, most likely attack scenario, top defensive priority. Be specific. No generic statements. Base only on source material. State overall confidence level with justification.]

---

**Step 1 — Operational Environment**

Likely Targets [Confidence: H/M/L — justification]
[Specific industries, regions, or system types extracted from source. If not in source: "Not addressed in source reporting."]

Critical Systems at Risk [Confidence: H/M/L — justification]
[Map threat targeting to specific system types. If no organizational context provided: "Generalized assessment based on threat targeting patterns in source reporting."]

External Dependencies [Confidence: H/M/L — justification]
[Third-party, supply chain, or partner risks based on TTPs or targeting described in source.]

---

**Step 2 — Attack Surface Analysis**

| Element | Assessment | Source Basis |
|---------|------------|--------------|
| Key Terrain | [Critical systems giving attacker decisive advantage — explain WHY] | [Direct quote or figure reference] |
| Attack Paths | [Entry to Movement to Objective chain from source] | [Direct quote or figure reference] |
| Obstacles | [Security controls that impede this specific threat based on documented techniques] | [Sourced or noted as general control not confirmed in source] |
| Visibility Gaps | [Where this threat evades detection based on documented evasion techniques] | [Direct quote or figure reference] |

Terrain Assessment: [Favors Attacker / Defender / Contested] — [1 sentence justification sourced from report]

---

**Step 3 — Threat Profile**

3.1 Identification
| Actor | Type | Status | Targeting | Confidence |
|-------|------|--------|-----------|------------|
| [Name] | [Nation-state / Criminal / Hacktivist] | [Active / Emerging / Dormant] | [Specific sectors and regions] | [H/M/L — justification] |

3.2 Capabilities [Confidence: H/M/L]
[2-3 sentences: tooling sophistication, exploitation capabilities, infrastructure quality, operational security level. Assign capability tier: Tier 1 Advanced Persistent / Tier 2 Sophisticated / Tier 3 Intermediate / Tier 4 Opportunistic. Base strictly on source.]

3.3 Intent [Confidence: H/M/L]
[2 sentences: primary objective, target selection pattern. Explicitly distinguish FACTS stated in source from ASSESSMENTS inferred from behavior.]

3.4 Key Techniques
[Do not reproduce the full ATT&CK table from Core Analysis Output. State: "Full ATT&CK mapping with data components, mitigations, and confidence levels is available in the Core Analysis Output." List only the 3-4 most operationally significant techniques here with their T-codes.]

---

**Step 4 — Predicted Attack Scenarios**

Most Likely Scenario [Probability: H/M/L | Confidence: H/M/L — justification]
[2 sentences describing expected attack path based on documented patterns.]

| Step | Attacker Action | Technique | What to Watch For | Response Window |
|------|-----------------|-----------|-------------------|-----------------|
| 1 | [Action] | [T#### from Step 3.4] | [Specific detectable indicator] | [Estimated time to next step] |
| 2 | [Action] | [T#### from Step 3.4] | [Specific indicator] | [Time window] |
| 3 | [Action] | [T#### from Step 3.4] | [Specific indicator] | [Time window] |
| 4 | [Action] | [T#### from Step 3.4] | [Specific indicator] | — |

Rules:
- Every technique must trace back to Step 3.4 and the Core Analysis ATT&CK mapping.
- "What to Watch For" must be specific enough to write a detection rule.
- Response windows based on source-documented speed where available. If not in source, state "Not specified in source."

Best Disruption Point: [Step number — specific action required]

Worst Case Scenario [Impact: Critical / Severe / Moderate | Probability: H/M/L]
[2 sentences: highest impact if attacker achieves optimal conditions. Focus on impact differences, not just technical differences.]
Key Differences from Most Likely: [What changes — specific about impact]
Watch For: [Unique indicator this scenario is unfolding instead of Most Likely]
Best Disruption Point: [Phase — specific action]

Alternative Scenario: [Include only if source supports a distinct third scenario. Omit entirely if not supported. Do not invent.]

---

**Intelligence Gaps**
[2-4 specific gaps that limit assessment quality. State what each gap would improve if filled. If no significant gaps: "Available reporting provides comprehensive coverage with no significant intelligence gaps identified."]

---

**Confidence and Limitations**

Key Assumptions: [1-2 critical assumptions the analysis depends on]
Critical Unknowns: [What is missing from source that most limits confidence]
Source: [What each source contributed and its limitations — single source vs. corroborated reporting]

---

**Quick Reference**

Top IOCs: [Reference Core Analysis IOC table. Do not reproduce. List max 6 highest-priority indicators with scenario association only.]

Detection Priorities:
| Behavior | Technique | Where to Look |
|----------|-----------|---------------|
[Reference Core Analysis Sigma rules. Do not reproduce. List behaviors only — 3-5 rows.]

Leadership Summary: [Exactly 2 sentences. No jargon. No acronyms except widely known. Sentence 1: threat and risk. Sentence 2: single most important action.]

---

*This assessment is based solely on [source citation]. All analytical judgments beyond explicitly stated facts are marked with confidence levels. No indicators or techniques have been added beyond what appears in the source document. Recommended actions should be validated by your security team before implementation.*
