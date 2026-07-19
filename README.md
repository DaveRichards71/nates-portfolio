# CAD Portfolio — Scaffold

Design direction: pages read as engineering drawing sheets — graph-paper
background, a title block anchoring the bottom of every page (doubles as nav),
and the project index styled as a parts list rather than a card grid.

## Structure
- `index.html` — project index (parts list). Add one `<tr>` per project.
- `style.css` — shared design system (colors/type as CSS variables at the top).
- `projects/project-template.html` — copy this per project, fill in the
  callout strip, swap the OnShape iframe `src`, write the three note sections.

## To do in Claude Code
1. `git init`, first commit, push to a new GitHub repo (`yourusername.github.io`
   for a root site, or any name for a project site).
2. Enable GitHub Pages in repo Settings -> Pages (source: branch `main`, root).
3. For each project: duplicate `projects/project-template.html`, rename,
   fill content, get the OnShape embed `src` (Share -> Public -> Embed in
   OnShape), and add a row in `index.html`'s parts list linking to it.
4. Replace `mailto:you@example.com` placeholders in both files.
5. Test OnShape embeds on mobile before finalizing — the viewer is heavy
   and may need a "view on OnShape" fallback link on slow connections.

## Known open decisions
- Currently only flagship projects should probably use live OnShape embeds;
  consider static renders for the rest to avoid full-portfolio dependency
  on OnShape uptime (see chat history for the reasoning).
- Fonts loaded from Google Fonts CDN — fine for GitHub Pages, but note the
  external dependency if that matters to you.
