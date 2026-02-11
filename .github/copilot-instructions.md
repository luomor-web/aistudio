<!-- Copied/created for AI coding agents: concise, actionable guidance for this repo -->
# Copilot instructions — AI Studio

Purpose
- Short: Help an AI assistant be immediately productive in this repo (a small static "AI Studio" personal site).

Big picture (what this project is)
- Single-page static website (no build toolchain). Core files: `index.html`, `style.css`, `script.js` and a short `README.md` in `docs/`.
- UX-focused: large CSS codebase (2000+ lines) implements visual/animation system; JS is vanilla DOM code that injects a small `projects` data array and handles interactions (loader, cursor follower, contact copy, smooth scroll).
- There is an `openclaw/` folder containing an installer script (`install.sh`) for an external tool used by the author — not part of the website runtime but useful for local developer tooling.

Where to start (commands)
- Run locally (static server):
  - `python3 -m http.server 8080` (works in repo root)
  - or `npx serve` if you prefer Node-based static server
- No build step, no bundler. Edit files and refresh browser.

Key files & responsibilities
- `index.html`: semantic markup, hero structure, references to Google Fonts and `lucide-static` icons via CDN.
- `style.css`: main styling and animation system. Contains CSS variables in `:root` (colors, gradients, fonts) — change visual theme here. Avoid wholesale reformatting; edit targeted selectors like `.card`, `.hero`, `.cursor-follower`.
- `script.js`: data-driven pieces (see `projects` array at top). Functions to know: `renderProjects()`, `initLoader()`, `initCursor()`, `initCopyContact()`, `initScrollReveal()`; `DOMContentLoaded` boots everything.
- `docs/README.md` and top-level `README.md`: project description and quick-start notes maintained by the author.
- `openclaw/install.sh`: installer and helper for OpenClaw (external CLI); useful for onboarding if you need that tooling.

Project-specific conventions & patterns (examples)
- Data-first UI: add or update entries in `script.js` `projects` array — UI will auto-render into `#projectGrid` via `renderProjects()`.
  - Example: to add a project, append a JS object: `{ name: "New", desc: "...", url: "https://...", code: "15", tags: ["Tag"] }`.
- Copy-to-clipboard contact cards: elements with `data-copy` (in `index.html`) are wired by `initCopyContact()` in `script.js` — change text by editing the `data-copy` attribute or visible `.contact-value` content.
- Visual theming: modify CSS variables in `:root` at top of `style.css` (e.g., `--gradient-primary`, `--glow-purple`) to change colors globally.
- Cursor & loader: custom cursor is `.cursor-follower`, loader is `#loader` (toggled by `.hidden`); test changes by reloading and observing transitions.

Integration points & external dependencies
- Fonts: Google Fonts link in `index.html`. Icons: `https://unpkg.com/lucide-static@latest/font/lucide.css`.
- External links in `projects` may point to other services (e.g., `Gemini` entry pointing at `chatgpt.luomor.com`) — check `script.js` for outbound URLs before editing.
- `openclaw/install.sh` contains many helpful shell examples for installing OpenClaw (npm/pnpm) — run it only if you trust and need the tool.

Development & debugging notes
- No tests or CI configured in this repo. Use browser DevTools for JS/CSS debugging.
- Console helpers: `script.js` logs a load message on DOMContentLoaded. Use `console.log` to add short debug traces.
- Because `style.css` is large, prefer adding small supplementary styles or scoped overrides rather than reformatting the file.

When modifying code
- Keep changes minimal and targeted: e.g., change `projects` array or CSS variables rather than rewriting the entire CSS file.
- Preserve inline structure: `script.js` is plain JS (no modules); do not assume bundling or import semantics.

If you need to make a larger change
- Create a short PR with: summary, files changed, visual screenshots (if UI), and steps to reproduce locally (server command above).

Ask maintainers when
- You need guidance on visual/UX intent for animation timing or color choices.
- A change touches external integrations (OpenClaw, third-party services) or requires secrets/credentials.

Example quick tasks for an AI agent
- Add a new project card: edit `script.js` → `projects` array and verify render in `#projectGrid`.
- Update email/contact copy: edit `index.html` `.contact-card[data-copy]` attributes and visible `.contact-value` text.
- Tweak global theme color: update `--gradient-primary` in `style.css` `:root` and reload.

If anything here is unclear or you want deeper coverage (e.g., CSS areas to avoid touching, or typical deploy target), tell me what to expand and I will iterate.
