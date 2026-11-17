# AGENTS.md — NTHU Study Notes

## Purpose
Build a small, reusable learning website for an NTHU EECS student. Explain difficult university subjects in clear, beginner-friendly English with short examples and quick self-check questions. The site is a learning resource, not an official university website.

## Technology and deployment
- Use a static website with no build step and no external dependencies.
- GitHub Pages must be able to serve `index.html` from the repository root.
- Keep the site accessible on mobile and desktop.
- Use semantic HTML and vanilla CSS/JavaScript; never require API keys or paid services.

## Project structure
- `index.html` — navigation, layout, styles, content data and client-side rendering.
- `AGENTS.md` — rules for humans and AI contributing to the project.
- `README.md` — project description, instructions and deployment.
- If the site grows, split styles into `assets/styles.css` and content into `data/notes.js` without changing page behavior.

## Visual style
- Clean academic dashboard with a dark navy background, soft blue and mint accents, rounded cards and generous whitespace.
- English text, with technical terms explained at first mention.
- Use short headings, high-contrast text and clearly labeled links/buttons.
- Keep header/navigation, note-card layout and footer consistent across notes.
- Respect reduced-motion preferences.

## Content schema and page rules
Notes live in the `notes` array in `index.html`. Each new note MUST be an object with:
- `slug`: unique lowercase kebab-case identifier (e.g. `cache-memory`).
- `subject`: existing subject label or a clear new one.
- `title`: concise title, ideally under 65 characters.
- `level`: `Beginner` or `Intermediate`.
- `summary`: 1–2 plain-English sentences.
- `concept`: clear explanation in original words (2–5 sentences).
- `example`: one worked example or practical scenario.
- `question`: one self-check question.
- `answer`: correct answer and short rationale.

Each entry automatically becomes a searchable home-page card and a dedicated hash-addressable page (`#note/slug`). Do not hand-copy card HTML for each entry.

## AI contribution workflow
1. Read AGENTS.md and inspect existing notes before editing.
2. Ask which topic and learner level are desired if unspecified; otherwise make a sensible beginner-level choice.
3. Add ONE valid object to the `notes` array following the schema. Do not duplicate a slug.
4. Use correct factual concepts; show units in numerical examples and verify any formulas before publishing.
5. Keep original phrasing; do not paste copyrighted lecture slides or private student information.
6. Reuse existing rendering, navigation, design tokens and components. Do not add frameworks unless essential.
7. Check search, subject filters, card links, back navigation and reveal-answer behavior.
8. Verify the page in a browser at desktop and mobile sizes; check console errors and missing content.
9. Update README only when setup, features or file structure changes.
10. Never expose tokens, passwords, personal health information or protected class materials.

## Acceptance checklist
- [ ] Each note has all nine required fields and a unique slug.
- [ ] Search and subject filters find the new note.
- [ ] `#note/<slug>` opens the correct page, including via direct link.
- [ ] Example and self-check answer render and are readable.
- [ ] Works on narrow phones and wide desktops.
- [ ] Existing notes and layout remain functional.

## Example prompt to an AI agent
"Read AGENTS.md. Add a Beginner note called 'What Is Cache Memory?' to NTHU Study Notes. Follow the required schema, keep the visual design unchanged, include one real example and one self-check question, and verify the new page and search."