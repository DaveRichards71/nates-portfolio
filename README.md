# CAD Portfolio — Scaffold

Design direction: pages read as engineering drawing sheets — graph-paper
background, a title block anchoring the bottom of every page (doubles as nav),
and the project index styled as a parts list rather than a card grid.

Live at https://DaveRichards71.github.io/nates-portfolio/ (GitHub Pages,
branch `main`, root). `.nojekyll` at repo root disables Jekyll — keep it.

## Structure
- `index.html` — project index (parts list). Add one `<tr>` per project.
- `style.css` — shared design system (colors/type as CSS variables at the top).
- `project-template.html` (repo root) — copy into `projects/`, rename, then
  fill in the callout strip, point `<model-viewer src>` at the project's
  `.glb`, and write the three note sections. Search the file for `TODO` and
  `REPLACE_WITH_MODEL` to find every spot to edit.
- `projects/` — one HTML page per project (paths inside use `../`).
- `assets/models/` — self-hosted `.glb` files loaded by `<model-viewer>`.

## Adding a project
1. Copy `project-template.html` into `projects/` and rename it.
2. Drop the `.glb` in `assets/models/`; set both `src` references to it.
3. Fill in `<title>`, `<h1>`, the callout strip, the three notes, and the
   title-block "Title" cell (search `TODO`).
4. Set the sheet number: `Sheet 00X` in the header and `X / N` in the footer.
   `N` = total sheets (index counts as sheet 001), so bump `N` on every page
   — including `index.html` — whenever the project count changes.
5. Add a `<tr>` to the parts list in `index.html` linking to the new page.

## Notes
- 3D viewer: self-hosted `.glb` via Google's `<model-viewer>` (not OnShape
  iframes). Each viewer has a text/download fallback for unsupported browsers
  and a JS error handler that swaps in a download link if the model fails.
- `<model-viewer>` needs `http://`/`https://`; opening a page via `file://`
  is blocked by CORS. Test locally with `python -m http.server`.
- Case-only file renames: Windows git ignores them but GitHub Pages (Linux)
  is case-sensitive. Use the two-step `git mv` trick or check `core.ignorecase`.
- Fonts + the model-viewer script load from CDNs — fine for GitHub Pages, but
  note the external dependency.

## Outstanding
- Add the remaining projects (see chat handoff): each needs its `.glb`, the
  callout/status values, and the three note sections.
- `repo-README.md` is a leftover GitHub-generated stub; fold it in or delete it.
