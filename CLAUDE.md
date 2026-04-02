# C4C Bootcamp

Teaching materials for Code for Compassion Campus bootcamps. Turns developers into advocacy technologists using real movement data and APIs. Part of the Open Paws developer pipeline (Layer 1).

## Quick Start

Notebooks are designed for Google Colab -- open directly via GitHub URL, no local setup needed.

For local development:
```bash
pip install jupyter matplotlib requests
jupyter notebook
```

## Architecture

```
module-2/                        # Coding Foundations module
├── notebooks/                   # 3 Google Colab notebooks (Python 3)
│   ├── module-2-1-task-coding-demo.ipynb      # Data exploration, matplotlib, FAO data
│   ├── module-2-2-api-exercise.ipynb          # HTTP, JSON, REST APIs, OpenFoodFacts
│   └── module-2-3-openrouter-ai-for-advocacy.ipynb  # LLM APIs, tokens, cost, prompts
├── project-pitches/             # Fork-branch-PR exercise (publishable as separate repo)
│   ├── pitches/                 # Student pitch submissions
│   ├── CONTRIBUTING.md          # Student workflow instructions
│   └── .github/PULL_REQUEST_TEMPLATE.md
└── vibe-coding-demo/
    └── demo-script.md           # 60-90s screen-recording demo script
```

## Key Files

| File | Purpose |
|------|---------|
| `module-2/notebooks/*.ipynb` | Core teaching notebooks (Colab) |
| `module-2/project-pitches/README.md` | Student-facing GitHub exercise instructions |
| `module-2/project-pitches/CONTRIBUTING.md` | Fork/branch/PR workflow guide |
| `module-2/vibe-coding-demo/demo-script.md` | Reproducible vibe coding demo |
| `.gitmodules` | Submodule references |

## Development

- **Tech stack:** Python 3, Google Colab, OpenRouter, OpenFoodFacts API, Our World in Data
- **Adding modules:** Create `module-N/` directory following the existing pattern
- **Adding notebooks:** Place in `module-N/notebooks/`, ensure they run in Colab without local deps
- **Project pitches directory** is designed to be published as a separate repo (`c4c-project-pitches`) for students to fork

## Organizational Context

**Layer:** 1 | **Lever:** Strengthen | **Integration:** Curriculum content for the bootcamp pipeline

This is the teaching content that turns developers into advocacy technologists. Entry point of the Layer 1 flywheel (Bootcamp → Hackathon → Guild → RDP). The India community launch (May 2026, Bengaluru + Mumbai) will use these materials.

**Settled decisions affecting this repo:**
- **2026-04-02: Bootcamp identity framing** — Month 1 introduces advocacy context through real APIs (FAO slaughter data, OpenFoodFacts) and the ubiquitous language dictionary framed as practical communication. No explicit liberation rhetoric in early modules. Liberation framing develops through the work.
- **2026-04-02: Graze-CLI architecture** — Graze-CLI will integrate as a CLAUDE.md template / Claude Code extension. Do NOT write it into curriculum until it has been smoke-tested on a non-core-team machine.
- **2026-03-25: Graze-CLI needs smoke test before curriculum** — Sam coordinates; bootcamp launch is not blocked by this.

**Relevant strategy documents:**
- `programs/developer-training-pipeline/guild/operations.md` — full Guild pipeline
- `programs/developer-training-pipeline/india-community/community-strategy.md` — May 2026 India launch
- `ecosystem/repos.md` — `structured-coding-with-ai` should be referenced in bootcamp curriculum

**Current status:** Active. Tutorial quest content due 2 weeks before May 2026 launch (Abid owns). Bootcamp launch is not blocked by Graze-CLI smoke test — those are parallel tracks.

## Development Standards

### 10-Point Review Checklist (ranked by AI violation frequency)

1. **DRY** — AI clones code at 4x the human rate. Search before writing anything new
2. **Deep modules** — Reject shallow wrappers and pass-through methods. Interface must be simpler than implementation
3. **Single responsibility** — Each function does one thing at one level of abstraction
4. **Error handling** — Never catch-all. Every catch block must handle specifically
5. **Information hiding** — Don't expose internal state. Mask API keys (last 4 chars only)
6. **Ubiquitous language** — Use movement terminology consistently. Never let AI invent synonyms for domain terms
7. **Design for change** — Abstraction layers and loose coupling
8. **Legacy velocity** — Use characterization tests before modifying existing notebooks
9. **Over-patterning** — Simplest structure that works
10. **Test quality** — Every test must fail when the covered behavior breaks

### Quality Gates

- **Desloppify:** `desloppify scan --path .` — minimum score ≥85
- **Speciesist language:** `semgrep --config semgrep-no-animal-violence.yaml` on all notebook and docs edits
- **Two-failure rule:** After two failed fixes on the same problem, stop and restart with a better approach

### Seven Concerns — Critical for This Repo

All 7 concerns apply. Highlighted critical ones:

- **Advocacy domain** (critical) — Bootcamp materials DEFINE how new developers learn movement terminology. Use precise terms: **farmed animal** (not "livestock"), **factory farm** (not "farm"), **slaughterhouse** (not "processing facility"). The ubiquitous language dictionary should be introduced in Month 1.3.
- **Accessibility** (critical) — Content is for India developers on constrained connections. Notebooks must run on Google Colab free tier. Minimize large downloads.
- **Emotional safety** — FAO slaughter data produces numbers representing animal deaths. Frame appropriately for students encountering this data for the first time.
- **Cost optimization** — OpenRouter usage in notebooks must use free or cheapest capable models. Students should not face unexpected API costs.
- **Security** — API keys in notebooks must use environment variables or Colab secrets, never hardcoded.

### Advocacy Domain Language

Bootcamp materials shape how the next cohort thinks. Use these terms precisely:
- **Farmed animal** — not "livestock" (industry framing normalizes commodification)
- **Factory farm** — not "farm" (scale and conditions matter)
- **Slaughterhouse** — use precisely in any data analysis context
- **Campaign** — organized advocacy effort (not "project")
- **Activist** — person engaged in advocacy work (not "user")

### Structured Coding Reference

For tool-specific AI coding instructions (Claude Code rules, Cursor MDC, Copilot, Windsurf, etc.), copy the corresponding directory from `structured-coding-with-ai` into this project root.
