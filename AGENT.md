# AGENT.md — AI Agent Instructions for AI Studio

Purpose
- Short: Provide precise, actionable instructions for an AI coding agent working in this repository.

Scope & Big Picture
- This is a single-page static portfolio site. No build tools, no bundler.
- Runtime is the browser; key behavior is implemented in `script.js` and styling in a large `style.css` file.
- `openclaw/install.sh` is an installer script for an external tool; treat it as tooling, not part of the site runtime.

Primary agent responsibilities
- Make minimal, focused edits that preserve the site's visual/UX intent.
- Prefer small, targeted changes (edit `projects` array or CSS variables) over global refactors.
- When adding files or changing behavior, include a short test plan and the commands to validate locally.

How to modify files (rules)
- Use the repo `apply_patch` workflow to edit files. Keep patches minimal and contained to relevant files.
- Do NOT reformat `style.css` entirely. If you need CSS changes, add small scoped rules or edit the `:root` variables.
- `script.js` is plain ES5/vanilla JS; do not introduce module syntax or assume a bundler.
- When changing content in `index.html`, keep semantic structure intact (sections: `#home`, `#works`, `#about`, `#contact`).

Developer workflows / quick commands
- Run a local static server to preview changes:
  - `python3 -m http.server 8080`
  - or `npx serve`
- Open the page in a browser and use DevTools to inspect DOM/CSS and console logs.

Patterns & examples (do these for small tasks)
- Add a project card: edit `script.js` → `projects` array. Example object:
  `{ name: "New Project", desc: "Short description", url: "https://...", code: "15", tags: ["Tool"], featured: false }`
- Update contact copy: edit `index.html` contact card element with `data-copy="..."` and the visible `.contact-value` text.
- Theme tweak: edit `:root` variables in `style.css` (e.g. `--gradient-primary`, `--glow-purple`) and reload.

Testing & verification
- No automated tests exist. Verification is manual:
  1. Start local server (see commands above).
  2. Reload the page and confirm UI changes visually.
  3. Use browser console to check for runtime errors.

Commit & PR guidance
- Keep commits small and focused. Commit message format: `<area>: short description` (e.g., `ui: add Gemini project card`).
- For UI changes include a one-line test instruction and (optionally) a screenshot in the PR body.

Safety & integration notes
- External links and scripts: review outbound URLs in `script.js` before changing them.
- `openclaw/install.sh` may contain operations requiring sudo or network downloads — only run if you trust the source.

If unclear
- Ask for clarification when UX intent or color/animation timing is not obvious. Maintain the original look-and-feel unless asked to redesign.

Contact
- Repo owners: referenced in `README.md` (GitHub: `zhangchunsheng`, email: `1097692918@qq.com`).

If you want, I can also generate a short PR template or expand this with line-range cautions for `style.css`.
