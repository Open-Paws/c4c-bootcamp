# Module 2 — Notebooks

Three Google Colab teaching notebooks for the Coding Foundations module. Each uses real advocacy data and real APIs. Designed to run in Colab free tier — no local setup required.

## Files

| File | What It Teaches | APIs / Data |
|------|----------------|-------------|
| `module-2-1-task-coding-demo.ipynb` | Task coding (cell-by-cell execution), data loading, filtering, matplotlib charting | FAO animals slaughtered data via Our World in Data CSV |
| `module-2-2-api-exercise.ipynb` | HTTP methods (GET, POST, PUT, DELETE), JSON parsing, REST APIs | OpenFoodFacts (vegan product checker), JSONPlaceholder (POST practice), hardcoded FAO/IPCC environmental data |
| `module-2-3-openrouter-ai-for-advocacy.ipynb` | LLM API calls, token economics, model comparison, system prompts | OpenRouter (GPT-4o-mini, Claude Haiku, Claude Sonnet) |

## Notebook Summaries

### module-2-1-task-coding-demo.ipynb — Task Coding Demo: The Scale of Animal Agriculture

Introduces "task coding" — running code one cell at a time, inspecting output before continuing. Students fetch global FAO slaughter data from Our World in Data, filter for world totals in the most recent year, compute per-second kill rates, then chart chicken slaughter over time (line chart) and all major species over time (stacked area chart). Final exercise: students filter for a country of their choice and generate a custom chart. Fallback hardcoded dataset included for offline use.

**Libraries:** `requests`, `csv`, `io`, `matplotlib`
**Data:** `https://ourworldindata.org/grapher/animals-slaughtered-for-meat.csv`
**Key concepts:** CSV parsing, dict filtering, matplotlib, data exploration

### module-2-2-api-exercise.ipynb — APIs for Advocacy

Covers how APIs work and why they matter for advocacy tools. Students make GET requests to OpenFoodFacts to check if a product is vegan (by barcode), extract JSON fields including vegan status and palm oil status, practice POST using JSONPlaceholder, parse hardcoded environmental data (livestock emissions, land use, water usage per kg of food) sourced from FAO/IPCC/Poore & Nemecek, and end with an OpenFoodFacts search exercise. Each step includes a "your turn" exercise.

**Libraries:** `requests`, `json`
**APIs:** OpenFoodFacts v2 (`world.openfoodfacts.org`), JSONPlaceholder (`jsonplaceholder.typicode.com`)
**Key concepts:** GET, POST, status codes, JSON traversal, HTTP error handling

### module-2-3-openrouter-ai-for-advocacy.ipynb — AI for the Movement

Students make their first LLM API calls. They load an OpenRouter API key from Colab Secrets (never hardcoded), draft a social media post about factory farming, generate a counter-argument response, inspect token usage and calculate per-call cost, compare three models (GPT-4o-mini, Claude Haiku, Claude Sonnet) on the same advocacy fact-check prompt, and build a VEG3 persona using a system prompt. Ends with a cost-control checklist.

**Libraries:** `requests`, `time`, `google.colab`
**APIs:** OpenRouter (`openrouter.ai/api/v1/chat/completions`)
**Models used:** `openai/gpt-4o-mini`, `anthropic/claude-3.5-haiku`, `anthropic/claude-sonnet-4`
**Key concepts:** API authentication, token economics, system prompts, model routing, cost control

## Development Notes

- All notebooks must run on Colab free tier. Do not add dependencies requiring local installation.
- API keys must use Colab Secrets (`userdata.get(...)`) — never hardcode keys in cells.
- Each notebook has a fallback path for network errors (especially notebook 1 which fetches a remote CSV).
- Use cheapest capable models for student exercises. Notebook 3 uses GPT-4o-mini by default.
- FAO/IPCC data in notebook 2 is hardcoded from peer-reviewed sources — cite them if updated.
- Use domain-correct terminology: **farmed animal** (not "livestock"), **factory farm** (not "farm"), **slaughterhouse** (not "processing facility").

## Cross-References

- Parent module: `../` (module-2)
- Exercise built on these APIs: `../project-pitches/` (students pitch tools using these APIs)
- Vibe coding demo: `../vibe-coding-demo/demo-script.md`
- Org context: `programs/developer-training-pipeline/india-community/community-strategy.md` (May 2026 launch)
