# CTI Fusion Analyst -- LM Studio Presets

Seven focused system prompts for LM Studio. Each preset does one job from a raw source document. No preset depends on output from another. The analyst selects the preset matching their output goal, pastes the source document, and runs.

Works with any instruction-tuned model. Designed and tested on Gemma 3n E4B (Q4_K_M) on a CPU-only machine.

---

## Setup

### Step 1 -- Install LM Studio

Download from [lmstudio.ai](https://lmstudio.ai) and install a compatible model (Q4_K_M recommended for 16 GB RAM).

### Step 2 -- Configure LM Studio settings

Apply these settings in LM Studio before loading any preset (Developer tab or Chat settings):

```
n_ctx:         4096
n_threads:     [your physical core count -- not logical/hyperthreaded]
n_batch:       256
GPU offload:   0 (unless you have a dedicated GPU)
Flash Attn:    On
KV cache:      Q8_0
mmap:          On
mlock:         Off
Max output:    2048
Temperature:   0.15
Top-P:         0.90
Top-K:         40
Min-P:         0.05
Repeat pen:    1.10
```

Verify the chat template matches your model family. Wrong template is the most common cause of poor output. In LM Studio, check Model Info -- the template should say Gemma, Llama 3, Qwen, Phi, or the appropriate family name.

### Step 3 -- Create presets

Open `CTI_Preset_Library.md`. For each preset:

1. In LM Studio, open the Chat tab.
2. Click the system prompt area and clear any existing content.
3. Find the preset in the library (e.g., "Preset 1 -- CTI Core Analysis").
4. Copy everything between the four-backtick code fences under "PASTE THIS".
5. Paste into the LM Studio system prompt field.
6. Set sampling parameters as listed in Step 2.
7. Click the preset dropdown (top right of system prompt panel) and choose **Save as new preset**.
8. Name it exactly as suggested (e.g., `CTI - 1 Core Analysis`).
9. Repeat for each of the seven presets.

Presets are saved to `%APPDATA%\LM Studio\presets\` on Windows and can be version-controlled or copied between machines.

---

## Usage

**Recommended workflow:**

1. Start with `CTI - 1 Core Analysis` -- load the source document, run it, review the output.
2. The Core Analysis produces the IOC table and ATT&CK mapping that other presets reference.
3. Switch to the preset for the deliverable you need.
4. Paste the same source document and run.
5. Start a new chat when switching presets -- do not switch presets mid-conversation.

**Preset reference:**

| Preset | Output | Audience |
|--------|--------|----------|
| CTI - 1 Core Analysis | ATT&CK mapping, IOC table | CTI analyst (review gate) |
| CTI - 2 Detection Rules | Sigma rules | Detection engineers |
| CTI - 3 Threat Assessment | Threat picture | CTI team, leadership |
| CTI - 4 Executive Brief | Under one page, no jargon | Senior leadership |
| CTI - 5 Risk Mitigation | Owner-assigned actions | All teams |
| CTI - 6 Threat Hunt | Hunt procedures | Hunt and IR teams |
| CTI - 7 Patch Notification | CVE remediation notice | IT, system owners |

---

## Model Swap Notes

These presets work on any instruction-tuned model. When changing models:

- Verify the chat template matches the new model family.
- Adjust n_ctx to what fits in your RAM (Q4_K_M, 7B model needs ~6 GB; 3B needs ~2.5 GB).
- Temperature 0.15 / top-p 0.90 / min-p 0.05 works across most instruction-tuned models for analytical work.
- Min-P is only applied by llama.cpp-based backends (which LM Studio uses) -- leave it set.
- For models larger than 7B on 16 GB RAM, reduce n_ctx to 2048 or use Q3_K_M quant.
- For models smaller than 3B, expect more errors in ATT&CK technique selection and Sigma syntax -- spot-check carefully.

Models known to work well for CTI analysis on CPU:
- Gemma 3n E4B (Q4_K_M) -- tested, designed for this hardware profile
- Llama 3.2 3B Instruct (Q4_K_M) -- fast, good instruction following
- Qwen 2.5 3B Instruct (Q4_K_M) -- strong on structured output
- Mistral 7B Instruct (Q4_K_M) -- best quality, slower on CPU

---

## Upgrading to Open WebUI (Optional)

For a skill-selector UI, file attachments with RAG, and persistent conversations, install [Open WebUI](https://docs.openwebui.com/) in front of LM Studio:

```
docker run -d -p 3000:8080 --add-host=host.docker.internal:host-gateway \
  -v open-webui:/app/backend/data --name open-webui \
  ghcr.io/open-webui/open-webui:main
```

Enable LM Studio's local server (Developer tab -> Start Server, exposes `http://localhost:1234/v1`). In Open WebUI, add a connection to `http://host.docker.internal:1234/v1` and create one "Model" per preset. This gives you a dropdown to select presets and the ability to attach reference files for RAG.

---

## Security Disclaimer

All outputs from local models require human analyst review before dissemination or operational use. Local models produce more errors in ATT&CK technique selection and Sigma syntax than cloud models. Spot-check at minimum 3 ATT&CK rows and 3 IOCs against the source document before using any output. Never deploy AI-generated detection rules to production without review by a qualified detection engineer.
