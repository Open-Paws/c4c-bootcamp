# Vibe Coding — Prompt Examples

**What is vibe coding?** You describe what you want in plain English, an AI builds it, and you judge the result by whether it works — not by reading the code. You iterate by refining your description, not by editing files.

**Your task:** Pick a tool below, try some of these prompts, and see what happens. Start with the bad prompts to feel the frustration, then try the good ones and notice the difference.

## Tools to Try

Use any of these — all have free tiers and generate working web apps from text:

| Tool | URL | Free Tier |
|------|-----|-----------|
| Lovable | lovable.dev | 5 edits/day |
| Bolt | bolt.new | 150k tokens/day |
| Replit | replit.com | Limited free |

## Example Prompts

Each example has a **vague** version and a **detailed** version. Try both and compare the results.

---

### 1. Animal Rescue Counter

**Vague prompt:**
> Make a page about an animal sanctuary

**Detailed prompt:**
> Build a single-page web app for a fictional animal sanctuary called "Safe Haven Farm." Show a grid of cards, one per species (cows, pigs, chickens, goats, sheep), each displaying the species name, an emoji, and a count of animals rescued this year. The counts should animate up from zero when the page loads. Use a warm colour palette with greens and earth tones. Below the grid, show a single total and a large "Sponsor an Animal" button.

**What to notice:** The vague prompt will produce *something*, but the AI decides all the details for you. The detailed prompt gives you something much closer to what you actually imagined.

---

### 2. Vegan Ingredient Checker

**Vague prompt:**
> Make a vegan ingredient checker

**Detailed prompt:**
> Build a single-page web app with a large text area where someone can paste a food ingredient list. When they click "Check," scan the text for common animal-derived ingredients (gelatin, casein, whey, carmine, shellac, lard, tallow, isinglass, cochineal, lanolin) and highlight each match in red with a tooltip explaining what it is and where it comes from. Show a verdict at the bottom: either "Appears vegan" in green or "Contains X animal-derived ingredients" in red. Clean minimal design, no backend needed — everything runs in the browser.

**What to notice:** "Vegan ingredient checker" could mean anything — a search engine, a barcode scanner, a database. The detailed prompt specifies exactly the interaction: paste text, highlight matches, show verdict.

---

### 3. Carbon Footprint Comparison

**Vague prompt:**
> Make a carbon footprint calculator

**Detailed prompt:**
> Build a single-page web app that compares the carbon footprint of common meals. Show two dropdown menus side by side — each lets you pick a meal (beef burger, chicken wrap, bean burrito, lentil curry, tofu stir-fry, veggie pasta). Below each dropdown, display the estimated CO2 in kg using a simple bar that fills proportionally. Between them, show the percentage difference. Use hardcoded data — no API needed. At the bottom, show a one-line source credit to Our World in Data.

**What to notice:** "Carbon footprint calculator" is an enormous scope — transport, energy, diet, housing. The detailed prompt narrows it to one specific, buildable interaction.

---

### 4. AI Risk Timeline

**Vague prompt:**
> Build something about AI safety

**Detailed prompt:**
> Build a single-page interactive timeline of key moments in AI safety. Include 8-10 entries: Turing's 1950 paper, Asimov's Three Laws, Bostrom's "Superintelligence" (2014), the OpenAI founding (2015), GPT-3 release (2020), the Pause AI open letter (2023), the EU AI Act (2024), and Anthropic's RSP framework. Each entry has a year, a title, and a two-sentence summary. Display them as a vertical scrollable timeline with dots on a centre line. Clicking an entry expands it to show the summary. Muted colour scheme, no images needed.

**What to notice:** "Something about AI safety" gives the AI zero direction. The detailed prompt specifies the content, the interaction pattern, and the visual style.

---

### 5. Protest Sign Generator

**Vague prompt:**
> Make an animal rights thing

**Detailed prompt:**
> Build a single-page web app that generates protest sign designs. The user types a short slogan (max 50 characters), picks a background colour from 5 preset options (red, black, green, purple, orange), and picks a font style (bold block letters, handwritten, or stencil). Show a live preview of the sign as a styled card that updates as they type. Include a "Download as PNG" button that saves the card as an image. Start with the placeholder text "Their body, not ours."

**What to notice:** "An animal rights thing" could be literally anything. The detailed prompt defines a specific tool with a clear user flow.

---

## Tips for Writing Good Vibe Coding Prompts

1. **Name the thing.** "A single-page web app" beats "a thing" or "something."
2. **Describe the interaction.** What does the user *do*? Type, click, select, scroll?
3. **Specify the data.** If it needs data, provide it inline or say "use hardcoded placeholder data." Don't assume the AI will find a working API.
4. **Constrain the scope.** One page, no backend, no login, no database. The smaller the scope, the better the result.
5. **Mention the visual style.** Even a few words ("clean and minimal", "dark mode", "warm earth tones") dramatically change the output.
6. **State what you DON'T need.** "No images needed," "no authentication," "everything client-side" prevents the AI from overbuilding.

## From Vibes to Structure

The prompts above already show the pattern: more detail up front = better results. But even the "detailed" prompts here are just scratching the surface. When you want to build something real — something reliable, something an organisation can depend on — you need to do more work *before* you ever ask the AI to generate code.

That's what we mean by **structured vibe coding**:

- **Write a project brief first.** A short document describing what you're building, who it's for, and what "done" looks like. Feed this to the AI as context.
- **Define your requirements.** Before generating anything, write out what the tool should do in specific, testable statements: "When the user pastes an ingredient list containing 'casein,' the word should be highlighted in red."
- **Write tests before code.** Describe the expected behaviour in plain language or simple test cases. Give these to the AI alongside your prompt so it has something to build *toward*.
- **Build in small pieces.** Instead of one massive prompt, break the project into components. Generate one piece, verify it works, then move to the next.
- **Keep a living spec.** As you iterate, update your documentation rather than stacking prompts on top of prompts. The AI works better with a clear, current document than a long chat history.

You don't need to learn to code to do any of this. You need to learn to **think structurally** about what you're building — and that's what the rest of this course teaches you.
