# CTI Fusion Analyst -- Gemini Gem

Deploy the CTI Fusion Analyst as a custom Gem in Google Gemini. Works in Google Gemini Advanced (gemini.google.com) or Google Workspace environments with Gemini access.

---

## Setup

1. Go to [gemini.google.com](https://gemini.google.com).
2. Click **Gems** in the left sidebar (requires Gemini Advanced).
3. Click **New Gem**.
4. Give it a name: `CTI Fusion Analyst`.
5. Open `gem_instructions.md` from this folder.
6. Copy the full contents and paste into the **Instructions** field.
7. Click **Save**.

The gem is now available from your Gems list. Select it before starting any CTI analysis session.

---

## Usage

1. Open the CTI Fusion Analyst gem from your Gems list.
2. Paste the full text of your threat report into the chat.
3. Stage 1 Core Analysis is produced first -- review it before requesting deliverables.
4. Request deliverables by name: "Generate the Threat Assessment", "Generate the Executive Brief", etc.

Tips:
- Paste the full report text. Do not paste a fragment or summary.
- For PDF reports: open the PDF, select all text, copy and paste. Or use Google Drive to open the PDF and extract the text.
- Multiple related reports (same actor or campaign): paste them together in one message.
- Multiple unrelated reports: the gem will ask how you want to proceed.

---

## Deliverables

| Deliverable | Audience | When Generated |
|-------------|----------|----------------|
| Core Analysis | CTI analyst (review gate) | Always, produced first |
| Threat Assessment | CTI team, operational leadership | Always |
| Executive Brief | Senior leadership | Always |
| Risk Mitigation Plan | All teams | Always |
| Threat Hunt Hypothesis | Hunt and IR teams | When behavioral TTPs are huntable |
| Red Team Emulation Plan | Offensive and purple teams | When TTP fidelity supports emulation |
| Patch Notification | IT, system owners | When CVEs are present in source |

---

## Notes on Gemini vs. Claude

Gemini and Claude handle long documents differently. For best results:
- Use Gemini 1.5 Pro or Gemini 2.0 (larger context window handles longer reports better).
- If the gem produces truncated output, try splitting the request: ask for Core Analysis first, then each deliverable separately.
- ATT&CK technique selection accuracy varies by model. Always validate mappings against the source document.

---

## Security Disclaimer

This gem assists qualified security professionals in processing threat intelligence. It is not a replacement for human analyst judgment. All outputs require human review before dissemination or operational use. AI-generated detection rules must be validated by a qualified detection engineer before deployment. Nothing generated is guaranteed to be complete, accurate, or error-free.
