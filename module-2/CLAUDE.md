# Module 2 — Coding Foundations

The first hands-on coding module of the C4C bootcamp. Students go from zero to making real API calls and LLM requests — all using advocacy data and movement APIs.

## Structure

```
module-2/
├── notebooks/          # 3 Google Colab teaching notebooks
├── project-pitches/    # GitHub fork/branch/PR exercise (publishable as c4c-project-pitches)
└── vibe-coding-demo/   # Prompt examples for live/recorded vibe coding session
```

## Subdirectory Docs

| Directory | CLAUDE.md | What It Covers |
|-----------|-----------|----------------|
| `notebooks/` | [`notebooks/CLAUDE.md`](notebooks/CLAUDE.md) | Per-notebook summaries: what each teaches, APIs used, key concepts |
| `project-pitches/` | [`project-pitches/CLAUDE.md`](project-pitches/CLAUDE.md) | GitHub workflow exercise, file inventory, instructor notes |
| `vibe-coding-demo/` | [`vibe-coding-demo/CLAUDE.md`](vibe-coding-demo/CLAUDE.md) | Demo script contents, how to run the session, pedagogical purpose |

## Learning Arc

1. **Vibe coding demo** — Show AI building real advocacy tools to motivate the module
2. **Notebook 1** (Task Coding Demo) — Cell-by-cell execution with FAO slaughter data
3. **Notebook 2** (APIs for Advocacy) — HTTP, JSON, REST with OpenFoodFacts
4. **Notebook 3** (AI for the Movement) — LLM API calls, tokens, cost, system prompts
5. **Project pitches** — GitHub workflow exercise: fork → branch → commit → PR → review → merge

## Key APIs Used in This Module

| API | Purpose | Auth |
|-----|---------|------|
| Our World in Data CSV | FAO global slaughter data | None |
| OpenFoodFacts v2 | Vegan product checker by barcode | None |
| JSONPlaceholder | POST practice (fake API) | None |
| OpenRouter | LLM calls (GPT-4o-mini, Haiku, Sonnet) | API key via Colab Secrets |

## Cross-References

- Root context: [`../../CLAUDE.md`](../../CLAUDE.md)
- India launch using these materials: `programs/developer-training-pipeline/india-community/community-strategy.md`
- Guild pipeline this feeds into: `programs/developer-training-pipeline/guild/operations.md`
