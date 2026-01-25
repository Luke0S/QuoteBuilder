<!-- Auto-generated guidance for AI coding agents working on this repo. -->
# Copilot instructions for QuoteBuilder

Purpose
- Provide concise, actionable guidance for editing and extending this project.

Big picture
- This is a single-file static web app: `QuoteBuilder.html` contains the UI, styles, and JavaScript.
- UI is driven by DOM IDs/classes and inline scripts; key features include a "compare" mode, print/export, and a dynamic quote table.

Key files
- Primary: [QuoteBuilder.html](QuoteBuilder.html)

Project-specific patterns (search these exact tokens when exploring)
- DOM anchors & toggles: `#compare-section`, `body.compare-mode`, `#add-row-btn`, `#load-quote-btn`, `#export-pdf`.
- UI state classes: `.compare-link-wrapper.hidden`, `#compare-section.active`, `.toggle-slider.position-0/position-1`.
- The Sam's Club feature uses `.sams-club-benefits` and related `.sams-club-*` selectors — look here for special-case UI.

Developer workflows
- No build step or package manager. To run locally open `QuoteBuilder.html` in a browser or use a Live Server extension.
- Debugging: use the browser DevTools console and search for handlers in `QuoteBuilder.html` (look for element IDs above and for `document.addEventListener` / inline `onclick`).

Editing guidelines
- Prefer minimal, local edits: the codebase relies on initialization order in the HTML. If you extract JS to a new file, add the `<script src="...">` just before `</body>` and preserve the original inline init sequence.
- Keep CSS variables in the `:root` block (top of the file) for global theming changes.
- Preserve print-related CSS and selectors (they affect `#print-info-container` and export behavior).
- If adding external libraries, prefer CDN links in the `<head>` and call them from the inline script after they load.

Testing & verification (manual)
- Open the file in a browser and exercise these actions:
  - Toggle compare mode (check `body.compare-mode` and `#compare-section.active`).
  - Add a row (`#add-row-btn`), load a quote (`#load-quote-btn`), and export (`#export-pdf`).
  - Inspect console for errors and network panel for any external assets.

When to ask the repo owner
- If you need API endpoints, data persistence, or external integrations — none are present in the repo, ask for the intended backend or storage mechanism.

Notes for AI agents
- Look for logic by searching `addEventListener`, `querySelector`, and the IDs listed above inside `QuoteBuilder.html`.
- Avoid large behavioral changes without running the manual test steps above — small, incremental PRs are preferred.

If anything above is incomplete or you need more context (APIs, desired persistence, CI rules), ask the maintainer before large refactors.
