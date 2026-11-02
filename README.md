# Syna — Stay close, even off-grid

13-slide, five-minute HTML project proposal. Open `index.html` directly in a modern browser, or serve this directory with `python3 -m http.server 8000` and visit http://localhost:8000.

## Controls
Arrow keys / Space / PageUp / PageDown: navigate. Home/End: first/last. Swipe left/right or use the mouse wheel. F: fullscreen. N: speaker notes. R: replay animation. E: inline text editing. Ctrl/Cmd+S: download edited HTML; Save button does the same. Downloads do not overwrite the source file automatically. Hover near the bottom to reveal controls.

Use `?static` for immediate final animation states; `#5` opens slide 5. Print styles lay out one slide per page. Read `docs/speaker-notes.md` for the 300-second script, `docs/brief-draft.md` for content decisions and placeholders, and `docs/design-system.md` for the brand system.

`sources/` preserves the supplied PDFs and rubric image. `.agents/skills/frontend-slides/` vendors the authoring skill; `AGENTS.md` requires its use. No framework, npm install or build pipeline required. Google Fonts are embedded by the font-bundling helper when available, enabling offline playback.

## Before presenting
Replace the three skills/experience placeholders and confirm member names. The animated interfaces and numerical readings are illustrative concept visuals, not a functional Android demo. Follow the supplied brief for nearby-range, stale-coordinate, privacy and sensor constraints.


## PDF download
Open syna-presentation.pdf for the 13-page widescreen static export with selectable text. The HTML retains animations. For a fresh export after edits, use your browser Print command, enable background graphics, and save as PDF; the print stylesheet creates one slide per page.
