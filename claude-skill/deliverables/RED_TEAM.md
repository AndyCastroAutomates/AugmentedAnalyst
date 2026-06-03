# Deliverable: Red Team Emulation Plan

**Trigger:** When source report provides sufficient TTP fidelity to emulate — specific tools, commands, file paths, execution chains, or behavioral sequences that a red team can replicate in a controlled environment.
**Audience:** Red team operators, purple team, offensive security practitioners.
**Purpose:** Translates observed adversary tradecraft into executable emulation steps. Validates detection coverage against real-world behavior.

---

## Format

---

RED TEAM EMULATION PLAN
TLP:[marking] | [Date] | Source: [Report citation]
Threat Actor: [Actor name]
AUTHORIZATION REQUIRED BEFORE EXECUTION
Reviewed by: ______________________________

**Summary of Threat Activity**

| Field | Detail |
|-------|--------|
| Threat Actor | |
| Campaign | |
| Targeted Sectors | |
| Objective | |
| ATT&CK Tactics | |
| Tools and Malware | |
| CVEs | [If present in source / None identified in source material] |

---

**Attack Procedures — Emulation Steps**

For each procedure, use this structure:

---

Step [N] — [Short name]

- Tactic: [ATT&CK Tactic]
- Technique: [T#### — Name]
- Confidence: [High / Medium / Inferred]
- Source Justification: "[Direct quote or specific behavioral description from source]"
- Procedure Description: [Technical detail of how the technique was used per source reporting]
- Emulation Plan:
  ```
  # AI-GENERATED — Derived from behavioral descriptions in [source].
  # Review before use. Validate in isolated lab environment.
  # Use benign stand-ins only — never execute actual malware hashes.
  # Obtain written authorization before execution.
  # Not guaranteed to be complete, accurate, or error-free.

  [Commands or steps]
  ```
- Environment Considerations: [Infrastructure or configuration required for this step]

---

Rules:
- Every step includes a source justification — a direct quote or specific behavior from the report.
- Every AI-generated code block carries the inline disclaimer at the top of that block.
- Use benign stand-ins in all commands. Never reference actual malware hashes as executable payloads.
- Named-application parent-child emulation: when source describes malware activating in response to a specific named application, emulate the parent-child process relationship as the primary detection validation target for that step.
- Obtain proper written authorization from the appropriate authority before conducting any adversary emulation activity.

---

**Detection Opportunities**

| Step | Log Source | Event ID | Key Fields to Validate |
|------|------------|----------|------------------------|
| [Step name] | [Sysmon / EDR / Windows Event] | [ID] | [Specific fields that should populate if detection fires] |

Do not reproduce Sigma rule blocks here. State: "Full Sigma detection rules are available in the Core Analysis Output. Validate that those rules fire correctly against each emulation step."

---

**Purple Team Collaboration**

| Technique | Validation Goal | Suggested KPI |
|-----------|-----------------|---------------|
| [T#### Name] | [Specific detection or response capability being validated] | [Measurable threshold — e.g., detection latency under 5 minutes, zero false negatives on high-fidelity indicator] |

---

**Mitigations and Hardening**

| MITRE M-Code | Mitigation | ATT&CK Technique IDs Addressed |
|--------------|------------|-------------------------------|
| M#### | [Mitigation description] | [T#### / T#### — explicit technique IDs, not step numbers] |

---

*All emulation steps use benign stand-ins. Actual malware samples are not referenced as executable payloads. All procedures are derived from [source citation] and represent observed adversary tradecraft — they do not constitute endorsement of offensive activity. Obtain proper authorization before execution. Nothing in this output is guaranteed to be complete, accurate, or error-free.*
