# Instructor Run-Through: Module 2 — Coding Foundations Notebooks

This document provides step-by-step instructions for instructors to run through all three Module 2 notebooks **before** teaching the session. Each notebook takes 45–90 minutes to complete. Total instructor prep time: ~3 hours.

Verify:
- All cells execute without errors on Colab free tier
- Charts render correctly
- API calls return expected data
- Student-facing instructions in each notebook are accurate

Common pitfalls and timing notes included for each.

## Preparation (5 min)

1. Open [Colab](https://colab.research.google.com) in incognito mode (fresh session, no cached secrets)
2. Add `OPENROUTER_API_KEY` to Secrets (left sidebar 🔑 icon) for Notebook 3
3. Fork this repo if testing student PR workflow

## Notebook 1: Task Coding Demo [~45 min]

**Colab link:** [module-2-1-task-coding-demo.ipynb](https://colab.research.google.com/github/Open-Paws/c4c-bootcamp/blob/main/module-2/notebooks/module-2-1-task-coding-demo.ipynb)

### Expected Flow
1. **Cell 1–2:** Imports + FAO CSV load → `df_animals` (shape: 1000+ rows, columns: Entity, Year, slaughtered_land_animals_tons)
2. **Cell 3:** Filter 2020+ → line chart (global slaughter trend ~60M tons)
3. **Cell 4:** Top 5 countries → bar chart (China, US, Brazil, India, Indonesia)
4. **Student task:** Compute EU share → expected ~12–15%

### Common Pitfalls
- CSV parse fails if Colab runtime restarted → Runtime → Restart & clear
- Matplotlib not rendering → `%matplotlib inline` auto-added by Colab

**Timing:** Demo Cells 1–3 live (10 min), students complete task (35 min)

## Notebook 2: APIs for Advocacy [~60 min]

**Colab link:** [module-2-2-api-exercise.ipynb](https://colab.research.google.com/github/Open-Paws/c4c-bootcamp/blob/main/module-2/notebooks/module-2-2-api-exercise.ipynb)

### Expected Flow
1. **Cell 1:** `requests.get('https://world.openfoodfacts.org/api/v2/product/3017620422003.json')` → `{'product': {'product_name': 'Nutella', 'labels_tags': ['en:palm-oil', 'en:non-vegan']}}`
2. **Cell 2:** Vegan checker function → `is_vegan(product)` → False for Nutella
3. **Cell 3:** JSONPlaceholder POST → `{'userId': 1, 'title': 'My advocacy tool', 'body': 'Farmed animal liberation', 'id': 101}`
4. **Student task:** Query 5 barcodes → vegan count

### Common Pitfalls
- 429 rate limit on OpenFoodFacts → add `time.sleep(1)` between calls
- JSONPlaceholder POST returns 201 → normal

**Timing:** Live demo vegan check (15 min), students barcode exercise (45 min)

## Notebook 3: AI for the Movement [~75 min]

**Colab link:** [module-2-3-openrouter-ai-for-advocacy.ipynb](https://colab.research.google.com/github/Open-Paws/c4c-bootcamp/blob/main/module-2/notebooks/module-2-3-openrouter-ai-for-advocacy.ipynb)

### Expected Flow
1. **Cell 1:** `openrouter_client.chat.completions.create(...)` → GPT-4o-mini response (~20 tokens, $0.00015)
2. **Cell 2:** Claude Haiku advocacy classification → 'high_relevance: factory farm exposure'
3. **Cell 3:** Token cost calc → ~50 input tokens, 30 output
4. **Student task:** Generate project idea → refine prompt

### Common Pitfalls
- Missing `OPENROUTER_API_KEY` → Colab Secrets (not hardcoded)
- Rate limit → free tier ~10 req/min, wait 60s
- High token cost → use 'mini'/'haiku' models

**Timing:** Live GPT/Claude demo (20 min), students prompt engineering (55 min)

## Post-Run Checklist

- [ ] All notebooks complete, no lingering errors
- [ ] Charts match expected (screenshot for reference if needed)
- [ ] API responses live/current (no 404s)
- [ ] Student tasks solvable in time allotted
- [ ] Project pitches exercise fork/PR tested

**Total session time:** 3.5–4 hours (90 min notebooks + 60 min pitches + breaks)

---

*Last verified: YYYY-MM-DD by Instructor Name*
