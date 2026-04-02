# Module 2 — Project Pitches

A GitHub workflow exercise where students practice fork → branch → commit → PR → review → merge using real content: pitching an advocacy tech project idea.

This directory is designed to be published as a separate repo (`c4c-project-pitches`) so students can fork it independently. All files here are student-facing.

## Files

| File | Purpose |
|------|---------|
| `README.md` | Student-facing instructions — the full 7-step workflow (fork, branch, write, commit, PR, review, merge) with a pitch template |
| `CONTRIBUTING.md` | Branch naming conventions, commit message format, what good PR review looks like, merge conflict guidance |
| `.github/PULL_REQUEST_TEMPLATE.md` | PR template students fill in: pitch summary, category checkboxes, submission checklist, questions for reviewers |
| `pitches/example-sanctuary-supply-tracker.md` | Example pitch: a supply-sharing platform for animal sanctuaries to match surplus and need by location |
| `pitches/example-veg3-advocacy-assistant.md` | Example pitch: VEG3 AI chatbot for animal advocates — evidence-based counter-arguments, Telegram + web + API |
| `pitches/.gitkeep` | Keeps the `pitches/` directory tracked in git before student submissions exist |

## What Students Do

1. Fork this repo to their own GitHub account
2. Create a branch named `pitch/short-description`
3. Add a file to `pitches/` using the template in README.md
4. Commit with message `Add pitch: [project name]`
5. Open a PR back to the original repo
6. Review at least one classmate's pitch
7. Merge after approval

## Pedagogical Purpose

This exercise teaches the professional open-source contribution workflow. It replaces "add your name to a list" exercises with something substantive: students contribute an idea with real advocacy value. The two example pitches (`example-sanctuary-supply-tracker.md` and `example-veg3-advocacy-assistant.md`) give students a concrete quality bar and show the range of projects in scope.

## Instructor Notes

- Publish `project-pitches/` as a separate repo (`c4c-project-pitches`) before bootcamp starts — students fork from that repo, not from `c4c-bootcamp`
- Example pitches stay in the repo as permanent reference, not as student submissions
- Merge conflicts are intentional learning opportunities — cover resolution in the next session, do not pre-resolve
- The PR template enforces the checklist: pitch file in correct folder, template used, commit message format, classmate review done

## Cross-References

- Parent module: `../` (module-2)
- Notebooks introducing the APIs referenced in many pitches: `../notebooks/`
- Vibe coding demo showing rapid prototyping: `../vibe-coding-demo/demo-script.md`
