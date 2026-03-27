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
