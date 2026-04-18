# AGENTS.md — C4C Bootcamp

## Summary

`c4c-bootcamp` is the teaching materials repository for Code for Compassion Campus bootcamps — the entry point of Open Paws' Layer 1 developer pipeline (Bootcamp → Hackathon → Guild → RDP). It contains three Google Colab notebooks, a GitHub workflow exercise (project pitches), and a vibe coding demo script, all built around real advocacy APIs and movement data. The May 2026 cohort launches in Bengaluru and Mumbai. The CLAUDE.md at the repo root is the authoritative agent context file; this AGENTS.md is its counterpart for non-Claude agent systems.

---

## Status

**Active Development** — Content is live and in use. The May 2026 India cohort is imminent. LMS course content on Campus (the wrapper around these notebooks) has no assigned author as of 2026-04-14 and is a blocker for the May cohort. Graze-CLI is not yet integrated into any curriculum material (smoke test on a non-core-team machine is a prerequisite). The no-animal-violence VS Code extension and pre-commit hook are not yet in curriculum.

**Change implications:** Any edit to a notebook must be verified to run end-to-end on Colab free tier before merging. Any new API introduced must be free-tier accessible or cost-free for students. Do not add Graze-CLI references until the smoke test passes.

---

## Curriculum Structure

```
module-2/                                      # Coding Foundations — only published module
├── notebooks/                                 # 3 Google Colab teaching notebooks
│   ├── module-2-1-task-coding-demo.ipynb      # FAO slaughter data, matplotlib, CSV parsing
│   ├── module-2-2-api-exercise.ipynb          # OpenFoodFacts, JSONPlaceholder, HTTP methods
│   └── module-2-3-openrouter-ai-for-advocacy.ipynb  # LLM API calls via OpenRouter
├── project-pitches/                           # GitHub fork/PR workflow exercise
│   ├── README.md                              # Student-facing step-by-step instructions
│   ├── CONTRIBUTING.md                        # Fork/branch/PR workflow guide
│   ├── pitches/                               # Student pitch submissions (Markdown files)
│   └── .github/PULL_REQUEST_TEMPLATE.md       # PR template for pitch submissions
└── vibe-coding-demo/
    └── demo-script.md                         # Prompt examples for live AI coding demo
```

**Agent context files (CLAUDE.md tree):**

| File | Covers |
|------|--------|
| `CLAUDE.md` | Root: full project context, org placement, settled decisions, India launch, quality gates |
| `module-2/CLAUDE.md` | Module 2 overview: learning arc, subdirectory index, API table |
| `module-2/notebooks/CLAUDE.md` | Per-notebook summaries: APIs, libraries, key concepts, dev notes |
| `module-2/project-pitches/CLAUDE.md` | File inventory, GitHub workflow steps, instructor notes |
| `module-2/vibe-coding-demo/CLAUDE.md` | Demo script contents, session flow, pedagogical purpose |

---

## Setup Commands

```bash
# Clone
git clone https://github.com/Open-Paws/c4c-bootcamp.git
cd c4c-bootcamp

# Local notebook development
pip install jupyter matplotlib requests
jupyter notebook

# Speciesist language check (run before any PR)
semgrep --config semgrep-no-animal-violence.yaml

# Quality scan
desloppify scan --path .   # minimum score ≥85
```

Students use Google Colab exclusively — no local setup required for learners. Colab URLs follow the pattern:
```
https://colab.research.google.com/github/Open-Paws/c4c-bootcamp/blob/main/module-2/notebooks/<name>.ipynb
```

---

## Architecture Decisions

**Notebook format (Google Colab):** All teaching notebooks target Colab free tier. This is a deliberate accessibility decision for the India cohort (constrained connections, no local dev environment assumed). Do not add dependencies that require local installation. Colab Secrets (`userdata.get(...)`) is the only approved mechanism for API keys — never hardcode credentials in cells.

**Real advocacy data from day one:** Every notebook uses real data (FAO slaughter statistics, OpenFoodFacts product data, peer-reviewed environmental footprint figures). This is an identity-formation decision, not just a pedagogy choice. Students encounter the scale of animal agriculture in their first coding exercise.

**OpenRouter as LLM gateway:** Notebook 3 uses OpenRouter rather than direct Anthropic or OpenAI APIs. This avoids vendor lock-in, gives students access to multiple models under one key, and allows cost comparison across providers. Default model is `openai/gpt-4o-mini` (cheapest capable model). Do not switch to a paid-by-default model without updating the cost-control checklist in the notebook.

**Project pitches as a separate publishable repo:** The `module-2/project-pitches/` directory is designed to be deployed as `c4c-project-pitches` — a separate GitHub repo students fork. This gives students a real fork target with a real contribution history. It is kept in this repo for instructor maintainability.

**No liberation rhetoric at the entry point:** Bootcamp materials use systems framing ("animal agriculture is an engineering problem") rather than explicit liberation language in early modules. Identity shift is a deliberate journey. See `CLAUDE.md` for the 2026-04-09 settled decision on identity framing.

**India-aware curriculum framing:** Dairy is the primary entry point (not meat) for the May 2026 Indian cohort. Economic framing ("meaningful AND paid") is required alongside cause framing. Anti-caste tone is a design-level principle, not a disclaimer. See `CLAUDE.md` India section for full detail.

---

## Key APIs and Data Sources

| API / Source | Used In | Auth | Cost |
|---|---|---|---|
| Our World in Data CSV (FAO slaughter data) | Notebook 1 | None | Free |
| OpenFoodFacts v2 | Notebook 2 | None | Free |
| JSONPlaceholder | Notebook 2 | None | Free |
| OpenRouter | Notebook 3 | API key (Colab Secrets) | Free tier available |

---

## Integration Points

- **C4C Campus (LMS):** Campus hosts the module/lesson/quiz wrapper around these notebooks. LMS content authorship for May 2026 cohort is currently unassigned (blocker — see status above).
- **Guild tutorial quests:** After bootcamp, graduates enter the Guild. Five tutorial quests are documented in `programs/developer-training-pipeline/guild/tutorial-quests.md` (strategy repo). Notebooks should reference these as the post-bootcamp on-ramp.
- **no-animal-violence GitHub Action:** `.github/workflows/no-animal-violence.yml` runs speciesist language checks on every PR. This is non-negotiable — do not disable.
- **Graze-CLI:** NOT yet integrated. Integration requires a smoke test on a non-core-team machine before any curriculum reference is added.
- **structured-coding-with-ai:** Tool-specific AI coding instructions (Claude Code rules, Cursor MDC, etc.) should be copied from `structured-coding-with-ai` repo into this project root when needed.

---

## Safe vs. Risky Changes

**Safe:**
- Editing prose in `demo-script.md` or `project-pitches/README.md`
- Fixing typos or updating terminology in any `.md` file
- Adding new pitch examples to `module-2/project-pitches/pitches/`
- Updating hardcoded environmental data in Notebook 2 with newer peer-reviewed figures (cite source)
- Adding new prompt examples to the vibe coding demo

**Requires care:**
- Editing notebook cells — verify the full notebook runs end-to-end in Colab free tier after any change
- Changing model names in Notebook 3 — check current OpenRouter model IDs and update the cost-control checklist
- Changing the OpenFoodFacts barcode in Notebook 2 — verify the product still exists and is correctly flagged as vegan/not vegan
- Adding new Python dependencies — must be available without pip install (pre-installed in Colab) or clearly documented as a `!pip install` cell

**Risky (requires explicit decision):**
- Adding Graze-CLI references — blocked until smoke test passes
- Adding the no-animal-violence VS Code extension or pre-commit hook to curriculum — requires a curriculum decision
- Adding liberation framing to early-module content — see identity-framing settled decision in `CLAUDE.md`
- Changing the project-pitches directory structure — may break the live `c4c-project-pitches` repo if it has already been published for a cohort
- Adding modules — must follow `module-2/` structure and include full CLAUDE.md tree

---

## Language Rules

All content must use domain-correct terminology:

- **Farmed animal** — not "livestock" (industry framing that normalises commodification)
- **Factory farm** — not "farm" (scale and conditions matter)
- **Slaughterhouse** — use precisely, not euphemisms
- **Campaign** — organised advocacy effort (not "project")
- **Sanctuary** — permanent animal care facility (not "shelter" or "foster")

The `no-animal-violence` semgrep ruleset enforces 65+ patterns on every PR. Run `semgrep --config semgrep-no-animal-violence.yaml` before submitting any pull request touching `.py`, `.ipynb`, `.md`, or config files.

---

## TODOs

- [ ] Assign LMS content author for May 2026 cohort (blocker — escalate if not resolved by April 15)
- [ ] Complete Graze-CLI smoke test on a non-core-team machine; then add curriculum references
- [ ] Add India-specific framing to Notebook 1 (dairy entry point, economic framing, Ambedkarite tone)
- [ ] Add Guild tutorial quest references to Notebook 3 (post-bootcamp on-ramp)
- [ ] Decide whether to introduce no-animal-violence VS Code extension and pre-commit hook in bootcamp
- [ ] Add Module 1 (non-coding foundations) materials when ready
- [ ] Add Module 3+ as curriculum develops
- [ ] Verify all notebook Colab URLs are still valid after any repo restructure
