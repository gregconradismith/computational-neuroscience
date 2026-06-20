# Codex Handoff

Date: 2026-06-19

Repo: `computational-neuroscience`

Branch: `main`

Current Git status at handoff creation:

```bash
## main...origin/main
```

## Repository Role

This repository publishes the APSC 450 Computational Neuroscience course site
from editable Markdown source in `docs/`.

## High-Value Context

- Read `AGENTS.md` before editing.
- Source pages live in `docs/_materials/`.
- Source posts live in `docs/_posts/`.
- GitHub Actions builds Jekyll from `docs/` and deploys Pages.
- The original WordPress export is preserved under `tmp/`.
- Oversized WordPress media may be left as external links rather than copied
  into the repository.
- Public site: https://gregconradismith.github.io/computational-neuroscience/
- Recent design work aligned the site with the
  `cellular-biophysics-and-modeling` course-site style:
  - landing page uses a full-width image banner;
  - landing page menu uses large centered buttons;
  - home page recent announcements use a centered dated list;
  - `/posts/` Announcements uses a centered dated list rather than card panels;
  - archive/export framing was removed from public-facing pages.
- The latest pushed commit at this handoff is `133aa48` (`Remove announcements
  subtitle`). If local state differs, inspect `git log --oneline -5`.
- On 2026-06-19, the published CN `/posts/` HTML and CSS were fetched directly
  and confirmed to no longer include the Announcements subtitle and to include
  `.posts-listing` centering rules. If Greg sees stale text, suspect browser or
  CDN cache first.

## Useful Commands

Check Git state:

```bash
git status --short --branch
git diff --check
```

Inspect the Pages workflow:

```bash
sed -n '1,220p' .github/workflows/pages.yml
```

## Notes For The Next Codex

- Do not run local Jekyll/Bundler unless Greg explicitly asks.
- Keep source edits in Markdown and shared layouts/assets.
- Preserve the CBM-inspired live-course-portal feel. Avoid reverting to
  generic WordPress-export card grids for the landing page or Announcements.
- Avoid committing generated `_site/`, Bundler artifacts, or export noise.
- After adding or updating `AGENTS.md` / `CODEX-HANDOFF.md`, commit the scoped
  change and push it to `main`.
