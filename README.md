# C4C Bootcamp

**Status:** ![Active Development](https://img.shields.io/badge/status-active%20development-yellow) | Part of the [Open Paws](https://github.com/Open-Paws) ecosystem

Teaching developers to build AI tools for animal liberation, climate action, and AI safety.

Code for Compassion Campus (C4C) runs intensive bootcamps that turn developers into advocacy technologists. This repository contains the teaching materials, exercises, and demo scripts used across the curriculum. Every exercise uses real advocacy data, real movement APIs, and real problems — no toy examples, no generic starter apps. Students build tools that matter from day one.

---

## What This Bootcamp Teaches

Students leave with the ability to:

- Fetch, parse, and visualise real-world advocacy datasets (FAO slaughter statistics, environmental footprint data)
- Call external APIs to build practical movement tools (food product checkers, LLM-powered assistants)
- Make direct LLM API calls, compare models, understand token economics, and control cost
- Use the professional open-source workflow (fork → branch → commit → PR → review → merge) to contribute to real repositories
- Rapidly prototype advocacy tools using AI-assisted code generation

The bootcamp is the entry point of the Layer 1 developer pipeline:

```
Bootcamp → Hackathon → Guild → Resident Developer Programme (RDP)
```

---

## Who This Is For

**Target audience:** Developers new to advocacy technology — typically engineers with some Python or web development experience who want to apply their skills to animal liberation, climate action, or AI safety.

**Skill level:** Beginner to intermediate. Module 2 (Coding Foundations) assumes familiarity with basic programming concepts but no prior experience with APIs or LLMs.

**Delivery context:** Live cohorts with an instructor. Notebooks are designed for Google Colab — no local setup required for students. The May 2026 cohort runs in Bengaluru and Mumbai.

---

## Curriculum Map

The curriculum is organised into numbered modules. Currently published:

### Module 2 — Coding Foundations

The first hands-on coding module. Students go from zero to making real API calls and LLM requests using advocacy data and movement APIs.

**Learning arc:**

| Step | Activity | What It Teaches |
|------|----------|----------------|
| 1 | Vibe Coding Demo | Show AI building real advocacy tools; motivate structured thinking |
| 2 | Notebook 1: Task Coding Demo | Cell-by-cell execution, CSV parsing, matplotlib, FAO slaughter data |
| 3 | Notebook 2: APIs for Advocacy | HTTP methods, JSON parsing, REST APIs, OpenFoodFacts |
| 4 | Notebook 3: AI for the Movement | LLM API calls, token economics, model comparison, system prompts |
| 5 | Project Pitches | Fork → branch → commit → PR → review → merge GitHub workflow |

**Notebooks (Google Colab):**

| Notebook | What It Teaches | Data / APIs |
|----------|----------------|-------------|
| [`module-2-1-task-coding-demo.ipynb`](module-2/notebooks/module-2-1-task-coding-demo.ipynb) | Task coding, data exploration, matplotlib charting | FAO animals-slaughtered data via Our World in Data CSV |
| [`module-2-2-api-exercise.ipynb`](module-2/notebooks/module-2-2-api-exercise.ipynb) | HTTP GET/POST, JSON parsing, REST APIs | OpenFoodFacts (vegan product checker), JSONPlaceholder, FAO/IPCC environmental data |
| [`module-2-3-openrouter-ai-for-advocacy.ipynb`](module-2/notebooks/module-2-3-openrouter-ai-for-advocacy.ipynb) | LLM calls, token economics, model routing, system prompts | OpenRouter (GPT-4o-mini, Claude Haiku, Claude Sonnet) |

**Supporting materials:**

| Directory | Contents |
|-----------|----------|
| [`module-2/project-pitches/`](module-2/project-pitches/) | Standalone GitHub workflow exercise — students fork, branch, commit, and open a PR to submit a project idea |
| [`module-2/vibe-coding-demo/`](module-2/vibe-coding-demo/) | Prompt examples for a 60–90 second live or recorded AI code-generation demo |

---

## Prerequisites

Students should have:

- A GitHub account
- A Google account (for Colab)
- Basic programming familiarity (variables, loops, functions in any language)
- An OpenRouter account for Notebook 3 (free tier is sufficient — API key loaded via Colab Secrets)

No local Python installation is required. All notebooks run on Google Colab free tier.

---

## Setup

### For Students

Your instructor will share direct links to each notebook and the project pitches repo. You do not need to clone this repository.

Open notebooks directly in Colab:

```
https://colab.research.google.com/github/Open-Paws/c4c-bootcamp/blob/main/module-2/notebooks/<notebook-name>.ipynb
```

For Notebook 3, add your OpenRouter API key to Colab Secrets (key icon in the left sidebar) under the name `OPENROUTER_API_KEY`. Never paste your key directly into a cell.

### For Instructors

Clone the repo:

```bash
git clone https://github.com/Open-Paws/c4c-bootcamp.git
cd c4c-bootcamp
```

For local notebook development:

```bash
pip install jupyter matplotlib requests
jupyter notebook
```

The `module-2/project-pitches/` directory is designed to be published as a separate repository (`c4c-project-pitches`) for students to fork. Copy the contents there before each cohort or point students to the live version.

---

## How to Work Through the Materials

**Recommended order for a cohort session:**

1. Instructor runs the **vibe coding demo** live or plays the recording — establishes what is possible and sets expectations for structured prompting
2. Students open **Notebook 1** in Colab, work cell by cell, complete the country-filter exercise at the end
3. Students open **Notebook 2**, step through each API call, complete the "your turn" exercises
4. Students open **Notebook 3**, load their API key via Colab Secrets, run the model comparison, build the VEG3 persona
5. Instructor publishes the **project pitches** repo — students fork it, write a pitch, open a PR, review a classmate's PR, merge

Each notebook takes approximately 45–90 minutes. The project pitches exercise takes approximately 60 minutes with instructor support.

---

## Connection to C4C Campus

The bootcamp delivers the hands-on coding component of the [Code for Compassion Campus](https://campus.openpaws.ai) curriculum. Campus hosts the LMS content (modules, lessons, quizzes) that wraps these materials. After completing the bootcamp, graduates are on-ramped into the **Guild** — a paid marketplace for advocacy technology quests.

Five tutorial quests are ready in `programs/developer-training-pipeline/guild/tutorial-quests.md` (strategy repo) and are referenced as the post-bootcamp on-ramp in the notebooks.

---

## Repository Structure

```
c4c-bootcamp/
├── module-2/
│   ├── notebooks/
│   │   ├── module-2-1-task-coding-demo.ipynb
│   │   ├── module-2-2-api-exercise.ipynb
│   │   └── module-2-3-openrouter-ai-for-advocacy.ipynb
│   ├── project-pitches/
│   │   ├── README.md                          # Student-facing instructions
│   │   ├── CONTRIBUTING.md                    # Fork/branch/PR workflow guide
│   │   ├── pitches/                           # Student pitch submissions
│   │   └── .github/PULL_REQUEST_TEMPLATE.md
│   └── vibe-coding-demo/
│       └── demo-script.md                     # Prompt examples for live demo
├── CLAUDE.md                                  # Agent context (authoritative project guide)
└── .github/workflows/
    ├── auto-merge.yml
    └── no-animal-violence.yml                 # Speciesist language check on PRs
```

---

## Tech Stack

| Technology | Role |
|------------|------|
| Python 3 | Notebook language |
| Google Colab | Execution environment (no local install required) |
| OpenRouter | LLM API gateway (GPT-4o-mini, Claude Haiku, Claude Sonnet) |
| OpenFoodFacts API | Vegan product data |
| Our World in Data | FAO animal agriculture statistics |
| GitHub | Version control exercise platform |

---

## Contributing

### Adding a Notebook

1. Place the notebook in `module-N/notebooks/` where N is the module number
2. Ensure it runs completely on Colab free tier with no local dependencies
3. Load any API keys via `google.colab.userdata.get(...)` — never hardcoded
4. Use domain-correct terminology: **farmed animal** (not "livestock"), **factory farm** (not "farm"), **slaughterhouse** (not "processing facility")
5. Update `module-N/notebooks/CLAUDE.md` with a summary row

### Adding a Module

Create `module-N/` following the structure of `module-2/`. Include a `CLAUDE.md` in the module root and in each subdirectory.

### Adding a Project Pitch

See [`module-2/project-pitches/README.md`](module-2/project-pitches/README.md) and [`module-2/project-pitches/CONTRIBUTING.md`](module-2/project-pitches/CONTRIBUTING.md) for the student-facing workflow.

### Code Quality

All pull requests are checked for speciesist language via the `no-animal-violence` GitHub Action. Run locally with:

```bash
semgrep --config semgrep-no-animal-violence.yaml
```

---

## License

MIT License. See [LICENSE](LICENSE).

Built by Open Paws for the animal liberation movement.
