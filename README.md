# C4C Bootcamp

**Teaching developers to build AI tools for animal liberation, climate action, and AI safety.**

Code for Compassion Campus runs intensive bootcamps that turn developers into advocacy technologists. This repository contains the teaching materials, exercises, and demo scripts used across the curriculum.

Every exercise uses real advocacy data, real movement APIs, and real problems. No generic weather apps. No toy examples. Students build tools that matter from day one.

## Repository Structure

```
module-2/
├── notebooks/
│   ├── module-2-1-task-coding-demo.ipynb
│   ├── module-2-2-api-exercise.ipynb
│   └── module-2-3-openrouter-ai-for-advocacy.ipynb
├── project-pitches/
│   ├── README.md
│   ├── CONTRIBUTING.md
│   ├── pitches/
│   └── .github/PULL_REQUEST_TEMPLATE.md
└── vibe-coding-demo/
    └── demo-script.md
```

## Module 2 — Coding Foundations

### Notebooks (Google Colab)

Three teaching notebooks designed for Google Colab. Students open them directly from GitHub and save a copy to their own Drive.

| Notebook | What It Teaches | Data/APIs Used |
|----------|----------------|----------------|
| Task Coding Demo | Cell-by-cell execution, data exploration, matplotlib | FAO animal slaughter data via Our World in Data |
| APIs for Advocacy | HTTP methods, JSON parsing, REST APIs | OpenFoodFacts (vegan product checker), JSONPlaceholder |
| AI for the Movement | LLM API calls, tokens, cost, system prompts | OpenRouter (GPT-4o-mini, Claude Haiku, Claude Sonnet) |

### Project Pitches (GitHub Exercise)

A standalone exercise repository where students practice the fork → branch → commit → PR → review → merge workflow. Instead of adding their names to a list, students pitch a project idea — a tool for animal advocacy, climate action, or AI safety.

The `project-pitches/` directory contains all the files needed to set up the `c4c-project-pitches` repository as a separate repo for students to fork. See the README inside that directory for the full student-facing instructions.

### Vibe Coding Demo

A reproducible demo script for screen-recording a 60–90 second vibe coding session. Builds an advocacy-relevant web tool using AI code generation to demonstrate rapid prototyping.

## How to Use These Materials

**Instructors:** Clone this repo. Notebooks can be opened directly in Colab via GitHub URL. The project-pitches directory should be published as a separate repo (`c4c-project-pitches`) for students to fork.

**Students:** Your instructor will share direct links to each notebook and the project pitches repo. You don't need to clone this repository.

## Tech Stack

- Python 3 (notebooks)
- Google Colab (execution environment)
- OpenRouter (LLM API gateway)
- OpenFoodFacts API (product data)
- Our World in Data (animal agriculture statistics)
- GitHub (version control exercise)

## License

MIT License. See [LICENSE](LICENSE).

Built by Open Paws for the animal liberation movement.
